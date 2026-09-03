# Source routing — pick the database before you pick the table

Read this on every question. Enumerated and verified **2026-08-29**.

## The two questions that decide everything

**1. Which practices, and does the window touch their EMR transition?**
Check `practice_registry.md` — it has a derived table of legacy system, ramp start and legacy
end for all 14 practices. If any practice in scope was on a legacy EMR for part of the window
→ **`PRIVATE.CORE.CAP`**. Neither ModMed nor the legacy extract alone covers a trailing 24
months at a converted practice, and the missing half looks like a volume collapse rather than
a data gap.

Three things that make this harder than it sounds:
- **It's a window, not a date.** Piedmont ran both systems 16 months, ENTSG 12, SCENT 10.
  A single switchover date is wrong for the entire ramp.
- **AAA never converted** — it is 100% legacy eCW, no ModMed data at all.
- **Cornerstone ENT, NEGA and Reston ENT are ModMed-native** in CAP with no legacy rows, so
  ModMed alone is safe for those three.

**2. Is the question clinical, or financial/operational?**
Clinical detail (diagnoses, exams, meds, orders, path, MIPS) exists **only** in ModMed.
The legacy extracts are billing/PM only — there is no clinical data in them at all.

## Routing table

| Question | Source | Notes |
|---|---|---|
| **Any named metric** — visits, charges, collections, RVUs, new patients, referrals, budget vs actual, doc days | `SIGMA_DT_SPINE.VERTEBRAE.CAP_METRICS` | **Read `metric_definitions.md` first — it carries the canonical rule for each.** Agrees with `PRIVATE.CORE.CAP` to the cent; adds pre-computed flags. Charge-line grain, so `COUNT(*)` is wrong for almost every metric. |
| Provider × CPT × month volume, any practice, crossing a cutover | `PRIVATE.CORE.CAP` | The only cross-EMR spine. `LEGACY_DESIGNATION` flags each row. |
| Charges / collections / RVUs across eras | `PRIVATE.CORE.CAP` | `TRAN_TYPE` splits Charges vs Payments — sum conditionally. |
| Appointments, demographics by **office** | `PRIVATE.CORE.APPT_DETAILS` | ~80 real offices. **No Reston ENT rows** — use `PRIVATE.MODMED.APPOINTMENT` there. |
| AR aging, cross-era | `PRIVATE.CORE.AR_AGING` | |
| Practice-admin: AR, claims, tasks, statements, unbilled, pre-collections | `PRIVATE.MODMED.*` | 94 curated tables with `LOCATION_NAME`, `PAYER_NAME`, `FINANCIAL_CATEGORY` pre-joined. Prefer over `MODMED.DATA` for ops work. |
| Clinical: dx, exam, meds, orders, path, labs, MIPS | `MODMED.ANCILLARY` / `MODMED.DATA` | See `modmed/schemas.md` for which. ModMed era only. |
| "As of" / point-in-time, AR trend, panel over time | `MODMED.SNAPSHOTS` | Filter `report_date` **first**. Ignore `SNAPSHOTS_RECOVER`. |
| Surgery order conversion | `MODMED.ANCILLARY_SNAPSHOTS.ORDER_LOG` | Snapshot floor 2025-09-08. Don't compute history from the live `ANCILLARY.ORDER_LOG` — status decays. |
| Drugs / medications | `MODMED.ANCILLARY.MEDICATION` | Legacy schemas have **no** medication table. |
| Pre-cutover detail for one practice | `RDS_P.<PRACTICE>` | Raw legacy extract. See `legacy_and_external.md`. |
| Payroll, hours, headcount | **No usable source.** | Kronos data sits in `IDM_P.TRANSACTIONS.KR_*` but that whole schema is deprecated and the contents are not trustworthy *(Dean, 2026-08-29)*. Say so rather than querying it. `PRIVATE.MASTER.KRONOS_LOCATION_M` and `IDM_P.REFERENCEDATA.KR_HEAD_COUNT` / `KR_LOCATIONS` / `KR_JOB_LISTING` are reference-side and may be fine — verify first. |
| NPI, RVU, insurance/location mapping, calendar | `IDM_P.REFERENCEDATA` | **Live.** `NPI_MASTER_NPPES`, `RVU_MASTER_2023`, `INSURANCE_MAPPING_M`, `CALENDAR_MASTER`, `DATES_M`, `CPT_CYCLE_TIMES`. |
| Provider master / referring provider master | `IDM_P.DIMENSIONS` or `PRIVATE.MASTER` | **Live.** `PROVIDER_MASTER_NEW`, `SENTA_PROVIDER_MASTER`, `SENTA_REFERRING_PROVIDER_M`, `SENTA_FACILITY_M`. |
| Budgets, service line, fee schedule, denial mapping | `PRIVATE.MASTER` | `BUDGET_*`, `SERVICE_LINE_M`, `DENIAL_M`, `MODMED_PRACTICE_M`, `KRONOS_LOCATION_M`. |
| Physician P&L, comp, cost allocation | `PRIVATE.PL_SUPPORT` (25 tables) + `PRIVATE.DOC_COMP` | Read the build order; many are intermediate. |
| Rev rec | `PRIVATE.REVREC.CAP` | The rest of that schema is dated `CAP_YYYYMMDD` snapshots. |
| ELT / exec scorecard | `PRIVATE.SIGMA_STORAGE.SCORECARD_METRICS` | Also `SIGMA_DT_SPINE.GROWTH_CORE.B2B_SCORECARD_METRICS`. |
| External claims / market / leakage | `PRIVATE.SCP_CLAIMS` (2 tables) | `type_1_npi` is the **performing** provider, not the referrer. |
| AAA allergy transactions, immunotherapy | `PRIVATE.AAA` / `RDS_P.AAA` | `AAA_TRANSACTIONS_QA1` is the payment-grain one. Not ModMed. |
| Patient reviews / reputation | `RDS_P.RATER8` (`R8_*`) | Per-practice `R8_<CODE>_EXPORT` tables. |
| CRM / physician-liaison visits | `RDS_P.MKT_CRM` (`CRM_SURVEYS`, `MD_VISITS_FROM_CRM`) | Also `RDS_P.SALESFORCE_BD`, `RDS_P.BD_SF_LEGACY` (141 raw SF objects). |
| Accounting / GL / AP / AR invoices | `RDS_P.SAGE_API` (raw) or `PRIVATE.SAGE` (curated) | Sage Intacct. |
| Web analytics | `RDS_P.GOOGLEANALYTICS` | `GA4_*` plus per-practice `*_EVENTS`. Ignore the `MKTG_P` copies. |
| Phone calls | `RDS_P.DIALPAD.CALL_LOGS*`, `PRIVATE.SIGMA_STORAGE.DIALPAD_CALLS` | **No external caller number** — useless for patient attribution. |
| NPS | `RDS_P.MKT_NPS.NPS_SURVEYS`, `PUBLIC.SIGMA_STORAGE.MKT_NPS` | |
| Online booking | `RDS_P.ZOCDOC.ZOCDOC_BOOKINGS`, `RDS_P.LIINE.LIINE_INTERACTIONS`, `RDS_P.ASSORT` | |
| Clearinghouse | `RDS_P.RCM.WAYSTAR_REPORTING` | |
| Patient reactivation (PDENT) | `BREVIUM.PDENT` (25 `FINAL_*` tables) | |
| No-show / cancellation prediction | `PRIVATE.ML_CNS`, `PRIVATE.SIGMA_STORAGE.CANCEL_NO_SHOW_*` / `CNS_XGBOOST_*` | Many versioned iterations — confirm which is live. |
| Patient LTV model | `PRIVATE.LTV_PREDICT`, `SENTA_AI.LTV_PREDICT` | |
| Payer policy briefs (AI) | `SENTA_AI.PAYER_POLICY` | |
| Schedule smartfill | `SENTA_AI.ML_CNS.SMARTFILL_*` | |
| Next-available-appointment / access | `PUBLIC.SIGMA_STORAGE.DDFE_*` | |
| Sigma usage, Claude/AI usage, Snowflake spend | `APPLICATIONS.SIGMA`, `APPLICATIONS.SNOWFLAKE_ACCOUNT_USAGE`, `AUDIT_LOG.SIGMA_SHARED` | Includes `ANTHROPIC_*` usage tables. |
| The ModMed data dictionary itself | `MODMED.UTILITIES.MODMED_DATA_DICTIONARY` | The dictionary is a **table** — queryable, and the way to refresh `references/modmed/`. |

## Never query these

- **`RCM_P`, `MKTG_P`, `OPRTNS_P`, `FPA_P`, `BSNSDEV_P`** (~400) — dead Sigma project.
- **`IDM_P.TRANSACTIONS`** (114) — the old integration layer, deprecated *(Dean,
  2026-08-29)*. Includes the Kronos `KR_*` family; the data is there but is not trustworthy.
  `IDM_P.REFERENCEDATA` and `IDM_P.DIMENSIONS` **are** still in use — only `TRANSACTIONS` is
  dead.
- **`RDS_D.*`, `IDM_D.*`** — dev mirrors.
- **`MODMED.SNAPSHOTS_RECOVER`** — duplicate of `MODMED.SNAPSHOTS`.
- **`SENTALYTICS_P.SIGMA`** (737 tables) — 100% Sigma-generated `SIGDS_*` / input-table
  audit-log artifacts. Same for the `SIGDS_*` / `SIGMA_DF_CSV_*` / `VIEW_*_<hash>` tables in
  `*_P.SIGMA`, `BSNSDEV_P.SIGMA`, `FPA_P.SIGMA`, `RCM_P.SIGMA`, `OPRTNS_P.UPLOAD`.
- **`PRIVATE.VALIDATION`** (144 `CAP_YYYYMMDD`) and the dated `CAP_*` in `PRIVATE.REVREC` —
  weekly validation snapshots, not analysis sources.
- **`RDS_P.UTILITIES`** (69 `*_CLONE`) — load-process clones.
- **Snowflake marketplace/sample data**, visible but irrelevant: `EXAMPLES`, `RETAIL`,
  `GLOBAL_GOVERNMENT`, `SNOWFLAKE_WEATHER_ENVIRONMENT`, `US_OPEN_CENSUS_DATA…`, `SANDBOX`,
  `FUN`, `CARDINAL`, `HEALTHCARE_LIFESCIENCES`, `BACKUPS`, and most of `FINANCE`
  (`PLUGS_ELECTRONICS_FINANCIALS`, `STOCKS`, `BITCOIN`, `LENDING_CLUB` are demo sets).

## Departmental marts — ignore them

`RCM_P` (revenue cycle), `MKTG_P` (marketing), `OPRTNS_P` (operations), `FPA_P` (FP&A) and
`BSNSDEV_P` (business development) — **~400 tables — were built for an earlier Sigma project.
All five are dead. Do not route to them.** *(Confirmed by Dean, 2026-08-29.)*

Structurally they each hold an `ANALYTICS` and/or `SIGMA` schema plus the same per-practice
schemas (AAA, ASA, ADVANCED_ENT, RESTON_ENT, SCENT, ENTSG, PIEDMONT, NWENT, CAAG, ENTC),
whose tables duplicate `PRIVATE.<PRACTICE>`. **Use `PRIVATE.<PRACTICE>` or `PRIVATE.CORE`
instead.** A mart table in an inherited query or old workbook is a repoint candidate, not a
source to build on.

## PRIVATE.SIGMA_STORAGE — treat every table as unknown

*(Dean, 2026-08-29.)* **This is where Sigma input tables and uploaded CSVs land.** It is not
a curated layer, the names are not self-describing, and **you genuinely cannot tell what a
table is without opening it in Sigma or running `describe`.** 602 tables.

Rules:
- **Never infer contents from a name here.** Verify before use — always.
- **Never treat it as a routing destination** for a general question. Go there only when
  looking for a specific known asset, or when the user points you at one.
- Expect dated one-offs (`*_20240812`), abandoned iterations, and personal uploads. The
  `CANCEL_NO_SHOW_*` / `CNS_XGBOOST_*` family alone has a dozen versions with no reliable way
  to tell which is live — **ask, don't guess.**

Assets verified in earlier work, safe to reference by name:
`SCORECARD_METRICS` (ELT Critical Indicators — see `legacy_and_external.md`),
`DIALPAD_CALLS`, `APPT_DETAILS_SNAPSHOTS`, `CAP_ICD10`.
`PUBLIC.SIGMA_STORAGE` has the same character — `DDFE_*` (next-available appointment),
`CAC_CURVE*`, `MKT_CRM`, `MKT_NPS`.

> Still unprofiled and **inferred from naming, not verified**: `PRIVATE.PL_SUPPORT` (25) and
> `PRIVATE.VALIDATION` (144, dated CAP snapshots). Names are in `warehouse_map.md`; confirm
> live before relying on them.
