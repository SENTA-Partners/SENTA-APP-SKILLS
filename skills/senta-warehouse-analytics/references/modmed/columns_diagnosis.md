# Column Dictionary: Diagnosis (91 columns)


## diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| is_new | If the diagnosis was selected as a new diagnosis. | boolean | True |  |  |  |
| is_ruleout | If the diagnosis is the leading diagnosis of a differential diagnosis (DDX). | boolean | True |  |  |  |
| diagnosis_name | ModMed clinical diagnosis names, not necessarily related to ICD codes. May be more or less detailed than an ICD code. | string | True | 255 | See static_diagnosis.diagnosis_name |  |
| uncertain_diagnosis_name | ModMed clinical diagnosis names, not necessarily related to ICD codes. May be more or less detailed than an ICD code. | string | True | 255 | See static_diagnosis.diagnosis_name |  |
| diagnosis_type | High-level diagnosis type | string | True | 100 | See static_diagnosis.diagnosis_type |  |
| diagnosis_status | Status of the diagnosis, if selected. | string | True | 50 | Improved Well Controlled Resolving Resolved Inadequately Controlled Worsening Stable Unchanged Estable Not At Treatment Goal status.improved status.resolved status.stable |  |
| icd9 | Internal reference for searching diagnoses, NOT sent for billing. May be partial/base codes not valid for billing. | string | True | 50 |  |  |
| icd10 | Internal reference for searching diagnoses, NOT sent for billing. May be partial/base codes not valid for billing. | string | True | 25 |  |  |
| medical_domain | Medical domain the chief complaint is part of. | string | True | 255 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY PRIMARY_CARE RHEUMATOLOGY UROLOGY |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_ddx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_ddx_id | diagnosis_ddx table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_name | ModMed clinical diagnosis names, not necessarily related to ICD codes. May be more or less detailed than an ICD code. | string | True | 255 | Differential diagnosis. See diagnosis.diagnosis_name for values. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_adx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_adx_id | diagnosis_adx table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_name | ModMed clinical diagnosis names, not necessarily related to ICD codes. May be more or less detailed than an ICD code. | string | True | 255 | Associated diagnosis. See diagnosis.diagnosis_name for values. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_cause_dx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_cause_dx_id | diagnosis_cause_dx table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_name | ModMed clinical diagnosis names, not necessarily related to ICD codes. May be more or less detailed than an ICD code. | string | True | 255 | Cause diagnosis. See diagnosis.diagnosis_name for values. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_body_location

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_body_location_id | diagnosis_body_location table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| body_part | Specific body part | string | True | 255 | See static_body_location.body_part |  |
| simple_description | Simple body location for diagnosis | string | True | 255 | See static_body_location.exam_simple_description |  |
| detail_description | Detailed body location for diagnosis | string | True | 255 | See static_body_location.exam_detail_description |  |
| zone | High-level body zone | string | True | 255 | See static_body_location.zone |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_body_location_morphology

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_body_location_morphology_id | diagnosis_body_location_morphology table id | string | False | 20 |  |  |
| diagnosis_body_location_id | diagnosis_body_location table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| morphology | Morphology associated with the diagnosis. Users can add custom morphologies; these are not included. | string | True | 10000 | See static_diagnosis_morphology.morphology for default morphologies. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_morphology

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_morphology_id | diagnosis_morphology table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| morphology | Morphology associated with the diagnosis. Users can add custom morphologies. | string | True | 10000 | See static_diagnosis_morphology.morphology for default morphologies. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_measurement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_measurement_id | hpi_follow_up_measurement table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| variable | Variable name for the measurement. Variable names may be re-used across different diagnoses, and multiple variables may have the same title and/or question_text. | string | True | 256 | See static_diagnosis_measurement.variable |  |
| title | Name of the measurement. | string | True | 256 | See static_diagnosis_measurement.title |  |
| question_text | Question displayed to the user. | string | True | 256 | See static_diagnosis_measurement.exam_question_text |  |
| type | Data type of the measurement | string | True | 256 | See static_diagnosis_measurement.type |  |
| value | Value of the measurement | double | True |  |  |  |
| value_title | Title associated with the value, if applicable | string | True | 256 | See static_diagnosis_measurement_value.title |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_lab

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_lab_id | diagnosis_lab table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| ordered_by_staff_id | staff table id | string | True | 20 | Staff member that ordered the lab. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| loinc_num | LOINC number | string | True | 10 |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## diagnosis_lab_set

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_lab_set_id | diagnosis_lab_set table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| lab_set_id | lab_set id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| lab_set_alias | Internal reference for a lab set, multiple lab_set_alias may have the same lab_set_name. NULL if the lab was not ordered as part of a lab set. | string | True | 100 | ~200 unique values. Examples include: Biologic, woundSpecimen, ANAProfile |  |
| lab_set_name | Lab set name displayed to the user. NULL if the lab was not ordered as part of a lab set. | string | True | 255 | ~150 unique values. Example include: Biologics Labs, Wound Specimen, ANA Profile |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## diagnosis_lab_set_lab

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_lab_set_lab_id | diagnosis_lab_set_lab table id | string | False | 20 |  |  |
| diagnosis_lab_set_id | diagnosis_lab_set table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| loinc_num | LOINC number | string | False | 10 |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## diagnosis_referral

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_referral_id | diagnosis_referral table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| referral_contact_id | referral_contact table id | string | True | 20 | Provider that the patient is being referred to. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| specialty | Specialty for the referral | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnosis_referral_correspondence

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnosis_referral_correspondence_id | diagnosis_referral_correspondence table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | False | 20 |  |  |
| referral_contact_id | referral_contact table id | string | True | 20 | Provider that the correspondence is being sent to. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| specialty | Specialty for the correspondence | string | True | 255 |  |  |
| include_body_diagram | If body diagram is included in the correspondence (fax) | boolean | True |  |  |  |
| include_ccd | If CCD is included in the correspondence (fax) | boolean | True |  |  |  |
| include_hipaa_cover_sheet | If HIPAA cover sheet is included in the correspondence (fax) | boolean | True |  |  |  |
| include_notes | If notes are included in the correspondence (fax) | boolean | True |  |  |  |
| include_summary | If summary is included in the correspondence (fax) | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
