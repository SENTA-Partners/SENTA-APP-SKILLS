# Column Dictionary: eLab (247 columns)


## result_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_id | result_log table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| referral_institution_id | referral_institution table id | string | True | 20 |  |  |
| elab_order_id | elab_order table id | string | True | 20 |  |  |
| elab_order_result_id | elab_order_result table id | string | True | 20 |  |  |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| pathology_log_id | pathology_log table id | string | True | 20 |  |  |
| pathology_group_identifier | Group identifier for pathology results | string | True | 20 |  |  |
| received_date | Date result was received | timestamp | True |  |  |  |
| visit_date | Date of patient visit | timestamp | True |  |  |  |
| collected_date | Date lab was collected | timestamp | True |  |  |  |
| performed_date | Date lab was performed | timestamp | True |  |  |  |
| type | Type of lab result | string | True | 20 | UNKNOWN RADIOLOGY PT_OT PROCEDURE PATHOLOGY LAB CLINICAL_TESTING |  |
| name | Title of result received | string | True | -1 |  |  |
| flag | Flag received with result | string | True | -1 |  |  |
| diagnosis | Diagnosis received with result | string | True | -1 |  |  |
| provider_name | Provider's name | string | True | 250 |  |  |
| vendor_name | Vendor's name | string | True | 150 |  |  |
| status | Status of result | string | True | 20 | CORRECTED FINAL PRELIMINARY |  |
| workflow_status | Workflow status of result | string | True | 20 | ARCHIVED COMPLETED NEW OPENED PENDING SENT_FOR_SIGNATURE SIGNED_AND_COMPLETE SIGNED_AND_PENDING |  |
| sent_to_portal | Sent to portal status | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## result_log_note

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_note_id | result_log_note table id | string | False | 20 |  |  |
| result_log_id | result_log table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | False | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| note | Note for a result | string | True | 1000 |  |  |
| archived | If archived | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## result_log_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_attachment_id | result_log_attachment table id | string | False | 20 |  |  |
| result_log_id | result_log table id | string | False | 20 |  |  |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## result_log_detail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_detail_id | result_log_detail table id | string | False | 20 |  |  |
| result_log_id | result_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| order_log_id | order_log table id | string | True | 20 |  |  |
| body_location_id | body_location table id | string | True | 20 |  |  |
| result_name | Name of result | string | True | -1 |  |  |
| result_type | Type of result | string | True | 10 | PATHOLOGY RADIOLOGY UNKNOWN |  |
| body_part | Body location of result | string | True | 100 |  |  |
| flag | Result flag | string | True | 20 | ABNORMAL BENIGN CANCEROUS HIGH INCONCLUSIVE LOW NONE NORMAL OUT_OF_RANGE PANIC_VALUE PRE_CANCEROUS UNKNOWN |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## result_log_sub_detail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_sub_detail_id | result_log_sub_detail table id | string | False | 20 |  |  |
| result_log_detail_id | result_log_detail table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| body_location_id | body_location table id | string | True | 20 |  |  |
| result_name | Name of result | string | True | 800 |  |  |
| result_type | Type of result | string | True | 10 | PATHOLOGY RADIOLOGY UNKNOWN |  |
| body_part | Body location of result | string | True | 100 |  |  |
| flag | Result flag | string | True | 20 | ABNORMAL BENIGN CANCEROUS HIGH INCONCLUSIVE LOW NONE NORMAL OUT_OF_RANGE PANIC_VALUE PRE_CANCEROUS UNKNOWN |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## result_log_detail_diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_detail_diagnosis_id | result_log_detail_diagnosis table id | string | False | 20 |  |  |
| result_log_detail_id | result_log_detail table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| diagnosis_id | diagnosis table id | string | True | 20 |  |  |
| diagnosis_name | Name of the diagnosis associated with the result | string | True | 200 |  |  |
| diagnosis_type | High-level diagnosis type | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## order_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| order_log_id | order_log table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| patient_case_id | patient_case table id | string | True | 20 |  |  |
| elab_order_id | elab_order table id | string | True | 20 |  |  |
| procedure_id | procedure table id | string | True | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| order_number | Requisition number for an order | string | True | 10 |  |  |
| order_name | Order name | string | True | -1 |  |  |
| order_details | Tests ordered, universal id, etc | string | True | -1 |  |  |
| priority | Order priority | string | True | 10 | HIGH NORMAL STAT |  |
| provider_name | Name of provider on order | string | True | 250 |  |  |
| facility_name | Name of facility on order | string | True | 100 |  |  |
| perform_at_name | Name of lab an order is sent to | string | True | 200 |  |  |
| order_type | Type of order | string | True | 20 | ALLERGY AUDIOLOGY DIAGNOSTIC_TEST DMEPOS FOLLOW_UP GENERAL INFUSION INJECTION LABS PATHOLOGY PROCEDURE RADIOLOGY REFERRAL SURGERY THERAPIES |  |
| order_sub_type | Sub type of order | string | True | 30 | CHEMISTRY CT DIAGNOSTIC DURABLE_MEDICAL_EQUIPMENT IMMUNOLOGY INSTRUCTION INTERVENTIONAL_RADIOLOGY INVASIVE MICROBIOLOGY MINIMALLY_INVASIVE MRI NUCLEAR_MEDICINE OCCUPATIONAL ORTHOTICS OTHER PANELS PHYSICAL RADIOGRAPHY SUPPLIES THERAPEUTIC US WORKERS_COMP |  |
| order_status | Status of order | string | True | 20 | CANCELED CLOSED IN_PROGRESS OPEN SENT |  |
| order_date | Date of order | timestamp | True |  |  |  |
| order_due_date | Due date of order | timestamp | True |  |  |  |
| order_scheduled_date | Schedule date of order | timestamp | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## order_log_detail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| order_log_detail_id | order_log_detail table id | string | False | 20 |  |  |
| order_log_id | order_log table id | string | False | 20 |  |  |
| parent_order_log_detail_id | order_log_detail table id. | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| order_type | order type | string | True | 20 | ALLERGY AUDIOLOGY DIAGNOSTIC_TEST DMEPOS FOLLOW_UP GENERAL INFUSION INJECTION LABS PATHOLOGY PROCEDURE RADIOLOGY REFERRAL SURGERY THERAPIES |  |
| key | Detail key | string | True | 30 |  |  |
| title | Title of the detail | string | True | 260 |  |  |
| value | Value of the detail | string | True | -1 |  |  |
| grouping | Group of details under the parent test, diagnosis, etc. | string | True | -1 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## order_log_detail_cpt_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| order_log_detail_cpt_code_id | order_log_detail_cpt_code table id | string | False | 26 |  |  |
| order_log_detail_id | order_log_detail table id | string | False | 20 |  |  |
| order_log_id | order_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| cpt_code | CPT Code. | string | True | 5 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## order_log_note

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| order_log_note_id | order_log_note table id | string | False | 20 |  |  |
| order_log_id | order_log table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | False | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| note | Note for an order | string | True | 1000 |  |  |
| archived | If archived | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## order_log_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| order_log_attachment_id | order_log_attachment table id | string | False | 20 |  |  |
| order_log_id | order_log table id | string | False | 20 |  |  |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## result_log_order

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| result_log_order_id | result_log_order table id | string | False | 20 |  |  |
| result_log_id | result_log table id | string | False | 20 |  |  |
| order_log_id | order_log table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## elab_order

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| elab_order_id | elab_order table id | string | False | 20 |  |  |
| visit_id | visit table id | string | True | 20 | Visit the order was created from |  |
| staff_id | staff table id | string | True | 20 | Ordering provider |  |
| patient_id | patient table id | string | True | 20 |  |  |
| lab_id | lab table id | string | True | 20 | Lab to send the order to |  |
| lab_facility_id | lab_facility table id | string | True | 20 | Lab facility to send the order to. NULL if a lab facility was not selected when creating the order. |  |
| order_number | Order number for the lab order. Multiple tests can have the same order_number. NOTE: order numbers may be re-used across patients (??). | int | True |  |  |  |
| lab_order_number | Lab order number for the lab order | string | True | 30 |  |  |
| billing_type | Billing Type | string | True | 30 |  |  |
| lab_type | Lab Type. May have a null value. | string | True | 30 | PATHOLOGY PATHOLOGY_EST CLINICAL CLINICAL_EST RADIOLOGY RADIOLOGY_EST SURGICAL THERAPIES THERAPIES_EST MIXED URINALYSIS UNKNOWN |  |
| workflow_status | Status of the order. | string | True | 20 | PENDING_RESULTS PENDING_COMPLETION COMPLETE CANCELLED RESULT_SOURCE_ORDER |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## elab_order_test

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| elab_order_test_id | elab_order_test table id | string | False | 20 |  |  |
| elab_order_id | elab_order table id | string | False | 20 | Order the test is a part of |  |
| patient_id | patient table id | string | True | 20 |  |  |
| diagnosis_id | diagnosis table id | string | True | 20 | Diagnosis the lab test was ordered from |  |
| pathology_log_id | pathology_log table id | string | True | 20 | Pathology log entry the test is associated with. NOTE: there may be multiple eLab tests associated with a single pathology log entry. |  |
| universal_service_id | Universal Service ID (HL7 OBR-4) | string | True | 300 |  |  |
| filler_field_1 | Filler Field 1 (HL7 OBR-20). Only populated for pathology orders. | string | True | 60 |  |  |
| loinc | LOINC number for the test, if applicable. | string | True | 10 |  |  |
| lab_compendium_code | Compendium code for the test, if applicable | string | True | 30 |  |  |
| test_number | Number to identify the test. Combination of order_number and filler_field_1/loinc/compendium_code. | string | True | 60 |  |  |
| relevant_clinical_information | Relevant Clinical Information (HL7 OBR-13) | string | True | 350 |  |  |
| specimen_source | Specimen Source (HL7 OBR-15) | string | True | 350 |  |  |
| reason_for_study | Reason for Study (HL7 OBR-31) | string | True | 350 |  |  |
| status | Status of the order | string | True | 30 | PLACED: order was created from a test procedure in the VE Room SENT: order was sent from the eLab Outbound Orders tab CANCELED: order was cancelled from the eLab Outbound Orders tab |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## elab_order_result

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| elab_order_result_id | elab_order_result table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 | firm id from firm table |  |
| patient_id | patient table id | string | True | 20 |  |  |
| elab_order_id | elab_order table id | string | True | 20 | Order the result is for. Can be NULL |  |
| process_type | What kind of information is in the lab order result | string | True | 21 | ASSIGNED CORRECTED ERROR PERMANENTLY_REJECTED REJECTED RESULTS |  |
| matching_confidence | This is the matching confidence of a result with an order | int | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## elab_result

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| elab_result_id | elab_result table id | string | False | 20 |  |  |
| elab_order_id | elab_order table id | string | False | 20 | Order the result is for. Can be NULL |  |
| elab_order_test_id | elab_order_test table id | string | True | 20 | Specific test the result is for. Can be NULL |  |
| patient_id | patient table id | string | True | 20 |  |  |
| assigned_by_id | staff table id | string | True | 20 | Staff member that assigned the result |  |
| pathology_log_id | pathology_log table id | string | True | 20 | Pathology log entry the result is associated with. NOTE: there may be multiple eLab results associated with a single pathology log entry. |  |
| date_received | Date/time the result was received. NOTE: this is determined from database record creation date, not a field received from the lab. | timestamp | True |  |  |  |
| universal_service_id | Universal Service ID (HL7 OBR-4) | string | True | 300 |  |  |
| filler_order_number | Filler Order Number (HL7 OBR-3). Only populated for pathology results. | string | True | 60 |  |  |
| loinc | LOINC number for the test, if applicable. | string | True | 10 |  |  |
| lab_compendium_code | Compendium code for the test, if applicable | string | True | 30 |  |  |
| test_number | Number to identify the test. Combination of order_number and filler_field_1/loinc/compendium_code. | string | True | 60 |  |  |
| relevant_clinical_information | Relevant Clinical Information (HL7 OBR-13) | string | True | 320 |  |  |
| specimen_source | Specimen Source (HL7 OBR-15) | string | True | 300 |  |  |
| reason_for_study | Reason for Study (HL7 OBR-31) | string | True | 500 |  |  |
| status | Status of the order | string | True | 30 | RESULTS: result received, not assigned to a patient CORRECTED: corrected results received ASSIGNED: result assigned to a test/patient REJECTED: result rejected by a staff member ERROR |  |
| date_assigned | Date/time the result was assigned. | timestamp | True |  |  |  |
| auto_assigned | If the result was auto-assigned based on 100% match. | boolean | True |  |  |  |
| active | If this result is the active result for the test. There may be multiple results for a test, but only one should be active. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_request

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_request_id | lab_request table id | string | False | 20 |  |  |
| elab_order_id | elab_order table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| pathology_log_id | pathology_log table id | string | True | 20 |  |  |
| result_status | Status of the order | string | True | 20 | ARCHIVED ASSIGNED CANCELED CORRECTED ERROR ORDER_SENT PLACE_ORDER REJECTED RESULTS |  |
| test_number | Unique identifier of the tests assigned to a lab order | string | True | 30 |  |  |
| filler_order_number | Filler Order Number (HL7 OBR-3). Only populated for pathology results. | string | True | 60 |  |  |
| universal_service_number | Universal Service ID (HL7 OBR-4) | string | True | 300 |  |  |
| relevant_clinical_information | Relevant Clinical Information (HL7 OBR-13) | string | True | 350 |  |  |
| ordering_provider | Name of ordering provider | string | True | 200 |  |  |
| reason_for_study | Reason for Study (HL7 OBR-31) | string | True | 400 |  |  |
| active | If this request is the active request for the test. There may be multiple requests for a test, but only one should be active. | boolean | True |  |  |  |
| observation_date | Date of observation | timestamp | True |  |  |  |
| date_received | date request was received | timestamp | True |  |  |  |
| date_assigned | date request was assigned | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_result

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_result_id | lab_result table id | string | False | 20 |  |  |
| lab_request_id | lab request id | string | False | 20 | lab_request table id |  |
| patient_id | patient table id | string | True | 20 |  |  |
| lab_note_id | lab note id | string | True | 20 | lab_note table id. Can be NULL |  |
| observation_identifier | lab observation identifier | string | True | -1 |  |  |
| observation_sub_id | sub lab observation identifier | string | True | 20 |  |  |
| observation_value | Observation value | string | True | -1 |  |  |
| observation_result_status | Result status of observation | string | False | 20 | CANNOT_BE_OBTAINED CORRECTION DELETE FINAL NOT_ASKED NOT_RESULT NOT_VERIFIED PARTIAL PENDING PRELIMINARY UNSUPPORTED |  |
| observation_datetime | Datetime of lab observation | timestamp | True |  |  |  |
| date_performed | Datetime of lab performance | timestamp | True |  |  |  |
| analysis_datetime | Datetime of lab analysis | timestamp | True |  |  |  |
| performing_organization_name | Performing lab organization name | string | True | 600 |  |  |
| performing_organization_address | Performing lab organization address | string | True | 300 |  |  |
| performing_organization_medical_director | Performing lab organization medical director | string | True | 1000 |  |  |
| lab_result_note | Additional note from performing organization | string | True | -1 |  |  |
| sequence_number | Sequence number of lab result note | int | True |  |  |  |
| source | Source of lab note | string | True | 100 |  |  |
| type | Type of lab note | string | True | 300 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_attachment_id | lab_attachment table id | string | False | 20 |  |  |
| lab_request_id | lab_request table id | string | False | 20 |  |  |
| lab_result_id | lab_result table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| result_signed_by_staff_id | staff table id | string | True | 20 |  |  |
| result_signed_by_staff_secondary_id | staff table id | string | True | 20 |  |  |
| filename | Name of the file | string | True | 255 |  |  |
| source | File associated with lab_request or lab_result | string | True | 20 | lab_request lab_result |  |
| result_signed_date | Date/time when the result is signed | timestamp | True |  |  |  |
| result_signed_date_secondary | Secondary date/time when the result is signed | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_note

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_note_id | lab_note table id | string | False | 20 |  |  |
| elab_order_id | elab_order table id | string | False | 20 |  |  |
| lab_request_id | lab_request table id | string | True | 20 |  |  |
| lab_result_id | lab_result table id | string | True | 20 |  |  |
| lab_attachment_id | lab_attachment table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| lab_note | Note created with a lab result or lab request | string | True | -1 |  |  |
| sequence_number | Sequence number of lab result note | int | True |  |  |  |
| source | Source of lab note | string | True | 100 |  |  |
| type | Type of lab note | string | True | 300 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
