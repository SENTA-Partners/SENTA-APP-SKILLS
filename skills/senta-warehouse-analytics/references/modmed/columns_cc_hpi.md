# Column Dictionary: CC/HPI (115 columns)


## hpi_response

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_response_id | hpi_response table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| body_detail_level | Detail level of the associated body location selection(s). | string | True | 20 | simple: use simple_description column detailed: use detail_description_column zone: use zone column generalized: don't consider body location (condition is "body throughout") |  |
| chief_complaint | Chief Complaint title | string | True | 255 | See static_hpi_response.chief_complaint |  |
| context | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| duration | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| location | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| modifying_factors | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| quality | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| severity | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| signs_and_symptoms | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| timing | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_response_body_location

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_response_body_location_id | hpi_response_body_location table id | string | False | 20 |  |  |
| hpi_response_id | hpi_response table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| body_part | Specific body part | string | True | 255 | See static_body_location.body_part |  |
| simple_description | Simple body location for CC/HPI | string | True | 255 | See static_body_location.hpi_simple_description |  |
| detail_description | Detailed body location for CC/HPI | string | True | 255 | See static_body_location.hpi_detail_description |  |
| zone | High-level body zone | string | True | 255 | See static_body_location.zone |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_response_metadata

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_response_metadata_id | hpi_response_metadata table id. | string | False | 33 |  |  |
| hpi_response_id | hpi_response table id | string | False | 20 |  |  |
| parent_hpi_option_value_id | hpi_option_value table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| variable | Metadata variable name. Chief complaints may re-use variable names. | string | True | 255 | See static_hpi_response_metadata.variable |  |
| question_text | Question displayed to the user | string | True | 1000 | See static_hpi_response_metadata.question_text |  |
| type | Data type of the metadata item | string | True | 255 | See static_hpi_response_metadata.type |  |
| component | HPI component the metadata item covers | string | True | 255 | See static_hpi_response_metadata.component |  |
| value | Metadata response value for single-select or text input items. | string | True | 20000 | See static_hpi_response_metadata_selection.value |  |
| body_detail_level | Indicates the level of detail used to inform the HPI. | string | True | 100 | detailed general generalized simple zone none |  |
| mini_madlib | Details related to bundle_key/option_value. | string | True | -1 |  |  |
| position | Order of the questions in the 'Provide Details' form. | int | True |  |  |  |
| preserve_order | Preserve order | boolean | True |  |  |  |
| duration_days | Metadata response for duration items. All duration_* columns are used together to record how long the patient has had the condition he/she is presenting for | int | True |  | -1 indicates an indeterminate amount of time i.e. "Patient has had condition for days" |  |
| duration_months | Metadata response for duration items. All duration_* columns are used together to record how long the patient has had the condition he/she is presenting for | int | True |  | -1 indicates an indeterminate amount of time i.e. "Patient has had condition for months" |  |
| duration_weeks | Metadata response for duration items. All duration_* columns are used together to record how long the patient has had the condition he/she is presenting for | int | True |  | -1 indicates an indeterminate amount of time i.e. "Patient has had condition for weeks" |  |
| duration_years | Metadata response for duration items. All duration_* columns are used together to record how long the patient has had the condition he/she is presenting for | int | True |  | -1 indicates an indeterminate amount of time i.e. "Patient has had condition for years" |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_response_metadata_selection

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_response_metadata_selection_id | hpi_response_metadata_selection table id | string | False | 20 |  |  |
| hpi_response_metadata_id | hpi_response_metadata id | string | False | 33 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| value | Metadata response value | string | True | 20000 | See static_hpi_response_metadata_selection.value |  |
| text_value | Text response value | string | True | 20000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_follow_up

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_follow_up_id | hpi_follow_up table id | string | False | 20 |  |  |
| diagnosis_referenced_id | diagnosis table id | string | True | 20 | Diagnosis the patient is following up on. |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| follow_up_reason | What the patient is presenting/following up for | string | True | 50 | See Appendix H CRYOTHERAPY, FOLLOW_UP_EVAL, HIGHRISK_MONITOR, LASER, OTHER |  |
| treatment_compliant | The treatment was followed as directed? | boolean | True |  |  |  |
| context | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| duration | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| location | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| modifying_factors | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| quality | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| severity | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| signs_and_symptoms | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| timing | True if the specific HPI component/element was covered | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_follow_up_value

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_follow_up_value_id | hpi_follow_up_value table id | string | False | 20 |  |  |
| hpi_follow_up_id | hpi_follow_up table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| question | Question displayed to the user | string | True | 100 | MODIFYING_FACTORS QUALITY SIGNS_AND_SYMPTOMS TIMING SEVERITY DURATION FOLLOW_UP_REASON CHANGE CAUSE CONDITION_STATUS CONTEXT |  |
| value | Response selected | string | True | 255 | ~300 unique values. Examples include: EPISODIC, SHARP, IMPROVED_WITH_REST |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_follow_up_measurement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_follow_up_measurement_id | hpi_follow_up_measurement table id | string | False | 20 |  |  |
| hpi_follow_up_id | hpi_follow_up table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| variable | Variable name for the measurement. Variable names may be re-used across different diagnoses, and multiple variables may have the same title and/or question_text. | string | True | 256 | See static_diagnosis_measurement.variable |  |
| title | Name of the measurement. | string | True | 256 | See static_diagnosis_measurement.title |  |
| question_text | Question displayed to the user. | string | True | 256 | See static_diagnosis_measurement.hpi_question_text |  |
| type | Data type of the measurement | string | True | 256 | See static_diagnosis_measurement.type |  |
| value | Value of the measurement | double | True |  |  |  |
| value_title | Title associated with the value, if applicable | string | True | 256 | See static_diagnosis_measurement_value.title |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## hpi_option

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_option_id | hpi_option table id | string | False | 20 |  |  |
| hpi_response_id | hpi_response table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| hpi_variable | Type of question asked. | string | True | 255 |  |  |
| hpi_variable_question_text | Text of the question asked during assessment. | string | True | 1000 |  |  |
| bundle_key | Detailed value associated to the hpi_option selected. Formatted as code key. | string | True | 255 |  |  |
| option_type | Type of field used in the form. | string | True | 50 |  |  |
| tab_label | Tab label | string | True | 100 | Aggravating Associated Symptoms Case Info Duration Employer History Injury Date Occupation Past_Treatments Pertinent History Pertinent Negatives Referral Source Referring Timeline Timing Treatment Treatments Work Date |  |
| exclude_gender | Whether the question should exclude a gender from answering it or not. Indicates the excluded gender. | string | True | 25 |  |  |
| position | Position of the question in the form. | int | True |  |  |  |
| question_level | Question level. | int | True |  |  |  |
| range_start | Lowest boundary of the range. | double | True |  |  |  |
| range_end | Highest boundary of the range. | double | True |  |  |  |
| range_default | Default value for the range. | double | True |  |  |  |
| range_increment | Increment steps for the range value. | double | True |  |  |  |
| preserve_order | Preserve order. | boolean | True |  |  |  |
| visible | Visible. | boolean | True |  |  |  |
| required | Indicates if the question is mandatory or not. | boolean | True |  |  |  |
| allow_none | Indicates if the question accepts answer 'does not apply' or not. | boolean | True |  |  |  |
| allow_other | Indicates if the question accepts answer 'other' or not. | boolean | True |  |  |  |
| indicates_chronic_condition | Indicates if the question is related to a chronic condition or not. | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## hpi_option_value

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| hpi_option_value_id | hpi_option_value table id | string | False | 20 |  |  |
| hpi_option_id | hpi_option table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| option_value | Detailed value associated to the hpi_option selected. Formatted for presentation. | string | True | -1 |  |  |
| diagnosis_type | Diagnosis type. | string | True | 100 |  |  |
| bundle_key | Detailed value associated to the hpi_option selected. Formatted as code key. | string | True | 255 |  |  |
| mini_madlib | Details related to bundle_key/option_value. | string | True | -1 |  |  |
| exclude_gender | Whether the option should exclude a gender from answering it or not. Indicates the excluded gender. | string | True | 10 |  |  |
| position | Position of the detailed option, relative to the question/hpi_option. | int | True |  |  |  |
| exclude_component | Exclude component | boolean | True |  |  |  |
| visible | Visible. | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |
