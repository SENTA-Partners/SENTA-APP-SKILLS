# Column Dictionary: Visit (196 columns)


## visit

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 | Facility where the visit took place |  |
| physician_id | staff table id | string | True | 20 | Primary provider for the visit. --Deprecated and used for backward compatibility |  |
| primary_provider_id | staff table id | string | True | 20 | Primary provider for the visit |  |
| primary_biller_id | staff table id | string | True | 20 | Primary biller for the visit |  |
| primary_care_provider_id | referral_contact table id | string | True | 20 | Primary care provider set to mention in the note. NOTE: only is populated if "Mention in visit note" is selected in Manage Visit Settings for the Primary Care Provider (PCP). |  |
| referring_provider_id | referral_contact table id. *Note*: This column will be deprecated on our next release. Please join to `patient_referring_provider` on `patient_id`. Relationship will be one to many. | string | True | 20 | Referring provider set to mention in the note. NOTE: only is populated if "Mention in visit note" is selected in Manage Visit Settings for the Referring Provider. | True |
| bill_overridden_staff_id | staff table id | string | True | 20 | Staff Id from override billing table. |  |
| patient_case_id | Patient Case Identifier | string | True | 20 |  |  |
| fee_schedule_id | fee_schedule table id (PM Column). Provider fee schedule. | string | True | 20 |  |  |
| ordering_provider_id | staff table id | string | True | 20 |  |  |
| supervising_provider_id | staff table id | string | True | 20 |  |  |
| ordering_referral_contact_id | referral_contact table id. | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| visit_date | Date the visit took place | timestamp | True |  |  |  |
| visit_date_ld | Date the visit took place | timestamp | True |  |  |  |
| type | Type of visit record. NOTE: not all types are "real" visits! | string | True | 30 | VISIT PATIENT_CREATED_VISIT PROTOCOL VISIT_WITHOUT_ENCOUNTER MEASUREMENT_WITHOUT_VISIT |  |
| visit_category | Visit category associated with the visit. | string | True | 255 |  |  |
| transition_of_care | Was patient referred from another setting of care or provider? | boolean | True |  |  |  |
| pms_id | PMS ID | string | True | 50 |  |  |
| pms_id_type | PMS ID Type | string | True | 100 |  |  |
| fin | FIN Visit ID | string | True | 50 |  |  |
| bill_as | Bill As | string | True | 45 | See Appendix G |  |
| archived | If the visit is archived | boolean | True |  |  |  |
| override_em_code | Override Suggested E/M Code | string | True | 50 | TELEMEDICINE, EM_99024, EM_99201, etc. |  |
| bill_by_time_minutes | Bill by time - Time (in minutes) to bill | int | True |  |  |  |
| bill_by_time_percent_counseling | Bill by time - Percent of time Counseling or Coordinating Care | int | True |  |  |  |
| bill_by_time_visit_type | Bill by time - Visit Type | string | True | 50 | NEW_PATIENT ESTABLISHED CONSULT TELEHEALTH_NEW_PATIENT TELEHEALTH_ESTABLISHED_PATIENT |  |
| bill_overridden | If the suggested bill was overridden. NOTE: override E/M code and bill by time do not immediately set this flag to true. The user must actually select "Override Bill" and make edits to the bill to trigger this flag. Most will, however, since override E/M code and bill by time do not add a diagnosis pointer to the new E/M code. | boolean | True |  |  |  |
| refuse_vitals | If the patient refused vitals | boolean | True |  |  |  |
| is_last_visit | Visit is most recent visit for patient. | boolean | True |  |  |  |
| visit_status | Status of the visit | string | True | 50 | CHARGES_SENT CODED FINAL FINALIZING HELD_FOR_BILLING HELD_FOR_RESULTS HELD_FOR_TRANSCRIPTION PRELIMINARY RECORDING_IN_PROGRESS TRANSCRIPTION_FAILED TRANSCRIPTION_READY |  |
| historical_summary | Historical summary note | string | True | -1 |  |  |
| ai_scribe_visit | Boolean column to the visit table that designates if a visit was done with Ambient Listening | boolean | True |  |  |  |
| finalized_date | Date the visit was finalized. | timestamp | True |  |  |  |
| finalized_date_ld | Date the visit was finalized. | timestamp | True |  |  |  |
| note_created_date | Chart note created date | timestamp | True |  |  |  |
| note_created_date_ld | Chart note created date | timestamp | True |  |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| date_created | Date the visit was created (database generated). | timestamp | True |  |  |  |
| date_modified | Date the visit was modified (database generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_attendee

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_attendee_id | visit_attendee table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| staff_id | staff table id | string | True | 20 | Staff member that is in attendance |  |
| scribe | If the attendee is a scribe for the visit. | boolean | True |  |  |  |
| is_primary_provider | Designates if the staff member is the visit's Primary Provider. | boolean | True |  |  |  |
| is_primary_biller | Designates if the staff member is the visit's Primary Biller. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_finalization_phase

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_finalization_phase_id | visit_finalization_phase table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| phase | Each phase is a step in which a visit is finalized | string | True | 30 | ATTACH_PROCEDURES BROADCAST CCD CLAIM ENCOUNTER FINALIZE_BILL FINALIZE_CHART_NOTE FINALIZE_OUTPUTS GLOBAL_PERIOD INVENTORY_MGT MIPS_EVENTS OB_MANAGEMENT_LIST PATIENT_OUTCOME_MEASUREMENTS PROCEDURES_AND_PLANS PROCESS_ATTACHMENTS PUBLISH_CCD PUBLISH_VISIT SEND_CHARGES UPDATE_PROBLEM_LIST |  |
| phase_success | Indicates if phase was successful | boolean | True |  |  |  |
| error | Java error output for debugging when a phase fails. Note: This column will be removed on our next release. | string | True | -1 |  | True |
| position | The numerical position the finalizing phase is in | int | True |  |  |  |
| date_run | Datetime the phase was run | timestamp | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## ros

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| ros_id | ros table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| question | Review of systems question. | string | True | 255 |  |  |
| type | Ros type/system. | string | True | 100 | ALLERGIC_IMMUNOLOGIC, CARDIOVASCULAR, CONSTITUTIONAL_SYMPTOM, NONE, OTHER |  |
| flag_alert | If the ros entry is an alert, will alert provider when creating a new visit for the patient. | boolean | True |  |  |  |
| value | True for yes, false for no. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## vitals

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| vitals_id | vitals table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| taken_by_id | staff table id | string | True | 20 | Staff member that took the vitals |  |
| vitals_date | Date vitals are recorded (may be edited by staff member, and different than visit date) | timestamp | True |  |  |  |
| bp_diastolic | Diastolic blood pressure (mmHg) | int | True |  |  |  |
| bp_systolic | Systolic blood pressure (mmHg) | int | True |  |  |  |
| bp_position | Position the patient was in when blood pressure was recorded. | string | True | 50 | SITTING STANDING SUPINE |  |
| height | Patient height. | double | True |  |  |  |
| units_height | Units of measure for the height. | string | True | 20 | IN CM |  |
| weight | Patient weight. | double | True |  |  |  |
| units_weight | Units of measure for the weight. | string | True | 20 | LBS KG |  |
| pulse | Beats per minute | int | True |  |  |  |
| respiration | Breaths per minute | int | True |  |  |  |
| temperature | Patient temperature. | double | True |  |  |  |
| units_temperature | Units of measure for the temperature. | string | True | 20 | F C |  |
| oxygen_saturation | Oxygen Saturation (percent) | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_cash

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_cash_id | bill_cash table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_name | Name of the diagnosis associated with the cash bill. No ID linkage is present so the diagnosis table must be joined by visit_id and diagnosis_name. | string | True | 255 | See diagnosis.diagnosis_name |  |
| procedure_name | Name of the procedure associated with the cash bill. No ID linkage is present so the procedure must be joined by the visit_id, diagnosis_name, and procedure_name. | string | True | 255 | See procedure.procedure_name |  |
| quantity | Quantity of the bill. | int | True |  |  |  |
| charge | Charge in dollars. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## final_bill_procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| final_bill_procedure_id | final_bill_procedure table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position in the bill (order of code in list of codes). | int | True |  |  |  |
| cpt | CPT/HCPCS procedure code sent for billing. | string | True | 20 |  |  |
| quantity | Quantity of the CPT code. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## final_bill_diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| final_bill_diagnosis_id | final_bill_diagnosis table id | string | False | 64 |  |  |
| final_bill_procedure_id | final_bill_procedure table id | string | False | 20 | Procedure code that the diagnosis code(s) are associated with. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position in the bill (order of code in list of codes). | int | True |  |  |  |
| icd9 | ICD9 code sent for billing. | string | True | 255 |  |  |
| icd10 | ICD10 code sent for billing. | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## final_bill_modifier

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| final_bill_modifier_id | final_bill_modifier table id | string | False | 20 |  |  |
| final_bill_procedure_id | final_bill_procedure table id | string | False | 20 | Procedure code that the modifier is associated with. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position in the bill (order of code in list of codes). | int | True |  |  |  |
| modifier | CPT modifier. | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## original_bill_procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| original_bill_procedure_id | original_bill_procedure table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position in the bill (order of code in list of codes). | int | False |  |  |  |
| cpt | CPT/HCPCS procedure code | string | True | 20 |  |  |
| quantity | Quantity of the CPT code. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## original_bill_diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| original_bill_diagnosis_id | original_bill_diagnosis table id | string | False | 64 |  |  |
| original_bill_procedure_id | original_bill_procedure table id | string | False | 20 | Procedure code that the diagnosis code(s) are associated with. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position in the bill (order of code in list of codes). | int | False |  |  |  |
| icd9 | ICD9 code. | string | True | 25 |  |  |
| icd10 | ICD10 code. | string | True | 25 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## original_bill_modifier

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| original_bill_modifier_id | original_bill_modifier table id | string | False | 20 |  |  |
| original_bill_procedure_id | original_bill_procedure table id | string | False | 20 | Procedure code that the modifier is associated with. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position in the bill (order of code in list of codes). | int | True |  |  |  |
| modifier | CPT modifier. | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_follow_up

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_follow_up_id | visit_follow_up table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Position of the follow up entry in the list of follow ups. | int | True |  |  |  |
| prn | If follow up is PRN. If true, follow_up_time and follow_up_unit columns will be NULL. | boolean | True |  |  |  |
| follow_up_time | Time until follow up appointment. See follow_up_unit for the unit of time this is measured by. | int | True |  |  |  |
| follow_up_unit | Unit of time for follow_up_time | string | True | 20 |  |  |
| appointment_length | Follow up appointment length (in minutes) | int | True |  |  |  |
| scheduling_ok_to_double_book | Scheduling Instructions - ok to double book | boolean | False |  |  |  |
| scheduling_next_available | Scheduling Instructions - next available | boolean | False |  |  |  |
| scheduling_as_previously_scheduled | Scheduling Instructions - as previously scheduled | boolean | False |  |  |  |
| scheduling_once_testing_is_complete | Scheduling Instructions - once testing is complete | boolean | False |  |  |  |
| scheduling_prn | Scheduling Instructions - PRN | boolean | False |  |  |  |
| scheduling_with_physician | Scheduling Instructions - with physician | boolean | False |  |  |  |
| scheduling_with_pa | Scheduling Instructions - with PA | boolean | False |  |  |  |
| scheduling_with_np | Scheduling Instructions - with NP | boolean | False |  |  |  |
| scheduling_with_staff | Scheduling Instructions - once testing is complete | boolean | False |  |  |  |
| scheduling_by_phone | Scheduling Instructions - by phone | boolean | False |  |  |  |
| other_instructions | Other Instructions | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_follow_up_reason

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_follow_up_reason_id | visit_follow_up_reason table id | string | False | 20 |  |  |
| visit_follow_up_id | visit_follow_up table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| reason | Folow up reason | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## outcome_measurement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| outcome_measurement_id | outcome_measurement table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| hpi_response_id | hpi_response table id | string | True | 20 | Chief complaint that generated the outcome measurement. |  |
| exam_element_id | exam_element table id | string | True | 20 | Exam element that generated the outcome measurement. |  |
| procedure_id | procedure table id | string | True | 20 | Procedure that generated the outcome measurement. |  |
| procedure_body_location_id | procedure_body_location table id | string | True | 20 | Procedure body location that generated the outcome measurement. |  |
| variable | Outcome variable name | string | True | 256 | See static_outcome_measurement.variable |  |
| title | Name of the outcome | string | True | 256 | See static_outcome_measurement.title |  |
| question_text | Question text of the outcome | string | True | 256 | See static_outcome_measurement.question_text |  |
| value | Outcome measurement | double | True |  |  |  |
| units | Unit of measure | string | True | 256 | See static_outcome_measurement.units |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_quality_measure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_quality_measure_id | visit_quality_measure table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| quality_measure | quality_measure table id | int | False |  | Quality measure ID provided by CMS |  |
| performance | Measure performance for the visit | string | True | 20 | EXCLUSION PASS FAIL |  |
| modifier | Modifier code for the numerator code. Gives a different meaning to the numerator code. | string | True | 20 | 1P 2P 3P 8p 8P |  |
| procedure_modifier | Code to define laterality. (OD, OS) | string | True | 10 |  |  |
| numerator_code | Quality measure eligibility code | string | True | 20 |  |  |
| override_code | Flag indicating the code has been overridden, and to use override columns. | boolean | True |  |  |  |
| override_modifier | Overridden version of modifier column. | string | True | 20 |  |  |
| override_numerator_code | Overridden version of numerator code column. | string | True | 20 |  |  |
| override_quality_measure | Overridden version of quality measure column. | string | True | 20 | EXCLUSION PASS FAIL |  |
| reporting_year | Reporting year used for quality measure. | int | True |  |  |  |
| archived | Archived flag. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_code_id | visit_code table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| code_system | Describes the type of code. ICD9, IC10, CPT, etc | string | True | 20 | fdbID Modifier ICD10 LOINC Metathesaurus CPT ICD9 SNOMED quality |  |
| code_value | Code value. | string | True | 60 |  |  |
| source | Where the code came from within EMA. Problem list, past medical history, etc. | string | True | 1000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
