# PRIVATE.CORE and PRIVATE.MODMED — the workhorses

Every fact here carries the date it was verified. This layer is Senta-built and changes;
re-verify anything load-bearing that is more than a couple of months old.

---

# PRIVATE.CORE.CAP

*Verified 2026-08-28.* Charges and payments across **both** EMR generations. This is the
answer to most "provider × CPT × month" and "charges/collections over time" questions at any
practice that has converted.

**Assembled from** the `VW_<CODE>_CAP` views in each `RDS_P.<PRACTICE>` schema, plus ModMed.
`LEGACY_DESIGNATION` flags each row `LEGACY` or `MODMED`; `SOURCE_DESCRIPTION` names the
specific system. One query and one methodology therefore cover both sides of a cutover.

Scale: pre-aggregating to practice × provider × month × CPT over 36 months is ~270K rows,
631 providers, 14 practices.

### Traps

- **Neither ModMed nor the legacy extract alone covers a trailing 24 months at a converted
  practice.** Any "the report shows zeros for recent months" complaint at a converted
  practice is almost certainly this, not a volume decline.
- **`RVUS` is computed per claim LINE, not per unit.** Proven on 95017/95018: RVUS is
  constant (0.07 / 0.14) whether the line carries 6 units or 32. Correct for single-unit
  codes (99214 = 1.92/line, 94010 = 0.17) but **materially understates multi-unit codes** —
  95004 shows 11.59 wRVU against 72,998 units. **Never present CAP RVUs as a provider's wRVU
  total.** Use `UNITS` as the volume measure and price true wRVUs from the CMS RVU file
  (`IDM_P.REFERENCEDATA.RVU_MASTER_2023`, `PUBLIC.MASTER.RVU_M`).
- **`UNITS` vs `COUNT(*)` matters in allergy.** For 95004 (skin tests), 95165 (extract prep)
  and 95044 (patch tests) a unit is a dose/test, not an encounter — 95004 ran ~3,000 units
  across ~48 lines/month for one provider. Report both.
- **`TRAN_TYPE` is exactly `'Charges'` / `'Payments'`.** Charges carry `AMOUNT` and `RVUS`
  with `COLLECTION_AMOUNT` = 0; payments carry `COLLECTION_AMOUNT` with `AMOUNT` = 0. Sum
  conditionally, never blindly.
- **`DEPARTMENT` is place of service** (`Office`/`ASC`/`Hospital`/null), **not** a service
  line, despite its column comment. Use `SVC_LINE`.
- **`SVC_PROVIDER` is the rendering provider** — equivalent to the Allscripts "Actual
  Provider" grouping. Only exists once charges post.
- **`VISIT_REF_ID` does NOT join to `PRIVATE.MODMED.APPOINTMENT.VISIT_ID`.** 17,347 vs
  35,099 ids produced **1** match; the column comment says "GENERATED". To attach charges to
  appointments, aggregate CAP to `(PAT_REF_ID, TO_DATE(SERVICE_DT))` and join on
  `PATIENT_M.MRN` + `TO_DATE(APPOINTMENT_START_DATE)` — `PAT_REF_ID = PATIENT_M.MRN` matched
  17,579/17,579 at Advanced ENT.
- **`PAT_REF_ID` is the only unified patient key across eras.** It is **not** joinable to
  ModMed `PATIENT_ID` (which is `<id>-pod45` shaped).
- **Non-clinical ledger rows live in `CPT`:** `VOID`, `BALFWDAS` (Allscripts balance-forward
  conversion artifact), `No Show`, `No Show Fee`, `School Forms`, `Replacement Shot Card`.
  Exclude from any procedure or case log.
- **`FINANCIAL_CLASS` understates Medicare** — Medicare Advantage is filed under commercial
  brand classes and Medigap under `Commercial`. Classify from `PAYER_NAME` instead.
- **`PATIENT_AGE` is age as of refresh**, so age at service ≈ `PATIENT_AGE − (2026 − year)`.
- **Legacy months don't always tie to a print from the live legacy system.** For Coastal,
  94010 Sep 2024 reads 29 in CAP vs 8 on the Allscripts print — traced to how the
  EMR OLD → EMR NEW conversion was loaded. Charge-per-unit reconciles exactly. Say so up
  front rather than trying to reconcile.
- Legacy `POST_DT` == `SERVICE_DT`, so post-date vs service-date is not a variance source on
  the legacy side.
- Freshness runs ~1 day behind.
- Watch `Kenney, Tina` / `ZZKenney, Tina` (Advanced ENT) vs `Monica Rama Kenney` (Coastal) —
  different people.

---

# PRIVATE.CORE.APPT_DETAILS

*Verified 2026-08-13.* ~6.8M rows, one per appointment. The right table for **patient
demographics and appointment mix by office**. Carries `PRACTICE_NAME`, `LOCATION_NAME` (true
service office, ~80 of them), `DEPARTMENT`, `DIVISION`, `APPT_PROVIDER`, `PROV_TYPE`,
`PATIENT_AGE`, `PATIENT_DOB`, `VISIT_STATUS`, `VISIT_TYPE`, and `REFERRING_PROVIDER_NPI`.

### Traps

- **Zero Reston ENT rows** (verified 2026-08-19). Use `PRIVATE.MODMED.APPOINTMENT` there.
- **`PATIENT_AGE` is age TODAY, not age at the appointment.** Over a multi-year window this
  shifts the mix older and understates peds. Compute
  `FLOOR(DATEDIFF('day', PATIENT_DOB, APPT_DATE) / 365.25)` and bucket
  `age IS NULL OR age < 0 OR age > 110` as Unknown (442,829 null DOBs, 28 negative, 550 >110).
- **`PROV_TYPE` is the cleanliness filter.** `Phys` (119) / `Mid-level` (117) /
  `Audiologist` / `Clinical Staff` are mapped; **`PROV_TYPE IS NULL` holds 122,446 distinct
  junk `APPT_PROVIDER` strings** (legacy free-text like `NWENT MARIETTA SHATUL PARIKH
  POST/OP`). Always filter to a real `PROV_TYPE` before counting providers.
- **`VISIT_STATUS` is unusable raw** — legacy + ModMed, mixed case, trailing padding, ~70
  distinct values. Bucket: `CANCEL`→Cancelled (test first), then
  `NO SHOW`/`NO_SHOW`/`NO-SHOW`/`MISSED`→No Show, `RESCHEDUL`→Rescheduled,
  `COMPLET`/`CHECK`/`KEPT`/`ARRIVED`→Kept, else Other. Leaves 0.4% in Other.
- **`APPT_DATE` runs into the future** (scheduled appts out to 2028–2029). Cap at
  `CURRENT_DATE` for historical questions.
- Referring provider: 433,930 of 1,020,564 appointments in 2025 have a
  `REFERRING_PROVIDER_NPI` (42%), 15,222 distinct. This is a better referral source than
  ModMed's `PATIENT_REFERRING_PROVIDER` → `REFERRAL_CONTACT` hop.
- `PATIENT_M.PROVIDER_NAME` is NULL for 82% and is a panel/PCP attribution — not usable for
  "by office". `PATIENT_M.LOCATION_NAME` is the **practice**, only 13 values.
- Name formats differ: `PATIENT_M` = `"Last, First"`, `APPT_DETAILS.APPT_PROVIDER` =
  `"First Last"`. Fuzzy matching bites — `ILIKE '%ingley%'` also catches `Tingley`, `Singley`.

---

# PRIVATE.MODMED (94 tables)

*Verified 2026-08-19.* Curated ModMed with plain-English `LOCATION_NAME` (13 practices),
`BUSINESS_UNIT`, `FACILITY_NAME`, `PAYER_NAME`, `FINANCIAL_CATEGORY` already joined — no
staff/facility joins needed. **Prefer this over `MODMED.DATA` for practice-admin questions.**
Current to the prior day.

Confirmed present: `ACCOUNTS_RECEIVABLE`, `APPOINTMENT`, `APPOINTMENT_MISSING_CHARGES`,
`CLAIM`, `CLAIM_LOG`, `CHARGES`, `BILL`, `BILL_ITEM`, `UNBILLED_POSTED_CHARGES`,
`PRE_COLLECTIONS`, `PATIENT_STATEMENT`, `PATIENT_M`, `STAFF_M`, `VISIT`, `TASK`,
`APPOINTMENT_TYPE_M`, `BUSINESS_UNIT_M`.

### Traps

- **`APPOINTMENT_MISSING_CHARGES` is not a work queue.** At Reston, 5,060 of 5,544
  checked-out rows over 180 days are `Allergy Injection` plus 410 `Allergy Test` — 91%,
  running a flat ~220/week. Allergy visits check out without posting a charge. Exclude both
  types or the real signal is invisible (residual: ~84 visits/year).
- **`APPOINTMENT` has a `"NEW PATIENT"` column — with a space**, not `NEW_PATIENT`. Needs
  double-quoting in Snowflake.
- **Forward-book comparisons must be reconstructed point-in-time**, or future weeks look
  inflated because cancellations accumulate. Use
  `CREATED_DT <= week_start - 5d AND (CANCELLED_DT IS NULL OR CANCELLED_DT > week_start - 5d)`.
  Without it, next week read as an all-time high; with it, 3rd of 13.
- **`DATE_TRUNC('week')` is Monday-start in Snowflake but the Sigma MCP SQL layer truncates
  to Sunday.** The two give different weekly numbers — don't cross-check one against the other.
- **`TIMELY_FILING_DATE` is null on ~92% of Reston insurance AR lines.** Use
  `BILLED_STATUS = 'No'` instead.
- **Test providers carry real data.** `'TOPPLE, Testing'` had 16 checked-out appointments
  with real payers in 180 days. Filter `PRIMARY_PROVIDER NOT ILIKE 'TOPPLE%'`. ModMed-side
  test patients: `last_name LIKE '%test%'`; test provider ids `16681801-pod45`,
  `9473449-pod45`, `16057337-pod45`.
- **A negative `DATEDIFF` to `FOLLOW_UP_DATE`** means the follow-up is diarised ahead — those
  claims are already owned, don't count them as stale.
- `APPOINTMENT` carries patient match keys inline (`PATIENT_MRN`, `PATIENT_EMAIL`,
  `PATIENT_MOBILE_PHONE`, `PATIENT_HOME_PHONE`) — no `PATIENT_M` join needed just to match,
  though they lag 1–2 days per the column comments. Phones are bare digits, variable length,
  with junk (`0000000`, `9999999999999`).
- `APPOINTMENT_DATE_CREATED` is "date the appointment was scheduled" — the field campaign and
  conversion questions actually need, distinct from `APPOINTMENT_START_DATE`.
- Rendering provider: `APPOINTMENT.PROVIDER` is a staff id → join `STAFF_M.STAFF_ID`.
- `APPOINTMENT_STATUS` values seen: `CHECKED_OUT`, `PENDING`, `CANCELLED`, `CONFIRMED`,
  `NO_SHOW`, `CHECKED_IN`, `ARRIVED`. "Seen" = last three + `CHECKED_OUT`; "seen and billed"
  needs a charges check, since seen-but-unbilled is a real state.

---

# Cross-cutting: things with no clean answer

- **No provider-key bridge between ModMed and CAP.** `ORDER_LOG` uses `staff_id`
  (`16681801-pod45`); CAP uses `SVC_PROVIDER` name + `PROVIDER_KRONOS_ID`. Neither
  `PRIVATE.MASTER.PROVIDER_M` nor `IDM_P.DIMENSIONS.PROVIDER_MASTER_NEW` carries `staff_id`.
  Only path is `provider_id → MODMED.DATA.STAFF → name → PROVIDER_M`, name-matching ~170
  providers. **Unsolved.** `MODMED.DATA.LINK_STAFF` is *not* the answer — it is a CDC
  watermark table (`staff_id` + `CDC_TS` only), verified 2026-08-29.
- **`MODMED.DATA.FIRM` has no NPI column**, so there is no clean group-NPI source for
  identifying Senta in external claims data.
- **Net revenue** needs `MODMED.DATA.PRODUCTION_SUMMARY`
  (`ledger_charge_amount − ledger_adjustment_amount`); CAP's `COLLECTION_AMOUNT` is cash.
