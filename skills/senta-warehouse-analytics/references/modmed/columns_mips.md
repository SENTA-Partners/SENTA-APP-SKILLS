# Column Dictionary: MIPS (76 columns)


## mips_score

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_score_id | mips_score table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| gpro_id | gpro table id | string | True | 20 |  |  |
| date_calculated | Date/time the scores were calculated. | timestamp | True |  |  |  |
| quality_measure_score | Quality measure points | double | True |  |  |  |
| quality_measure_bonus_score | Quality measure type bonus | double | True |  |  |  |
| quality_ehr_bonus_score | Quality measure EHR reporting bonus | double | True |  |  |  |
| quality_score | Total quality points | double | True |  |  |  |
| quality_percentage | Quality percentage of the overall MIPS score | double | True |  |  |  |
| cost_percentage | Cost percentage of the overall MIPS score | double | True |  |  |  |
| pi_base_score | PI base points | double | True |  |  |  |
| pi_performance_score | PI performance points | double | True |  |  |  |
| pi_bonus_score | PI bonus points | double | True |  |  |  |
| pi_score | Total PI points | double | True |  |  |  |
| pi_percentage | Promoting Interoperability (PI) percentage of the overall MIPS score | double | True |  |  |  |
| ia_medium_score | Points for medium weight IA activities | double | True |  |  |  |
| ia_high_score | Points for high weight IA activities | double | True |  |  |  |
| ia_score | Total IA points | double | True |  |  |  |
| ia_percentage | Improvement Activities (IA) percentage of the overall MIPS score | double | True |  |  |  |
| overall_percentage | MIPS overall score | double | True |  |  |  |
| npi | Provider NPI | int | True |  |  |  |
| start_date | Reporting start date | timestamp | True |  |  |  |
| end_date | Reporting end date | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_quality_measure_score

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_quality_measure_score_id | mips_quality_measure_score table id | string | False | 100 |  |  |
| mips_score_id | mips_score table id | string | False | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| gpro_id | gpro table id | string | True | 20 |  |  |
| quality_measure_id | quality_measure table id | int | True |  | Quality measure |  |
| rate_category | Category of the score for measures than have multiple rates reported (i.e. Measure 238) | string | True | 255 |  |  |
| met | Measure met count | int | True |  |  |  |
| not_met | Measure not met count | int | True |  |  |  |
| exclusions | Measure exclusion count | int | True |  |  |  |
| performance_rate | Performance rate | double | True |  |  |  |
| score | Earned score for the quality measure | double | True |  |  |  |
| reporting_year | Reporting year for the quality measure | int | True |  | Quality measure |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_pi_objective_score

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_pi_objective_score_id | mips_pi_objective_score table id | string | False | 20 |  |  |
| mips_score_id | mips_score table id | string | False | 20 |  |  |
| pi_objective_id | pi_objective table id | string | True | 20 | PI objective |  |
| score | Earned score for the objective | double | True |  |  |  |
| objective_type | Objective type for ACI. | string | True | 60 |  |  |
| numerator | Numerator | int | True |  |  |  |
| denominator | Denominator | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_quality_selection_ep

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_quality_selection_ep_id | mips_quality_selection_ep table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| quality_measure_id | quality_measure table id | int | True |  | Quality measure selected |  |
| reporting_year | Reporting year | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_quality_selection_gp

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_quality_selection_gp_id | mips_quality_selection_gp table id | string | False | 20 |  |  |
| gpro_id | gpro table id | string | False | 20 |  |  |
| quality_measure_id | quality_measure table id | int | True |  | Quality measure selected |  |
| reporting_year | Reporting year | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_pi_selection_ep

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_pi_selection_ep_id | mips_pi_selection_ep table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| pi_objective_id | pi_objective table id | string | True | 20 | PI objective |  |
| reporting_year | Reporting year | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_pi_selection_gp

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_pi_selection_gp_id | mips_pi_selection_gp table id | string | False | 20 |  |  |
| gpro_id | gpro table id | string | False | 20 |  |  |
| pi_objective_id | pi_objective table id | string | True | 20 | PI objective |  |
| reporting_year | Reporting year | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_ia_selection_ep

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_ia_selection_ep_id | mips_ia_selection_ep table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| improvement_activity_id | improvement_activity table id | string | True | 20 | Improvement activity selected for the provider |  |
| reporting_year | Reporting year | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## mips_ia_selection_gp

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| mips_ia_selection_gp_id | mips_ia_selection_gp table id | string | False | 20 |  |  |
| gpro_id | gpro table id | string | False | 20 |  |  |
| improvement_activity_id | improvement_activity table id | string | True | 20 | Improvement activity selected for the GPRO |  |
| reporting_year | Reporting year | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
