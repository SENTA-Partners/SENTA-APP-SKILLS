# Practice registry

The 13–14 practices, their codes across systems, ModMed firm ids, and EMR history.
Codes differ between the warehouse, Sigma team names, and data values — that mismatch is a
recurring source of zero-row queries.

## ModMed firm ids

*Verified 2026-08-28.*

| Practice | firm_id |
|---|---|
| Advanced ENT (ADVENT) | 113887 |
| Asthma & Allergy Specialists (AAS) | 118589 |
| ASA | 118592 |
| CAAG | 118594 |
| Coastal Allergy & Asthma (CAA) | 118586 |
| Cornerstone ENT (CS) | 110414 |
| ENTC | 118584 |
| ENTSG | 118587 |
| NEGA | 109758 |
| NWENT | 118575 |
| Piedmont ENT (PDENT) | 118578 |
| Reston ENT | 110573 |
| SCENT | 118428 |

**AAA has no ModMed firm_id — it never converted** (see the cutover table below). That is 13
firm ids for 14 practices in `CAP.LOCATION_NAME`, not an omission.

ModMed ids elsewhere are `<number>-pod<N>` shaped (`16681801-pod45`). `firm_id` in the claim
worklist context appears as `508-pod45`-shaped.

## Code variants — the zero-row trap

| Practice | `RDS_P` schema / prefix | Warehouse schema | `LOCATION_NAME` value | Sigma team |
|---|---|---|---|---|
| Advanced ENT | `AENT` / `AENT_*` | `ADVANCED_ENT` | `Advanced ENT` | `ADVENTA` |
| Coastal Allergy & Asthma | `CAA` / `CAA_*` | — | `Coastal Allergy & Asthma` | `CAA` |
| Asthma & Allergy Specialists | `AAS` / `AAS_*` | `AAS` | — | `AAS` |
| NWENT | `NWENT` / **`NEMR_*`** | `NWENT` | `NWENT` | `NWENT` |
| ENTSG | `ENTSG` / **`SEMR_*`** | `ENTSG` | | `ENTSG` |
| Piedmont ENT | `PIEDMONT` / **`NG_*`** (NextGen) | `PIEDMONT` / `PDENT` | | `PIEDMONT ENT` |
| Cornerstone | `CS` / `CS_*` | — | | — |
| Reston ENT | `RESTON` / `RESTON_*` | `RESTON_ENT` | `Reston ENT` | `RESTON ENT` |
| ASA | `ASA` | `ASA` | `ASA` | `ASA` |
| SCENT | `SCENT` | `SCENT` | | `SCENT` |
| CAAG | `CAAG` | `CAAG` | | `CAAG` |
| ENTC | `ENTC` | `ENTC` | | `ENTC` |
| AAA | `AAA` | `AAA` | | `AAA` |
| NEGA | `NEGA` | — | | `NEGA` |
| "BB" | `BB` / `BB_*` | — | | — |

Sigma team names do **not** match data values (`ADVENTA` vs `Advanced ENT`, `CAA` vs
`Coastal Allergy & Asthma`, `AAS` vs `Asthma & Allergy Specialists`), so
`CurrentUserInTeam` is not a shortcut for row-level security.

## EMR history and cutovers

**Derived 2026-08-29** from `PRIVATE.CORE.CAP` charge lines by service date, comparing
`LEGACY_DESIGNATION` volume per practice per month. Reproducible — see the method note at
the end. The two independently-known dates (CAAG, Coastal) both fall out correctly.

> **A cutover is usually a window, not a date.** Six of the ten converting practices ran a
> phased rollout with *both* systems carrying real volume for 4–16 months. Treating the
> conversion as a single date and switching sources on it will undercount for the whole ramp.
> **When a window touches a transition period, use `PRIVATE.CORE.CAP` — never one side.**

`SOURCE_DESCRIPTION = 'DDFE'` identifies ModMed rows; anything else is a legacy system.

| Practice | Legacy system(s) | ModMed volume starts | Legacy effectively ends | Pattern |
|---|---|---|---|---|
| **AAA** | eCW (`AAA eCW`, `BB eCW`) | **never** | still live | **Never converted.** 2.46M legacy lines, zero ModMed. No ModMed firm_id. |
| **Cornerstone ENT** | — | ≤ 2021-01 | n/a | ModMed-native for the whole CAP window |
| **NEGA** | — | ≤ 2021-01 | n/a | ModMed-native |
| **Reston ENT** | — | ≤ 2021-01 | n/a | ModMed-native |
| **Advanced ENT** | Greenway | 2022-07 | 2022-07 *(strays to 2022-12)* | big bang — 90% ModMed in month one |
| **Piedmont ENT** | NextGen (+ Old NextGen) | 2023-05 | 2024-09 *(strays to 2025-02)* | **16-month phased ramp** |
| **ENTSG** | Azalea | 2023-11 | 2024-10 | **12-month phased ramp** |
| **SCENT** | AllMeds + SIS | 2023-10 | 2024-07 *(last 2024-08)* | **10-month phased ramp** |
| **ASA** | Meditab | 2024-05 | 2024-12 | **8-month phased ramp** |
| **Asthma & Allergy Specialists** | Agastha | 2024-05 | 2024-10 | **6-month phased ramp** |
| **ENTC** | Greenway | 2024-07 | 2024-10 | **4-month phased ramp** |
| **NWENT** | Epic | 2024-08 | 2024-09 *(last 2024-11)* | big bang |
| **CAAG** | Athena | 2024-12 | 2024-12 | big bang — 34%/66% split in the single month |
| **Coastal Allergy & Asthma** | Coastal EMR OLD → NEW | 2026-01 | 2026-01 | big bang |

### The ramp practices in detail

Percent of monthly charge lines still on the legacy system:

- **Piedmont ENT** — 97.5% (May 2023) → 94.2% (Apr 2024) → 87.4% (Aug 2024) → **50.3%
  (Sep 2024)** → done. `Old Nextgen EMR DB` is a third source behind `Nextgen EMR DB`.
- **ENTSG** — 97.5% (Nov 2023) → 92.9% (Feb 2024) → 89.2% (Sep 2024) → **73.0% (Oct 2024)**.
- **SCENT** — 97.2% (Oct 2023) → 90.5% (Mar 2024) → 82.6% (Jun 2024) → **57.3% (Jul 2024)**.
  Two legacy systems in parallel (`Allmeds EMR`, `SIS EMR`).
- **ASA** — 97.6% (May 2024) → 85.1% (Nov 2024) → **33.8% (Dec 2024)**.
- **AAS** — 97.9% (May 2024) → 92.0% (Sep 2024) → **78.5% (Oct 2024)**, completing Nov.
- **ENTC** — 97.8% (Jul 2024) → 95.9% (Sep 2024) → **79.4% (Oct 2024)**, completing Nov.

### Other notes

- **Do not use `MIN(SERVICE_DT) WHERE LEGACY_DESIGNATION = 'MODMED'` to find a cutover.**
  Stray ModMed rows predate go-live at nearly every practice — several show a first ModMed
  service date in 2021. Threshold against that practice's peak monthly volume instead.
- CAAG: 2024 spans both systems and 666 patients appear in both.
- Coastal: January 2026 draws from both but is **non-overlapping by service date — no double
  counting**. Legacy lineage is `Coastal EMR OLD` (through ~Jul 2024) then `Coastal EMR NEW`.
- **"BB" is not a separate practice** — `BB eCW TransactionsQA1` sits under AAA, matching the
  `RDS_P.BB` schema.
- `RDS_P.PIEDMONT_OLD` and `RDS_P.CAA_PRE_ACQUISITION` hold pre-acquisition history.
- These dates reflect when **billing** moved, from charge service dates. Clinical go-live may
  lead or lag by days. Treat month-level as solid, day-level as approximate.

**Whenever a question spans a transition window, use `PRIVATE.CORE.CAP`.** See `senta_core.md`.

### Method (to re-derive)

Group `PRIVATE.CORE.CAP` charge lines (`TRAN_TYPE = 'Charges'`) by `LOCATION_NAME` ×
`DATE_TRUNC('month', SERVICE_DT)` × `LEGACY_DESIGNATION`. Per practice take the peak monthly
volume of each designation; a month "counts" for a designation at ≥2–5% of that peak. The
transition window runs from the first counting ModMed month to the last counting legacy
month. Guard the peak with `> 0` or practices that never converted return nonsense.

## Practice-specific notes worth knowing

- **Reston ENT has zero rows in `PRIVATE.CORE.APPT_DETAILS`** — use
  `PRIVATE.MODMED.APPOINTMENT`. It is also the smallest practice by AR (~$443k of ~$24M).
- **Advanced ENT is the largest** — 572,756 rows in `PATIENT_M`.
- **AAA and Coastal capture zero referring NPIs**, so referral/leakage analysis can't be done
  for them at all.
- **Reston ENT (VA) and ASA (TX) are not covered by the SCP claims feed.**
- Allergy practices (AAA, CAAG, Coastal, AAS, SCENT) bill high-unit CPTs — 95004, 95165,
  95044 — where a unit is a dose/test, not an encounter. Always report units and line counts
  separately, and remember CAP's `RVUS` is per line.
- `SCENT` has a firm-specific carve-out in the surgery-order workbook: `firm_global_id =
  118428` counts PENDING appointments as complete.
