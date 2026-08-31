# Warehouse map

Complete schema inventory, enumerated **2026-08-29** via
`GET /v2/files?typeFilters=table&limit=1000` paginated on `nextPage` (12 pages).

**11,815 table inodes → 6,088 distinct `(database, schema, table)` → ~4,814 after removing
Snowflake sample data and Sigma artifacts. 274 schemas.** The inode count is ~2x inflated
because one table is exposed through several connections — so **inode ids are not unique**;
`PRIVATE.CORE.CAP` is both `e7537c86-…` and `8291f9dc-…`. Resolve by path, not by id.

Counts below are distinct tables. Purposes marked **[inferred]** come from naming and have
not been verified against contents.

---

## MODMED — 951 tables, 7 schemas · the EMR/PM source

| Schema | # | Purpose |
|---|---|---|
| `ANCILLARY` | 272 | Clinical/chart detail, histories, orders, faxes, tasks, ophthalmic. Fully documented in `modmed/`. |
| `DATA` | 217 | Primary current-state PM + core clinical. Documented in `modmed/`. |
| `SNAPSHOTS` | 217 | Daily point-in-time copies of `DATA` + `report_date`. Hundreds of millions of rows — filter `report_date` first. |
| `SNAPSHOTS_RECOVER` | 217 | **Duplicate of `SNAPSHOTS`. Do not use.** |
| `UTILITIES` | 22 | ELT plumbing and validation. **Contains `MODMED_DATA_DICTIONARY`** — the vendor dictionary as a queryable table, and the way to regenerate `references/modmed/`. Also `LINE_COUNTS`, `SNAPSHOT_EXCEPTION_LOG`, `LEGACY_BALANCE_CPTS`. |
| `MIPS` | 4 | `MIPS_AGGREGATED`, `MIPS_RAW`, `MIPS_MVP_RAW`. |
| `ANCILLARY_SNAPSHOTS` | 2 | `ORDER_LOG`, `ORDER_LOG_DETAIL`. Surgery-order conversion; snapshot floor 2025-09-08. |

The dictionary in `references/modmed/` covers 415 tables and is **accurate** — only 1
documented table isn't live. The 71 live-but-undocumented tables are plumbing: ~20 `LINK_*`
(CDC watermarks: `staff_id` + `CDC_TS`, **not** crosswalks) and ~15 `*_LEGACY_BALANCE`
(conversion artifacts). `CLAIM_SCRUB_RESULT` is the one notable undocumented analytic table.

---

## PRIVATE — 1,058 tables, 23 schemas · the curated layer

| Schema | # | Purpose |
|---|---|---|
| `CORE` | **3** | **`CAP`, `APPT_DETAILS`, `AR_AGING`.** The cross-EMR spine — the most load-bearing schema in the warehouse and the smallest. See `senta_core.md`. |
| `MODMED` | 94 | Curated ModMed with `LOCATION_NAME`/`PAYER_NAME`/`FINANCIAL_CATEGORY` pre-joined. Preferred for practice-admin work. See `senta_core.md`. |
| `SIGMA_STORAGE` | 602 | **Sigma input tables and uploaded CSVs.** Not a curated layer. *(Dean, 2026-08-29: "really hard to know what ANY of that is without opening the tables directly in Sigma.")* Never infer contents from a name; `describe` first. Known-good: `SCORECARD_METRICS`, `DIALPAD_CALLS`, `APPT_DETAILS_SNAPSHOTS`, `CAP_ICD10`. Also holds `ASK_SENTA`, `CONSOLIDATED_CONTRACT_TRACKER`, and the `CANCEL_NO_SHOW_*` / `CNS_XGBOOST_*` pipeline (a dozen versions, live one unknown — ask). |
| `VALIDATION` | 144 | Weekly `CAP_YYYYMMDD` validation snapshots. Not an analysis source. |
| `REVREC` | 52 | `CAP` (live) plus 51 dated `CAP_*` rev-rec snapshots. |
| `PL_SUPPORT` | 25 | Physician P&L build chain — payroll aggregation, immuno/biologic revenue splits, mid-level and staff-cost allocations. Many are intermediate; check build order. |
| `MASTER` | 24 | Reference dimensions: `MODMED_PRACTICE_M`, `PROVIDER_M`, `REFERRING_PROVIDER_M`, `SERVICE_LINE_M`, `INSURANCE_MAPPING_M`, `DENIAL_M`, `KRONOS_LOCATION_M`, `FEE_SCHEDULE`/budget tables. |
| `AAS` | 18 | Asthma & Allergy Specialists curated extract. |
| `SAGE` | 16 | Sage Intacct curated (GL, AP, AR, vendors, customers). |
| `AAA` | 14 | Atlanta Allergy & Asthma. **`AAA_TRANSACTIONS_QA1`** is the payment-grain table. |
| `ASA` | 8 | |
| `CAAG`, `SCENT` | 7 each | CAAG includes the Rosch allergy order/charge history. |
| `ENTSG`, `ML_CNS` | 6 each | `ML_CNS` = cancel/no-show model features and predictions. |
| `NWENT`, `PDENT`, `ANCILLARY` | 5 each | `ANCILLARY` holds rater8 review detail + Callbox. |
| `ENTC`, `DOC_COMP`, `LTV_PREDICT` | 4 each | `DOC_COMP` has its own `CAP` variant for physician comp. |
| `SOLA` | 3 | Referral-link audit/output. |
| `SCP_CLAIMS` | 2 | External claims feed. See `legacy_and_external.md`. |

---

## PUBLIC — 275 tables, 15 schemas · mirror of PRIVATE

Same shape as `PRIVATE` (`CORE` 3, `MODMED` 87, `MASTER` 22, and the per-practice schemas).
**Prefer `PRIVATE`.** Two schemas carry things `PRIVATE` does not:

- `PUBLIC.SIGMA_STORAGE` (98) — `DDFE_*` next-available-appointment / calendar-slot access
  tables, `CAC_CURVE*` acquisition-cost curves, `APPT_REVENUE_XGBOOST*`, `MKT_CRM`,
  `MKT_NPS`, `DOCTOR_DAYS`, `DIALPAD_QUALITY_SURVEYS`.
- `PUBLIC.MASTER` (22) — `RVU_M`, `FEE_SCHEDULE_M`, `ICD10_CATEGORIES`, `BUSINESS_DAYS`,
  `PROVIDER_SLOTS_M`, `REVREC_*_M`, `V_COLUMN_DESCRIPTIONS`.

---

## RDS_P — 536 tables, 35 schemas · raw landing zone

One schema per practice holding the raw legacy EMR extract, plus external-system landings.
**Each practice schema exposes a `VW_<CODE>_CAP` view — this is how `PRIVATE.CORE.CAP` is
assembled.** Details and traps in `legacy_and_external.md`.

Practice schemas: `AAA` 39 · `AAS` 20 · `SCENT` 18 · `CAA` 16 (Coastal) · `ASA` 16 ·
`PIEDMONT` 15 · `SCENT_ALLMEDS_DISCRETE_EXTRACT` 15 (frozen 2024-07-22 med extract) ·
`CAAG` 13 · `AENT` 13 · `NWENT` 12 (`NEMR_*`) · `RESTON` 11 · `PIEDMONT_OLD` 11 ·
`ENTC` 10 · `NEGA` 10 · `ENTSG` 10 (`SEMR_*`) · `CS` 10 (Cornerstone) · `BB` 7 ·
`CAA_PRE_ACQUISITION` 4 · `KUHN` 3.

External / functional: `BD_SF_LEGACY` 141 (raw Salesforce objects) · `UTILITIES` 69
(`*_CLONE`, load process) · `RATER8` 21 (reviews; per-practice `R8_<CODE>_EXPORT`) ·
`SAGE_API` 16 · `GOOGLEANALYTICS` 8 · `DAILY_CHARGES` 7 · `DIALPAD` 6 · `SALESFORCE_BD` 6 ·
`MKT_CRM` 2 (`CRM_SURVEYS`, `MD_VISITS_FROM_CRM`) · `ZOCDOC`, `RCM` (`WAYSTAR_REPORTING`),
`HR` (`TALENT_DEVELOPMENT`), `MKT_NPS`, `LIINE`, `ASSORT`, `TRIZETTO` 1 each.

---

## IDM_P — 168 tables, 3 schemas · partly live

| Schema | # | Status |
|---|---|---|
| `TRANSACTIONS` | 114 | **DEPRECATED — do not use.** *(Dean, 2026-08-29: "deprecated for the most part … everything in it is pointless.")* The old integration layer: `EMR_CAP`, `EMR_APPT_DETAILS`, `EMR_AR_AGING(_WEEKLY)`, `EMR_DOC_COMP`, `CLAIM_STATUS_DETAILS`, and the **Kronos** family `KR_PAYROLL`, `KR_EMP_LEVEL_DETAILS`, `KR_HIRE_FIRE_DATES`, `KR_HRS_BY_LOC_JOB(_AMT)`, `KR_DAILY_PTO`. The Kronos data physically exists but is not trustworthy — **there is currently no usable payroll/hours source.** |
| `REFERENCEDATA` | 46 | **Live.** `NPI_MASTER_NPPES`, `RVU_MASTER_2023`, `INSURANCE_MAPPING_M`, `CALENDAR_MASTER`, `DATES_M`, `CPT_CYCLE_TIMES`, `PROVIDER_TYPE_M`, `SENTA_*_MAPPING_M`, `R8_*`, `PCM_EBITDA`, `PROVIDERS_IGNORE_LIST`, `KR_HEAD_COUNT`/`KR_LOCATIONS`/`KR_JOB_LISTING`. |
| `DIMENSIONS` | 8 | **Live.** `PROVIDER_MASTER_NEW`, `SENTA_PROVIDER_MASTER`, `SENTA_PROVIDERS`, `SENTA_FACILITY_M`, `SENTA_REFERRING_PROVIDER_M`, `SENTA_REF_PHYSICIANS_SF`, `CI_ACCESS`, `REF_PROVIDER_FILTERED`. |

`IDM_D` (202) is the **dev** mirror — do not use.

---

## Departmental marts — 403 tables — DEPRECATED, do not route here

`RCM_P` 88 · `FPA_P` 99 · `MKTG_P` 88 · `OPRTNS_P` 78 · `BSNSDEV_P` 50.

**Built for an earlier Sigma project. All five are dead. Ignore them.**
*(Confirmed by Dean, 2026-08-29: "all of the above OPRTNS_P etc are dead.")*

Recorded here only so the question "what is `RCM_P`?" has an answer. If one of these tables
turns up in an inherited query or an old workbook, that's a repoint candidate, not a source
to build on. Use `PRIVATE.<PRACTICE>` or `PRIVATE.CORE`.

Shape: each has an `ANALYTICS` and/or `SIGMA` schema plus the same ~11 per-practice schemas
(AAA, ASA, ADVANCED_ENT, RESTON_ENT, SCENT, ENTSG, PIEDMONT, NWENT, CAAG, ENTC) at 4–9
tables each. **The per-practice tables duplicate `PRIVATE.<PRACTICE>`** — `RCM_P.AAA`,
`MKTG_P.AAA`, `OPRTNS_P.AAA` and `PRIVATE.AAA` all list `AAA_ADJUSTMENTS`,
`AAA_APPOINTMENTS`, `AAA_AR_AGING`, `AAA_CHARGES`, … The `ANALYTICS` schemas hold
department-flavoured consolidated views (`VW_EMR_AR_AGING`, `CHARGES_CONSOLIDATED`,
`VW_EMR_CAP_REVREC`, `REFERRING_PROVIDER_MASTER`, `GA4_*`, `VW_R8_*`, `VW_SF_*`); the
`SIGMA` / `UPLOAD` schemas are Sigma artifacts.

Note some of these views wrap sources that *are* live — `MKTG_P.ANALYTICS.GA4_*` and
`VW_R8_*` sit over `RDS_P.GOOGLEANALYTICS` and `RDS_P.RATER8`. Go to the `RDS_P` source
directly rather than through the mart.

---

## Smaller databases

| Database | # | Purpose |
|---|---|---|
| `APPLICATIONS` | 114 | `SIGMA` 52 (incl. `ANTHROPIC_*` Claude/API usage and `CORTEX_*`), `SNOWFLAKE_ACCOUNT_USAGE` 15, `SALESFORCE` 14, `SNOWFLAKE_ORGANIZATION_USAGE` 9, `FIVETRAN_PLATFORM` 9, `FIVETRAN_LOG` 8, `HUBSPOT` 3, `GONG`/`CROSSBEAM`/`GOOGLE_ANALYTICS` 1. Platform telemetry and spend. |
| `SENTA_AI` | 21 | `PAYER_POLICY` 9 (policy RAG: `POLICY_CHUNKS`, `PAYER_POLICIES_RAW`, `DAILY_BRIEF_OUTBOX`, `PROVIDER_WATCHOUTS`, `CARC_CODES_IN_SCOPE`); `ML_CNS` 9 (`SMARTFILL_*` schedule config + recommendations); `LTV_PREDICT` 2; `REFERRAL_LINK` 1. |
| `BREVIUM` | 27 | `PDENT` 25 (`FINAL_*` — patient-reactivation vendor extract); `NWENT_HISTORICAL` 2. |
| `SIGMA_DT_SPINE` | 9 | Dynamic-table spine. `VERTEBRAE`: `CAP_BASE`, `CAP_METRICS`, `APPT_DETAILS_METRICS`. `GROWTH_CORE`: `B2B_SCORECARD_METRICS(_BOARD)`, `PL_COST_DEV_BASE`, `REF_PROV_GAP`. `GROWTH_SUPPORT` 2. |
| `R_ANALYTICS` | 12 | `DAILY_CHARGES` per practice. |
| `AUDIT_LOG` | 11 | `SIGMA_SHARED` 10 — Sigma documents, elements, users, teams, connections, scheduled notifications. Useful for auditing workbook sprawl. |
| `MONITOR` | 5 | CAP monitoring dynamic tables (rolling 12-month weekly practice charges/collections). |
| `FINANCE` | 37 | `FACTSET` 13 and `CORPORATE_FINANCE` 3 may be real; `PLUGS_ELECTRONICS_FINANCIALS`, `STOCKS`, `BITCOIN`, `LENDING_CLUB`, `FINANCE_HOL` are Snowflake demo sets. **[inferred]** |

## Out of scope

Dev mirrors `RDS_D` (248) and `IDM_D` (202). Sigma artifacts: `SENTALYTICS_P.SIGMA` (737,
100% `SIGDS_*`). Snowflake sample/marketplace: `SNOWFLAKE`, `BACKUPS`, `EXAMPLES`, `RETAIL`,
`GLOBAL_GOVERNMENT`, `SNOWFLAKE_WEATHER_ENVIRONMENT`, `US_OPEN_CENSUS_DATA…`, `SANDBOX`,
`FUN`, `CARDINAL`, `HEALTHCARE_LIFESCIENCES`, `U_S__ZIP_CODE_METADATA`.
