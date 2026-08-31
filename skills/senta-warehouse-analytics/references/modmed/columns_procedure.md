# Column Dictionary: Procedure (45 columns)


## procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_id | procedure table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| procedure_alias | Internal reference alias for the procedure. Multiple procedure_alias may share the same procedure_name. | string | True | 255 | See static_procedure.procedure_alias |  |
| procedure_name | Name of the procedure that gets rendered in the note. | string | True | 255 | See static_procedure.procedure_name |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## procedure_body_location

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_body_location_id | procedure_body_location table id | string | False | 20 |  |  |
| procedure_id | procedure table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| body_part | Specific body part | string | True | 255 | See static_body_location.body_part |  |
| simple_description | Simple body location for procedure | string | True | -1 | See static_body_location.exam_simple_description |  |
| detail_description | Detailed body location for procedure | string | True | 255 | See static_body_location.exam_detail_description |  |
| zone | High-level body zone | string | True | 255 | See static_body_location.zone |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## procedure_metadata

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_metadata_id | procedure_metadata table id | string | False | 25 |  |  |
| procedure_body_location_id | procedure_body_location table id | string | True | 20 | Only one of procedure_body_location_id or procedure_id will be non-null in each row. |  |
| procedure_id | procedure table id | string | False | 20 | Only one of procedure_body_location_id or procedure_id will be non-null in each row. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| variable | Variable name for the metadata item. | string | True | 50 | See static_procedure_metadata.variable |  |
| question_text | Question displayed to the user | string | True | 255 | See static_procedure_metadata.question_text |  |
| type | Data type of the metadata item | string | True | 20 | See static_procedure_metadata.type |  |
| value | Metadata response value for single-select or text input items. | string | True | 12000 | See static_procedure_metadata_selection.value |  |
| range_value | Numeric response value. NOTE: many items default to a value of 0 | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## procedure_metadata_selection

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_metadata_selection_id | procedure_metadata_selection table id | string | False | 20 |  |  |
| procedure_metadata_id | procedure_metadata table id | string | False | 25 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| value | Metadata response value. | string | True | 2000 | See static_procedure_metadata_selection.value |  |
| text_value | Text response value. | string | True | 12000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## procedure_metadata_nested_value

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_metadata_nested_value_id | procedure_metadata_nested_value table id | string | False | 20 |  |  |
| procedure_metadata_selection_id | procedure_metadata_value table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| type | Data type of the metadata item. | string | True | 25 | CPT GCODE GCODE_MOD UCI |  |
| code | Metadata code | string | True | 80 |  |  |
| description | Metadata description | string | True | 10000 |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## procedure_mips_quality

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_mips_quality_id | procedure_mips_quality table id | string | False | 25 |  |  |
| procedure_id | procedure table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| tab_label | Tab (grouping) the question is displayed in | string | True | 50 | See static_procedure_metadata.tab_label |  |
| question_text | Question displayed to the user | string | True | 255 | See static_procedure_metadata.question_text |  |
| value | Response value. | string | True | 2000 | See static_procedure_metadata_selection.value |  |
| text_value | Text response value. | string | True | 12000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
