# Legacy extracts and external feeds

Every fact carries its verification date. Re-verify anything load-bearing.

---

# RDS_P.<PRACTICE> — raw legacy EMR extracts

*Verified 2026-08-28.*

**These are PM / billing extracts only. There is no clinical data in them.** For `RDS_P.CAAG`
and `RDS_P.CAA` the complete table list is charges, payments, AR balance/aging, appt details
(+ snapshots), patient demographics, insurance master, location master, provider master,
transaction details (`_NEW` = second legacy system), and Rosch allergy charge/order history.
**No medication, problem-list, or order table.** "What drug was this patient on before the
conversion?" cannot be answered from the warehouse — it has to come from the source EMR.

- Each practice schema exposes **`VW_<CODE>_CAP`**, the view that feeds `PRIVATE.CORE.CAP`.
- Diagnosis coverage is uneven. `CAA_TRANSACTION_DETAILS`/`_NEW` **do** carry
  `SVC_PRIMARY_DIAGNOSIS` (usable as a clinical proxy — D80–D84 found 50 Coastal
  immunodeficiency patients). **CAAG legacy has no diagnosis column anywhere** — neither
  `CAAG_CHARGES` nor `CAAG_APPT_DETAILS`.
- `RDS_P.SCENT_ALLMEDS_DISCRETE_EXTRACT` is a **one-time, frozen** extract (encounters
  through 2024-07-22). `R143_MEDICATIONS_20240722` has 664K rows / 118K patients with drug
  name, NDC, RxNorm, prescriber. Not CAAG or Coastal. Don't treat as live.
- Naming varies by source system: NWENT is `NEMR_*`, ENTSG is `SEMR_*`, Piedmont is `NG_*`
  (NextGen), Cornerstone is `CS_*`.
- `RDS_P.UTILITIES` (69 `*_CLONE` tables) is load-process scratch — ignore.
- Drug questions go to **`MODMED.ANCILLARY.MEDICATION`**. Caveats: `source = SURESCRIPTS`
  rows are real pharmacy fill history but carry **no `date_started`**, so duration of therapy
  is unavailable; `location` is **not** a site (it holds laterality codes AU/AD/AS/OU/OS/OD)
  — use `firm_global_id` joined to `PRIVATE.MASTER.MODMED_PRACTICE_M`; the same product
  repeats per strength, so dedupe patient × drug.

---

# PRIVATE.AAA / RDS_P.AAA — Atlanta Allergy & Asthma

*Verified 2026-08-28 on Jan–May 2026 service dates.* **Not ModMed data.**

`AAA_TRANSACTIONS_QA1` is transaction grain: separate `Charge` / `Payment` / `WriteOff` rows
per CPT line, joined by `CLAIM_NO` + `CPT_CODE` + `SERVICE_DATE`. Charge rows carry
`BILLED_CHARGE`/`UNITS`; payment rows carry
`INSURANCE_PAYMENT`/`PATIENT_PAYMENT`/`ALLOWED`/`CONTRACTUAL`/`WRITEOFF_AMOUNT`.

- **`SUM(ALLOWED)` double-counts and cannot be used as a dollar figure.** Reversed and
  reposted remits each write the allowed amount again, and secondary payers post their own
  allowed to the same line. Peach State's summed allowed ran 1.78x its insurance paid.
  `ALLOWED` is trustworthy only as a **`> 0` yes/no flag**. For dollars use
  `INSURANCE_PAYMENT + PATIENT_PAYMENT`. Same problem with `CONTRACTUAL`.
- **"Paid" vs "allowed" is the whole analysis, not a nuance.** On 95004 + same-day E&M the
  two differ by 18.5 points (80.6% vs 99.1%) — entirely patient deductible/coinsurance.
  Scoring only on paid manufactures a payor-denial finding that doesn't exist.
- **`Kaiser Cap` is capitated — insurance payment is $0 by design** (846 of 942 claims), and
  it's ~15% of AAA's 95004 volume. Carve it out of any payment-rate denominator.
  `Kaiser PPO`/`EPO`/`Permanente Insurance Company` are separate, tiny, fee-for-service.
- **No CARC/RARC codes.** Only AAA's own `ADJUSTMENT_CODE` write-off codes (`BUN`, `MAX`,
  `NONCOV`, `NODOC`, `NONPAR`, `DUP`, `TF`, `AUTH`). This *understates* denials — a denied
  line under appeal has no posting and is indistinguishable from "not yet adjudicated". Best
  "processed" filter: `ALLOWED + CONTRACTUAL <> 0 OR INSURANCE_PAYMENT <> 0`.
- `PRIMARY_INSURANCE_NAME` is constant across a claim's rows and is the reliable payer key;
  `INSURANCE_NAME` is whoever actually paid. `INSURANCE_NAME = 'Patient'` marks time-of-
  service copays, not adjudication. `PAYMENT_TYPE = 'Non Payment Data'` is a zero-pay ERA.
- ~119 distinct `PRIMARY_INSURANCE_NAME` on 95004. Aetna Signature Administrators TPAs
  (Meritain, Luminare, WebTPA, HealthEZ, EMI, Nippon) price off the Aetna schedule;
  UMR/Surest/Oxford/GEHA are UHC; exchange products of Medicaid brands
  (`Ambetter from Peach State (Exchange)`) are **not** Medicaid.
- **On 95165, `FACILITY_NAME` is the central mixing lab, not the patient's clinic.** Clinic
  must come from `ROSCH_ORDERHISTORY.FINAL_LOCATION` matched to the nearest `ORDERED_DATE`
  (97.8% within 7 days). `Mail Out` is a real `FINAL_LOCATION`, not a clinic.
  `RDS_P.AAA.CLAIM_PATIENT` maps `CLAIM_NO` → `PATIENT_ACCT_NO` at 99.93%.

---

# PRIVATE.SCP_CLAIMS — external market claims

*Verified 2026-08-19.* Two tables. Sigma `search` for "SCP_CLAIMS" only surfaces the ENT one.

1. **`SHORE_CAPITAL_PARTNERS_CLAIMS_DASHBOARD`** — the useful one. 44.3M rows, 50.6M claims,
   9,936 CPTs, 8,102 orgs, 60,273 NPIs, Q1 2024–Q3 2026. Scoped to Shore Capital portfolio
   markets (GA, NC, KY, IN, AL), not national. Zip and NPI are integers with real SQL NULLs.
2. **`SCP_CLAIMS_ENT_DATA_JULY_2026`** — 7.9M rows, national, but only 49 procedural ENT CPTs
   and zero office E/M. **Nulls are the literal string `'null'`** — `IS NULL` returns nothing
   and silently passes them through. Mostly superseded.

- **`type_1_npi` is the performing/billing provider, NOT the referring provider.** Tested
  three ways. Neither table has any referring/ordering field, and there is no patient
  identifier, so **no table here can trace a referral to a competitor or follow a patient who
  left.**
- Leakage recipe that works: demand per referrer from E&M claims filtered to ENT/allergy
  ICD-10 grouped by `type_1_npi`, versus referrals actually received via
  `MODMED.DATA.PATIENT_REFERRING_PROVIDER` (`is_latest = TRUE`) → `REFERRAL_CONTACT` on
  `referring_provider_id = referral_contact_id` **and `firm_id`**. Join
  `REFERRAL_CONTACT.npi` → `CAST(type_1_npi AS text)`: 14,220 of 37,393 referrer NPIs match.
- **Do not filter specialty by `organization_name LIKE '%ENT%'`** — misses "EAR, NOSE AND
  THROAT SPECIALISTS, LLC" and wrongly catches any name containing "CENTER". Use
  `taxonomy_code` or NPPES.
- Quarters: `MIN`/`MAX` sort alphabetically and lie. Complete through **Q4 2025** only.
- `short_description`/`long_description` describe the **diagnosis**, not the procedure.
  `patient_count` is per-row distinct — summing double-counts. **No dollars.**
  `patient_zip` is 3-digit.
- **Panel attrition is a trap for trending.** Of 62 orgs with 100+ claims in early 2024, 6
  collapsed >80% and 2 vanished by late 2025. Northwest ENT drops 2,600 → 21 — feed
  attrition, not lost business. Never show share-over-time without absolute counts beside it.
- Coverage: works for Advanced ENT (KY/IN), NWENT, NEGA, ENTC, Piedmont ENT, ENTSG, CAAG, AAA
  (GA), Cornerstone + A&A Specialists (NC), SCENT (SC, thin). **Does not work for Reston ENT
  (VA) or ASA (TX)** — almost no VA/TX data. AAA and Coastal capture zero referring NPIs.

---

# Other external systems

**`RDS_P.MKT_CRM.CRM_SURVEYS`** *(verified 2026-08-19)* — physician-liaison visit surveys.
`visiting_rep` = first + last; **`VISITING_REP_EMAIL` also exists** and is the stable key.
Traps for anything keyed on rep identity: fallback strings can name two people
(`'Trevuan Jeffries and Kristin Ashby'`); CRM spells one rep "Tre Jefrries" (typo); **Sigma
logins ≠ CRM emails** (of 12 active reps, 7 match, 3 have no Sigma account); `max_by` awards
a provider to the most-recent visitor, and 243 of 7,799 provider/clinic pairs have 2+ reps.

**`RDS_P.RATER8`** (21) — patient/employee reviews. Per-practice `R8_<CODE>_EXPORT` plus
`R8_EMPLOYEE`, `R8_LOCATION`, `R8_PRACTICE`, `R8_*REVIEW`. Review detail also in
`PRIVATE.ANCILLARY`; reference copies in `IDM_P.REFERENCEDATA.R8_*`. The
`MKTG_P.ANALYTICS.VW_R8_*` views belong to the deprecated mart — go to `RDS_P` directly.
**[not profiled]**

**`RDS_P.SAGE_API`** (16, raw) / **`PRIVATE.SAGE`** (16, curated) — Sage Intacct: GL detail,
AP/AR invoices and payments, vendors, customers, departments, locations, classes.
**[not profiled]**

**Dialpad** — `RDS_P.DIALPAD.CALL_LOGS*` (per practice) and
`PRIVATE.SIGMA_STORAGE.DIALPAD_CALLS`. **No external caller number** — only practice, entry
point, agent, durations. **Useless for patient attribution.** Feed lags several days.
*(Verified 2026-08-20.)*

**Google Analytics** — `RDS_P.GOOGLEANALYTICS` (GA4 + per-practice `*_EVENTS`). The
`MKTG_P.ANALYTICS.GA4_*` copies are in the deprecated mart. **[not profiled]**

**Salesforce** — `RDS_P.BD_SF_LEGACY` (141 raw SF objects), `RDS_P.SALESFORCE_BD` (6 core),
`APPLICATIONS.SALESFORCE` (14 enriched). Ignore `BSNSDEV_P.ANALYTICS.VW_SF_*`.
**[not profiled]**

**Others, not profiled:** `RDS_P.ZOCDOC.ZOCDOC_BOOKINGS`, `RDS_P.LIINE.LIINE_INTERACTIONS`,
`RDS_P.ASSORT.ASSORT_AGG`, `RDS_P.RCM.WAYSTAR_REPORTING`, `RDS_P.HR.TALENT_DEVELOPMENT`,
`RDS_P.MKT_NPS.NPS_SURVEYS`, `RDS_P.TRIZETTO`, `BREVIUM.PDENT` (25 `FINAL_*`).

**Payroll / hours has no usable source.** Kronos landed in `IDM_P.TRANSACTIONS.KR_*`, but
that schema is deprecated and its contents are not trustworthy *(Dean, 2026-08-29)*. If asked
for payroll, hours or headcount, say the source isn't reliable rather than producing a
number from it. `RDS_D.KRONOS` is a dev mirror. The reference-side tables
(`IDM_P.REFERENCEDATA.KR_HEAD_COUNT` / `KR_LOCATIONS` / `KR_JOB_LISTING`,
`PRIVATE.MASTER.KRONOS_LOCATION_M`) sit in live schemas and may be fine — verify first.

---

# PRIVATE.SIGMA_STORAGE.SCORECARD_METRICS — ELT Critical Indicators

*Verified 2026-08-19.* Grain `METRIC_NAME × SNAPSHOT_MONTH × LOCATION_NAME`. 22 metrics,
Jan–Jul 2026. `LOCATION_NAME` includes an **`'All Locations'` rollup row** plus 14 practices —
exclude it (and NULLs) for practice-level stats.

**The rollup is not the same operation for every metric:**
- **Sum of practices:** B2B Referrals, E&M Visits, NP Visits, Patient Counter.
- **Unweighted mean:** AR > 90, NPS Rating, Schedule Fill, MIPS 226/331/332 (exact);
  Answer Rate, Denial Rate, PCM, Employee Retention, Front Desk Audit, Avg NP Wait Time,
  Time to Fill, PL NP ROI (near-exact).
- **Neither:** EBITDA / EBITDA YTD do not reconcile (Jan reports −294,103; practices sum to
  −538,114).

Because mean-type metrics are unweighted, Coastal counts as much as Advanced ENT (~14x
larger). For AR > 90 the exec-relevant figure should be dollar-weighted.

**Live data defects (as of 2026-08-19):** New Hire Satisfaction mixes 0–1 and 0–100 scales;
Front Desk Audit is duplicated in Jun and is really quarterly; PCM stopped refreshing after
Mar; MIPS 226's panel shrinks 7→4 so its "improvement" is survivorship; Physician Retention
has SD=0 in Feb/Mar; 8 of 14 practices are pinned at exactly 1.000000 on Answer Rate, so
effective n is 6.
