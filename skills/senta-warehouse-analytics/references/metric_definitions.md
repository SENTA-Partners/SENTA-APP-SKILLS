# Metric definitions — the canonical rules for named metrics

Read this **before answering any named metric** (visits, charges, collections, RVUs, new
patients, referrals, budget vs actual, doc days). Measured and verified **2026-09-03**
against August 2026 data.

## The source

**`SIGMA_DT_SPINE.VERTEBRAE.CAP_METRICS`** — a dynamic table (1-hour lag, FULL refresh,
~47M rows) that is `CAP_BASE` plus budget targets, referral logic and doc-day actuals.
Sigma inode `baa0cdda-344c-46cb-b05a-b1a2b03d01a0`, on the `Sys Admin` connection.

**It agrees with `PRIVATE.CORE.CAP` exactly.** August 2026, `TRAN_TYPE = 'Charges'`:
144,711 lines / 98,392 distinct visits / **$48,222,016.02** — identical from both tables to
the cent. `CAP_METRICS` is CAP plus pre-computed metric columns, so routing a metric here
never changes a base number; it only saves re-deriving the flags.

Use it for named metrics. `PRIVATE.CORE.CAP` remains correct for everything else and stays
the routing answer for cross-cutover detail work.

## Read this before trusting the "single source of truth" label

`SIGMA_DT_SPINE.VERTEBRAE.CAP_METRICS_SEMANTICS` is a Snowflake semantic view over this
table, and the Cortex skill that owns it calls it *"the single source of truth for all
metrics, calculation logic, column descriptions, and business rules."*

**Two of its documented rules are wrong.** That label is a statement about governance, not a
measurement of correctness. The rules below are the corrected set — where they differ from
the semantic view, the difference is deliberate and the evidence is recorded.

If you are asked to reconcile a number against Cortex Analyst and it disagrees, **the
divergence is expected on new patients and referrals.** Say which rule you used and why
rather than assuming your own number is the broken one.

## The rules

`CAP_METRICS` is **charge-line grain**, so `COUNT(*)` is a count of billing lines and almost
never the metric anyone asked for. Count distinct visits unless you specifically want lines.

| Metric | Rule |
|---|---|
| Visits | `COUNT(DISTINCT VISIT_REF_ID) WHERE TRAN_TYPE = 'Charges'` |
| Charges | `SUM(AMOUNT) WHERE TRAN_TYPE = 'Charges'` |
| Collections | `SUM(COLLECTION_AMOUNT) WHERE TRAN_TYPE = 'Payments'` |
| RVUs | `SUM(RVUS) WHERE TRAN_TYPE = 'Charges'` |
| New patient visits | `COUNT(DISTINCT VISIT_REF_ID) WHERE IS_NEW_PATIENT AND TRAN_TYPE = 'Charges'` ← **corrected** |
| Referrals (provider) | `COUNT(DISTINCT VISIT_REF_ID) WHERE IS_NP_PROVIDER_REFERRAL AND TRAN_TYPE = 'Charges'` ← **corrected** |
| Referrals (source) | `COUNT(DISTINCT VISIT_REF_ID) WHERE IS_NP_SOURCE_REFERRAL AND TRAN_TYPE = 'Charges'` ← **corrected** |
| Provider visits, budget | `SUM(RECORD_PORTION_OF_PROVIDER_VISITS_BUDGET)` vs the Visits rule above as actual |
| Svc-category charges, budget | `SUM(RECORD_PORTION_OF_SVC_CATEGORY_CHARGE_BUDGET)` vs the Charges rule as actual |
| Svc-category visits, budget | `SUM(RECORD_PORTION_OF_SVC_CATEGORY_VISITS_BUDGET)` vs the Visits rule as actual |
| Doc days | `SUM(RECORD_PORTION_OF_DOC_DAYS_BUDGET)` vs `SUM(RECORD_PORTION_OF_DOC_DAYS_ACTUAL)` |

The `RECORD_PORTION_OF_*` columns are a budget figure pre-divided across the rows it spans
(`value / COUNT(*) OVER partition`), so they **must be summed, never averaged or counted** —
summing reconstitutes the original budget.

## Why new patients was corrected

The semantic view documents `COUNT(*) WHERE IS_NEW_PATIENT AND TRAN_TYPE = 'Charges'`.
August 2026 gives **12,844** under that rule against **12,683** distinct visits — a **+161**
overstatement, ranging from 0 to 6.5% by practice.

**This is not a definition disagreement.** `IS_NEW_PATIENT` is *exactly*
`SVC_CATEGORY = 'New Patient'` — 12,844 rows each way, and **zero rows on either side of the
symmetric difference**. The flag is sound. `COUNT(*)` is the defect, and it inflates two
different ways:

1. **Real multi-line visits.** A visit carrying 2–3 New Patient charge lines counts 2–3
   times. One visit is one new patient.
2. **A keyless row batch at AAA**, which is 129 of the 161 on its own. Those 129 lines share
   a **NULL `VISIT_REF_ID`**, have **zero distinct `PAT_REF_ID`** (null as well), and are all
   stamped `2026-08-31` — the last day of the month. AAA's other 1,972 lines are a clean 1:1
   with 1,972 distinct patients. Rows carrying no patient key are not 129 new patients; they
   look like an eCW month-end load artifact. `COUNT(DISTINCT VISIT_REF_ID)` drops them
   silently and correctly, because SQL does not count nulls. `COUNT(*)` counts them.

August 2026 by practice — the two rules, so you can recognise the gap:

| Practice | Correct | Semantic view | Δ |
|---|---|---|---|
| AAA | 1,972 | 2,101 | +129 |
| Advanced ENT | 2,939 | 2,945 | +6 |
| ASA | 241 | 247 | +6 |
| ENTC | 934 | 939 | +5 |
| NEGA | 910 | 915 | +5 |
| NWENT | 1,047 | 1,052 | +5 |
| SCENT | 1,265 | 1,269 | +4 |
| CAAG | 512 | 513 | +1 |
| AAS · Coastal · Cornerstone · ENTSG · Piedmont · Reston | *agree* | *agree* | 0 |
| **Total** | **12,683** | **12,844** | **+161** |

**Six of fourteen practices agree under both rules**, so a single-practice spot check will
not surface this. Check AAA, or check the group.

## Why referrals was corrected — this one is 4.2×

The semantic view documents `COUNT(*) WHERE IS_NP_SOURCE_REFERRAL` with **no `TRAN_TYPE`
filter at all**. August 2026:

| | Charge rows | Charge visits | Payment rows | Payment visits |
|---|---|---|---|---|
| `IS_NP_SOURCE_REFERRAL` | 2,192 | **1,049** | 2,169 | 830 |
| `IS_NP_PROVIDER_REFERRAL` | 5,487 | **5,478** | 0 | 0 |

So the documented source-referral rule returns **4,361** where the answer is **1,049** — a
**4.2× overstatement**, compounding two errors: it counts payment rows as referrals *and*
double-counts multi-line visits. A referral is an event, and posting a payment against it
later does not create a second one.

Provider referrals are barely affected (5,487 vs 5,478) because that flag is already set on
roughly one row per visit and never on payment rows. **Note the two flags are placed
inconsistently** — source-referral sits on ~2 charge lines per visit, provider-referral on
~1 — which is worth raising upstream rather than working around indefinitely.

## Gotchas

- **`VISIT_REF_ID` was verified globally unique** for August 2026 — zero ids appeared at more
  than one `LOCATION_NAME` — so a global `COUNT(DISTINCT …)` is safe. This is *not* true of
  `PAT_REF_ID`, which is only unique **within** a practice. Group by practice for
  patient-grain counts.
- **Nulls in the count key are load-bearing.** The AAA batch above is the reason. When a
  distinct-visit count and a row count disagree, check for a null key before assuming
  duplicates.
- **`RVUS` is per line, not per unit.** Do not multiply by `UNITS`.
- **`TRAN_TYPE` is null on some rows.** `'Charges'` and `'Payments'` do not partition the
  table; filter positively for the one you want rather than negating the other.
- **`SVC_CATEGORY = 'Surgery'` is not surgery** and `SVC_LINE` disagrees with it — see
  `senta_core.md` before using either for a surgical metric.
- **AAA is legacy eCW throughout** and posts no charges to ModMed, so any ModMed-side CPT
  metric excludes it entirely. In `CAP_METRICS` it is present.
- The new-patient definition here (`SVC_CATEGORY`) is **not** the ModMed CPT 99202–99205
  definition used for provider-level new-patient scorecards. They are different metrics
  answering different questions; say which one you used.

## If you need the full semantic-view documentation

The column descriptions and metric expressions live in the semantic view's DDL, which is
**not reachable from Sigma** — verified 2026-09-03:

- Path-qualified refs fail (`FROM "DB"."SCHEMA"."TABLE"` → *"Table not found"*). Sigma only
  resolves `FROM "connection"."<inodeId>"`.
- **Semantic views are not indexed as Sigma inodes at all**, so there is no inode to use.
- `GET_DDL` is rejected (*"Unknown function get_ddl"*) — Sigma canonicalizes to its own
  dialect.

Getting it requires a human in Snowsight:

```sql
SHOW SEMANTIC VIEWS IN ACCOUNT;
DESC SEMANTIC VIEW SIGMA_DT_SPINE.VERTEBRAE.CAP_METRICS_SEMANTICS;
```

The second returns a row per object with `object_kind` (METRIC, DERIVED_METRIC, DIMENSION,
FACT), `object_name`, `parent_entity`, `property` and `property_value`. Ask for it rather
than guessing at a definition that is not in the table above.
