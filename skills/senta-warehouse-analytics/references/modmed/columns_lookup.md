# Column Dictionary: Lookup (30 columns)


## loinc

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| loinc | LOINC number | string | False | 10 |  |  |
| component | LOINC component | string | True | 255 |  |  |
| shortname | Short description | string | True | 100 |  |  |
| long_common_name | Long description | string | True | 255 |  |  |

## icd9

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| icd9 | ICD9 code | string | False | 25 |  |  |
| short_description | ICD9 short description | string | True | 255 |  |  |
| long_description | ICD10 long description | string | True | 255 |  |  |

## icd10

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| icd10 | ICD10 code | string | False | 25 |  |  |
| description | ICD10 description | string | True | 2000 |  |  |

## snomed

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| snomed | SNOMED code | string | False | 25 |  |  |
| name | SNOMED description | string | True | 255 |  |  |
| type | Type of SNOMED code | string | True | 50 |  |  |

## quality_measure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| quality_measure_id | quality_measure table id | int | False |  | Quality measure ID provided by CMS |  |
| nqf_id | National Quality Forum (NQF) ID | int | True |  |  |  |
| name | Name of the quality measure | string | True | 255 |  |  |
| domain | National Quality Strategy (NQS) domain | string | True | 255 |  |  |
| reporting_option | Reporting option | string | True | 30 | ALL BEST_GROUP BEST_PROCEDURE BEST CUSTOM EPISODIC LATEST NONE OLDEST |  |
| measure_type | Quality measure type | string | True | 50 |  |  |
| high_priority | If the measure is a high priority measure | boolean | True |  |  |  |

## pi_objective

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pi_objective_id | pi_objective table id | string | False | 30 | PI objective ID provided by CMS |  |
| name | Name of the PI objective | string | True | 100 |  |  |
| description | Description of the PI objective | string | True | 600 |  |  |
| required_for_base_score | If the objective is required for the base score | boolean | True |  |  |  |

## improvement_activity

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| improvement_activity_id | improvement_activity table id | string | False | 50 | Improvement activity ID provided by CMS |  |
| name | Name of the improvement activity | string | True | 255 |  |  |
| description | Description of the improvement activity | string | True | 3000 |  |  |
| subcategory | Subcategory of the improvement activity | string | True | 100 |  |  |
| weighting | Weighting of the improvement activity | string | True | 100 |  |  |
| bonus | If the improvement activity is a bonus activity | boolean | True |  |  |  |
| recommended | If the improvement activity is a recommended activity | boolean | True |  |  |  |
