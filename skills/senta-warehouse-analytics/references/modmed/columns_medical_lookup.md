# Column Dictionary: Medical Lookup (129 columns)


## static_body_location

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_body_location_id | static_body_location table id | int | False |  |  |  |
| body_part | Specific body part | string | True | 255 |  |  |
| hpi_simple_description | Simple body location for CC/HPI | string | True | 255 |  |  |
| hpi_detail_description | Detailed body location for CC/HPI | string | True | 255 |  |  |
| exam_simple_description | Simple body location for diagnosis/procedure | string | True | -1 |  |  |
| exam_detail_description | Detailed body location for diagnosis/procedure | string | True | 255 |  |  |
| zone | High-level body zone | string | True | 255 |  |  |

## static_hpi_response

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_hpi_response_id | static_hpi_response table id | int | False |  |  |  |
| chief_complaint | Chief Complaint title | string | True | 255 |  |  |
| telemedicine_title | Telemedicine title for the chief complaint | string | True | 255 | NULL if complaint is not a telemedicine complaint |  |
| medical_domain | Medical domain the chief complaint is part of. | string | True | 255 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY PRIMARY_CARE RHEUMATOLOGY UROLOGY |  |
| archived | If chief complaint has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_hpi_response_metadata

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_hpi_response_metadata_id | static_hpi_response_metadata table id | int | False |  |  |  |
| static_hpi_response_id | static_hpi_response table id | int | False |  |  |  |
| required | If the variable is required to be collected in each chief complaint. | boolean | True |  |  |  |
| variable | Metadata variable name. Chief complaints may re-use variable names. | string | True | 255 |  |  |
| question_text | Question displayed to the user | string | True | 1000 |  |  |
| type | Data type of the metadata item | string | True | 255 |  |  |
| component | HPI component the metadata item covers | string | True | 255 |  |  |
| archived | If variable has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_hpi_response_metadata_selection

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_hpi_response_metadata_selection_id | static_hpi_response_metadata_selection table id | int | False |  |  |  |
| static_hpi_response_metadata_id | static_hpi_response_metadata id | int | False |  |  |  |
| value | Metadata response value | string | True | 4000 |  |  |
| archived | If value has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_exam_set

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_exam_set_id | static_exam_set table id | int | False |  |  |  |
| exam_set | Name of the exam set | string | True | 255 |  |  |
| medical_domain | Medical domain the exam set is part of. | string | True | 255 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY PRIMARY_CARE RHEUMATOLOGY UROLOGY |  |
| archived | If exam has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_exam_element

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_exam_element_id | static_exam_element table id | int | False |  |  |  |
| element | Exam element | string | True | 255 |  |  |
| system | Bodily system the element is a part of | string | True | 255 |  |  |
| tab_label | Tab (grouping) the exam element is displayed in | string | True | 50 |  |  |
| archived | If element has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_exam_set_element

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_exam_set_element_id | static_exam_set_element table id | int | False |  |  |  |
| static_exam_set_id | static_exam_set table id | int | False |  |  |  |
| static_exam_element_id | static_exam_element table id | int | False |  |  |  |
| default_checked | If element is checked by default. | boolean | True |  |  |  |
| archived | If element has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_exam_element_metadata

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_exam_element_metadata_id | static_exam_element_metadata table id | int | False |  |  |  |
| static_exam_element_id | static_exam_element table id | int | False |  |  |  |
| variable | Variable name for the metadata item. Variables are defined and entered for each exam element. | string | True | 50 |  |  |
| question_text | Question displayed to the user | string | True | 255 |  |  |
| type | Data type of the metadata item | string | True | 20 |  |  |
| range_start | Starting value for range (numeric) questions | double | True |  |  |  |
| range_end | Ending value for range (numeric) questions | double | True |  |  |  |
| range_increment | Increment value for range (numeric) questions | double | True |  |  |  |
| range_default | Default value for range (numeric) questions | double | True |  |  |  |
| text_default | Default value for text questions | string | True | 4000 |  |  |
| archived | If variable has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_exam_element_metadata_selection

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_exam_element_metadata_selection_id | static_exam_element_metadata_selection table id | int | False |  |  |  |
| static_exam_element_metadata_id | static_exam_element_metadata table id | int | False |  |  |  |
| value | Metadata response value | string | True | 255 |  |  |
| default | If value is selected by default. | boolean | True |  |  |  |
| archived | If value has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_diagnosis_id | static_diagnosis table id | int | False |  |  |  |
| diagnosis_name | ModMed clinical diagnosis names, not necessarily related to ICD codes. May be more or less detailed than an ICD code. | string | True | 255 |  |  |
| diagnosis_type | High-level diagnosis type | string | True | 100 |  |  |
| icd9 | Internal reference for searching diagnoses, NOT sent for billing. May be partial/base codes not valid for billing. | string | True | 50 |  |  |
| icd10 | Internal reference for searching diagnoses, NOT sent for billing. May be partial/base codes not valid for billing. | string | True | 25 |  |  |
| medical_domain | Medical domain the diagnosis is part of. | string | True | 255 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY PRIMARY_CARE RHEUMATOLOGY UROLOGY |  |
| archived | If diagnosis has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_diagnosis_measurement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_diagnosis_measurement_id | static_diagnosis_measurement table id | int | False |  |  |  |
| static_diagnosis_id | static_diagnosis table id | int | False |  |  |  |
| variable | Variable name for the measurement. Variable names may be re-used across different diagnoses, and multiple variables may have the same title and/or question_text. | string | True | 256 |  |  |
| title | Name of the measurement. | string | True | 256 |  |  |
| hpi_question_text | Question displayed to the user for CC/HPI follow up measurement. | string | True | 256 |  |  |
| exam_question_text | Question displayed to the user for diagnosis measurement. | string | True | 256 |  |  |
| type | Data type of the measurement | string | True | 256 |  |  |
| range_start | Starting value for the measurement | double | True |  |  |  |
| range_end | Ending value for the measurement | double | True |  |  |  |
| range_increment | Increment value for the measurement | double | True |  |  |  |
| range_default | Default value for the measurement | double | True |  |  |  |
| hpi | If the measurement is shown for CC/HPI follow up measurements | boolean | True |  |  |  |
| diagnosis | If the measurement is shown for diagnosis measurements | boolean | True |  |  |  |
| archived | If measurement has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_diagnosis_measurement_title

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_diagnosis_measurement_title_id | static_diagnosis_measurement_title table id | int | False |  |  |  |
| static_diagnosis_measurement_id | static_diagnosis_measurement table id | int | False |  |  |  |
| value | Measurement value | double | True |  |  |  |
| value_title | Title associated with the value. | string | True | 256 |  |  |

## static_diagnosis_morphology

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_diagnosis_morphology_id | static_diagnosis_morphology table id | int | False |  |  |  |
| static_diagnosis_id | static_diagnosis table id | int | False |  |  |  |
| morphology | Morphology associated with the diagnosis. Users can add custom morphologies; these are not included here. | string | True | 10000 |  |  |
| archived | If morphology has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_procedure_id | static_procedure table id | int | False |  |  |  |
| procedure_alias | Internal reference alias for the procedure. Multiple procedure_alias may share the same procedure_name. | string | True | 255 |  |  |
| procedure_name | Name of the procedure that gets rendered in the note. | string | True | 255 |  |  |
| search_plan_name | Name of the procedure that gets rendered in the exam search list. | string | True | 255 |  |  |
| medical_domain | Medical domain the chief complaint is part of. | string | True | 255 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY PRIMARY_CARE RHEUMATOLOGY UROLOGY |  |
| archived | If procedure has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_procedure_metadata

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_procedure_metadata_id | static_procedure_metadata table id | int | False |  |  |  |
| static_procedure_id | static_procedure table id | int | False |  |  |  |
| per_body_location | If the metadata variable is recorded for each body location, rather than the procedure as a whole. If true, the corresponding procedure_metadata.procedure_body_location_id will not non-null. | boolean | True |  |  |  |
| required | If the metadata variable is required to be recorded for each procedure. | boolean | True |  |  |  |
| variable | Variable name for the metadata item. | string | True | 50 |  |  |
| tab_label | Tab (grouping) the metadata variable is displayed in | string | True | 50 |  |  |
| question_text | Question displayed to the user | string | True | 255 |  |  |
| type | Data type of the metadata item | string | True | 20 |  |  |
| range_start | Starting value for range (numeric) questions | double | True |  |  |  |
| range_end | Ending value for range (numeric) questions | double | True |  |  |  |
| range_increment | Increment value for range (numeric) questions | double | True |  |  |  |
| range_default | Default value for range (numeric) questions | double | True |  |  |  |
| text_default | Default value for text questions | string | True | 8000 |  |  |
| archived | If variable has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_procedure_metadata_selection

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_procedure_metadata_selection_id | static_procedure_metadata_selection table id | int | False |  |  |  |
| static_procedure_metadata_id | procedure_metadata table id | int | False |  |  |  |
| value | Metadata response value. | string | True | 2000 |  |  |
| default | If this value is the default for the metadata variable. | boolean | True |  |  |  |
| default_text | Default text for the value | string | True | 8000 |  |  |
| archived | If value has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_outcome_measurement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_outcome_measurement_id | static_outcome_measurement table id | int | False |  |  |  |
| variable | Outcome variable name | string | True | 256 |  |  |
| title | Name of the outcome | string | True | 256 |  |  |
| question_text | Question text of the outcome | string | True | 256 |  |  |
| units | Unit of measure | string | True | 256 | %, microns, etc. |  |
| range_start | Starting value for the measurement | double | True |  |  |  |
| range_end | Ending value for the measurement | double | True |  |  |  |
| range_increment | Increment value for the measurement | double | True |  |  |  |
| worse_performance | What indicates worse performance for the measurement | string | True | 256 |  |  |
| archived | If measurement has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_pathology_result

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_pathology_result_id | static_pathology_result table id | int | False |  |  |  |
| result | Pathology result | string | True | 255 |  |  |
| cancer_type | Indicates if the pathology result is cancerous or precancerous | string | True | 50 |  |  |
| archived | If result has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_pathology_action

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_pathology_action_id | static_pathology_action table id | int | False |  |  |  |
| action | Pathology action | string | True | 255 |  |  |
| archived | If action has been archived (no longer presented in the application). | boolean | True |  |  |  |

## static_pathology_plan

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| static_pathology_plan_id | static_pathology_plan table id | int | False |  |  |  |
| plan | Pathology plan | string | True | 255 |  |  |
| archived | If plan has been archived (no longer presented in the application). | boolean | True |  |  |  |
