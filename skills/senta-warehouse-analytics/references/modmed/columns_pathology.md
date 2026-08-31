# Column Dictionary: Pathology (123 columns)


## pathology_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pathology_log_id | pathology_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| physician_id | staff table id | string | True | 20 | Provider associated with the entry |  |
| visit_id | visit table id | string | True | 20 |  |  |
| result_entered_by_id | staff table id | string | True | 20 | Staff member that entered the result. NULL if result not entered. |  |
| procedure_body_location_id | procedure_body_location table id | string | True | 20 | If performed in a visit, link to the specific procedure body location the specimen was taken from |  |
| facility_id | facility table id | string | True | 20 |  |  |
| completed_by_id | Staff member that completed the result. NULL if not completed | string | True | 20 |  |  |
| unresolved_by_id | Staff member that moved the result into unresolved status. NULL if status != UNRESOLVED | string | True | 20 |  |  |
| location | Body location override. If non-null the location should NOT be taken by joining on procedure_body_location_id. | string | True | 2000 | See static_body_location table (any field), can also be free-text override |  |
| procedure_name | Procedure name override. If non-null the procedure name should NOT be taken by joining to procedure table. | string | True | 2000 | See procedure.procedure_name, can also be free-text override |  |
| entry_created_date | Date biopsy log entry was created, same as visit date if created from visit. | timestamp | True |  |  |  |
| result_date | Date result was entered | timestamp | True |  |  |  |
| unresolved_date | Date record was moved into unresolved status. NULL if status != UNRESOLVED | timestamp | True |  |  |  |
| cancer_type | Indicates if the biopsy results is cancerous or precancerous. May have a null value. | string | True | 50 | ABNORMAL CANCEROUS PRECANCEROUS NONE WNL_CRITICAL CRITICAL |  |
| result | Biopsy result description | string | True | 2000 | See static_pathology_result.result, can also be free-text override |  |
| comments | Biopsy result comments | string | True | 2000 |  |  |
| action | Action override. If non-null the action should NOT be taken from the pathology_log_action table. | string | True | 2000 |  |  |
| plan | Plan override. If non-null the plan should NOT be taken from the pathology_log_plan table. | string | True | 2000 |  |  |
| manual_result | This is the option for adding result manually. | string | True | 2000 |  |  |
| notes | Path log notes | string | True | -1 |  |  |
| workflow | Practice-custom workflow assigned to the entry | string | True | 100 |  |  |
| pathology_group_identifier | Group identifier for pathology results | string | True | 20 |  |  |
| status | Status of the pathology log entry. NOTE: this status does not track if an eLab order was sent, see elab_order_test table. | string | False | 100 | PENDING_RESULTS: Removal plan was performed, awaiting results to be entered PENDING_PLAN_COMPLETION: Results entered, plan not completed UNRESOLVED: Record moved to unresolved status COMPLETED: Plan completed |  |
| visible | Visible | boolean | True |  |  |  |
| date_completed | Date when pathology_log.status was set to COMPLETED. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pathology_log_notification

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pathology_log_notification_id | pathology_log_notification table id | string | False | 20 |  |  |
| pathology_log_id | pathology_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| log_date_created | Time the notification log was generated | timestamp | True |  |  |  |
| template | Note template used for the noficiation | string | True | 50 | PHONE VOICEMAIL LETTER FREE_FORM |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pathology_log_action

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pathology_log_action_id | pathology_log_action table id | string | False | 20 |  |  |
| pathology_log_id | pathology_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| action | Action to perform based on the biopsy result. | string | True | 255 | See static_pathology_action.action |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pathology_log_plan

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pathology_log_plan_id | pathology_log_plan table id | string | False | 20 |  |  |
| pathology_log_action_id | pathology_log_action table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| plan | Plans to perform based on the biopsy result and action. | string | True | 255 | See static_pathology_plan.plan |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cancer_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cancer_log_id | cancer_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| physician_id | staff table id | string | True | 20 | Managing provider |  |
| pathology_log_id | pathology_log table id | string | True | 20 | Biopsy that cancer was diagnosed with. Use linkage to determine biopsy information such as visit date, procedure, etc. |  |
| refer_to_provider_id | referral_contact table id | string | True | 20 | Plan: Refer to Provider |  |
| referred_from_provider_id | referral_contact table id | string | True | 20 | Referred from Provider |  |
| entry_created_date | Date cancer log entry was created | timestamp | True |  |  |  |
| entry_updated_date | Date cancer log entry was updated | timestamp | True |  |  |  |
| diagnosis | Cancer diagnosis name, same value as pathology_log.result if created from a pathology log entry | string | True | 255 | See pathology_log.result |  |
| diagnosis_snomed | SNOMED based diagnosis for meaningful use | string | True | 25 |  |  |
| diagnosis_narrative | Diagnosis Narrative | string | True | 500 |  |  |
| diagnostic_confirmation | Diagnosis Confirmation | string | True | 32 | See Appendix D |  |
| location | Location | string | True | 255 |  |  |
| location_snomed | SNOMED based body location for meaningful use | string | True | 25 |  |  |
| laterality | Laterality | string | True | 32 | See Appendix D |  |
| behavior | Behavior | string | True | 32 | See Appendix D |  |
| biopsy_date | Biopsy Date | timestamp | True |  |  |  |
| diagnosis_date | Diagnostic Date | timestamp | True |  |  |  |
| treatment_date | Treatment Date | timestamp | True |  |  |  |
| treatment_method | Treatment Method | string | True | 250 |  |  |
| treated_by | Treated By | string | True | 100 |  |  |
| treatment_status | Treatment Status. May have a null value. | string | True | 32 | COMPLETED PENDING |  |
| progress_note | Diagnosis information - progress note | string | True | -1 |  |  |
| clinical_stage | Clinical Stage. May have a null value. | string | True | 32 | STATE_0, STAGE_0A, STAGE_I, ... |  |
| clinical_tumor | TNM Clinical Tumor. May have a null value. | string | True | 32 | See Appendix D CLINICAL_TA, CLINICAL_TIS, CLINICAL_T0, ... |  |
| clinical_node | TNM Clinical Node. May have a null value. | string | True | 32 | CLINICAL_N0, CLINICAL_N1,CLINICAL_N1A, ... |  |
| clinical_metastasis | TNM Clinical Metastasis. May have a null value. | string | True | 32 | CLINICAL_M0, CLINICAL_M1, CLINICAL_M1A, ... |  |
| tnm_date | TNM Date | timestamp | True |  |  |  |
| clinical_stage_descriptor | TNM Clinical Stage Descriptor. May have a null value. | string | True | 32 | NONE, EXTRANODAL_SPLEEN, EXTRANODAL, SPLEEN, etc. |  |
| tnm_edition | TNM Edition. May have a null value. | string | True | 32 | FIRST_EDITION, SECOND_EDITION, ... |  |
| clinical_staged_by | TNM Clinical Staged By. May have a null value. | string | True | 32 | PHYSICIAN, PATHOLOGIST, etc. |  |
| pathology_stage | TNM Pathology Stage. May have a null value. | string | True | 32 | STAGE_0, STAGE_0A, STAGE_I, ... |  |
| pathology_tumor | TNM Pathology Tumor. May have a null value. | string | True | 32 | PATHOLOGY_TA, PATHOLOGY_TIS, PATHOLOGY_T0, etc. |  |
| pathology_node | TNM Pathology Node. May have a null value. | string | True | 32 | PATHOLOGY_N0, PATHOLOGY_N1, etc. |  |
| pathology_metastasis | TNM Pathology Metastasis. May have a null value. | string | True | 32 | PATHOLOGY_M0, PATHOLOGY_M1, ... |  |
| pathology_stage_descriptor | TNM Pathology Stage Descriptor. May have a null value. | string | True | 32 | NONE, EXTRANODAL_SPLEEN, EXTRANODAL, SPLEEN, etc. |  |
| pathology_staged_by | TNM Pathology Staged By. May have a null value. | string | True | 32 | PHYSICIAN, PATHOLOGIST, etc. |  |
| seer_summary_stage | Seer Summary Stage. May have a null value. | string | True | 50 | InSitU, Localized, Distant, etc. |  |
| tumor_grade | Tumor Grade. May have a null value. | string | True | 32 | Low Intermediate High |  |
| breslow_depth | Breslow Depth (mm) | double | True |  |  |  |
| mitotic_index | Mitotic Index. May have a null value. | string | True | 32 | ZERO_PER_HPF, ONE_PER_HPF, ... |  |
| ulceration | Ulceration. May have a null value. | string | True | 32 | ABSENT PRESENT |  |
| tils | Tumor Infiltrating Lymphocytes (TILs). May have a null value. | string | True | 32 | ABSENT BRISK NON_BRISK |  |
| slnbx | Sentinel lymph node biopsy. May have a null value. | string | True | 32 | NEGATIVE POSITIVE |  |
| slnbx_comments | SLNbx Comments | string | True | -1 |  |  |
| radiation_oncology_note | Radiation Oncology Note | string | True | -1 |  |  |
| status | Status of the cancer log entry. | string | False | 32 | PENDING: cancerous pathology result logged, waiting to be added to cancer log ACTIVE: active entry INVALIDATED: entry invalidated REMOVED: pending entry removed ARCHIVED: active entry deleted |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cancer_log_pathology_treatment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cancer_log_pathology_treatment_id | cancer_log_pathology_treatment table id | string | False | 20 |  |  |
| cancer_log_id | cancer_log table id | string | False | 20 |  |  |
| pathology_log_id | pathology_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cancer_log_problem

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cancer_log_problem_id | cancer_log_problem table id | string | False | 32 |  |  |
| cancer_log_id | cancer_log table id | string | False | 20 |  |  |
| problem_list_id | problem_list table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cancer_log_procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cancer_log_procedure_id | cancer_log_procedure table id | string | False | 32 |  |  |
| cancer_log_id | cancer_log table id | string | False | 20 |  |  |
| procedure_log_id | procedure_log table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cancer_log_medication

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cancer_log_medication_id | cancer_log_medication table id | string | False | 32 |  |  |
| cancer_log_id | cancer_log table id | string | False | 20 |  |  |
| medication_id | medication table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cancer_log_visit

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cancer_log_visit_id | cancer_log_visit table id | string | False | 20 |  |  |
| cancer_log_id | cancer_log table id | string | False | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| history_selected | If history is being updated in this visit | boolean | True |  |  |  |
| history_status | Patient Status. May have a null value. | string | True | 100 | DENY_RECUR, CONCERN_RECUR, EDU_AND_COUNSELING, etc. |  |
| history_comments | Comments for patient status | string | True | -1 |  |  |
| plan_selected | If plan is being updated in this visit | boolean | True |  |  |  |
| exam | Exam | string | True | 100 | NO_CLINICAL_SIGNS, RESIDUAL_EROSION, WELL_HEALED_NER, etc. |  |
| plan | Plan | string | True | 100 | RECOMMEND_EXAM, EDU_REGULAR, FURTHER_EVAL |  |
| plan_comments | Comments for exam/plan | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
