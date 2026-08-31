# ModMed Tables Index (416 tables)

Source: ModMed Practice Data Master Dictionary V1.27.0 (2025-06-23).
Longitudinal Tracking codes: Y = row history tracked, N = current state only, S = static lookup.


## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| _info | Metadata for dataset deliverable |  | N |  |

## Lookup

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| loinc | Lookup table for loinc code descriptions. |  | S |  |
| icd9 | Lookup table for ICD9 code descriptions |  | S |  |
| icd10 | Lookup table for ICD10 code descriptions |  | S |  |
| snomed | Lookup table for snomed code descriptions |  | S |  |
| quality_measure | MIPS Quality measures |  | S |  |
| pi_objective | MIPS Promoting Interoperability (PI) objectives/measures. |  | S |  |
| improvement_activity | MIPS Improvement Activities (IA). |  | S |  |

## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| firm | Firm (practice) |  | N |  |
| gpro | Group Practice Reporting Option (GPRO) settings. See staff_mips_settings for providers assigned to a GPRO. | firm | N |  |
| facility | Practice location (facility). One or more per firm. | business_unit region firm | N |  |
| facility_phone_number | Facility phone numbers. Zero or more per facility. | facility | N |  |
| billing_provider_phone_number | Billing provider phone numbers. Zero or more per facility. | facility | N |  |
| staff | Staff member of a firm (Doctor, Medical Assistant, Receptionist, etc.) | staff facility firm | N |  |
| staff_clinical_registry_enrollment | Staff Clinical Registry Enrollment | staff | N |  |
| staff_credentials | Staff credentials. Zero or more per staff member. | staff | N |  |
| staff_specialty | Staff specialties. Zero or more per staff member. | staff | N |  |
| staff_phone_number | Staff phone numbers. Zero or more per staff member. | staff | N |  |
| staff_cds_alert_setting | Clinical decision support provider alert settings. One row per staff member/alert enabled | staff | N |  |
| staff_specialized_registry | Specialized Registries that a provider is submitting data to. One row per provider/registry | staff | N |  |
| staff_mips_settings | MIPS settings for a staff member. One row per staff member/reporting year. | gpro staff | N |  |
| referral_contact | Referral contact (person). One row per firm/referral contact | firm | N |  |
| referral_contact_specialty | Referral contact specialties. Zero or more per referral contact. | referral_contact | N |  |
| referral_institution | Referral institution. One row per firm/referral institution | firm | N |  |
| referral_institution_specialty | Referral institution specialties. Zero or more per referral institution. | referral_institution | N |  |
| lab | Laboratories added in Firm Admin as well as e-Labs set up for the practice. One row per firm/lab. | firm | N |  |
| lab_facility | Facilities for a lab. One row per lab/facility. | lab | N |  |
| lab_account_staff | Doctor (staff) lab accounts. One row per lab/staff member. | staff lab | N |  |
| lab_account_facility | Firm facility lab accounts. One row per lab/facility. | facility lab | N |  |
| firm_group | Staff Group Management. Staff groups allow the firm administrator to send Intramail messages to multiple staff members at one time and it also allows staff members to share protocols. One row per group. | firm | N |  |
| firm_group_member | Practice group member table. A staff member can belong to multiple groups. One row per staff member per group. | firm_group staff | N |  |
| protocol | Visit protocol created by a staff member. One row per protocol. | staff firm | N |  |
| protocol_category | Protocol category. One row per category per protocol | staff protocol | N |  |
| protocol_log | Protocol usage log. One row per protocol usage. | patient visit staff protocol | Y |  |
| protocol_shared | Identifies protocol shared between practice groups or individual staff members. One row per staff or group member. | firm_group staff protocol | N |  |
| business_unit | Business unit for facility. One business unit can be associated with many facilities | staff firm | N | PM |
| business_unit_staff_access | Business unit to staff mapping table. User will have ability to view bills, reports and any financial actions based on the User Privilege set for each user for each business unit | business_unit staff | N | PM |
| business_unit_payer_specific_identifier | Business unit to contracted payer(s) mapping table. | business_unit payer | N | PM |
| business_unit_batch_setting | Stores financial batches configuration for business units. | business_unit | N | PM |

## PM Financials

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| financial_category | Payer's financial category for billing. | firm | N | PM |

## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| firm_denial_management_setting | Denial management settings configured by practice. One row per practice. | firm | Y | PM |
| firm_denial_management_specific_assignee_payer | Denial management settings configured by practice stores the list of payers associated to a specific assignee. One or more row for each specific payer. | firm_denial_management_setting payer firm | Y | PM |
| firm_denial_management_specific_assignee_denial_category | Denial management settings stores the list of denial categories associated to a specific assignee. One or more row per specific assignee. | firm_denial_management_specific_assignee_payer firm | Y | PM |
| fee_schedule | Fee schedule for payers and providers as configured in the practice setting. One row per fee schedule. | provider_group | N | PM |
| fee_schedule_entry | Captures data from the "Manage Fees" user interface. This table only captures CPT entries that have been entered or overridden by the practice. CPT entries that default to the medicare fee schedule and have not been overriden are not stored in this table. One row per CPT code, per facility. | fee_schedule provider_group facility | N | PM |
| fee_schedule_facility | Fee schedule to facility mapping table. One row per fee schedule per facility. | fee_schedule facility | N | PM |
| fee_schedule_payer | Fee schedule to payer mapping table. One row per fee schedule per payer. | payer fee_schedule | N | PM |
| fee_schedule_import_file | Table with information about CSV files imported into a fee schedule. One row per imported file per facility. | fee_schedule facility | N | PM |
| payer | Payer (insurance company) set up by the practice. One row per payer/firm | financial_category firm | N | PM |
| additional_payer_identifier | Stores additional identifiers associated with a payer | payer firm | N | PM |
| payer_address | Payer address table | payer | N | PM |
| payer_plan | Payer plan table | payer | N | PM |
| payer_plan_address | Mapping table for payer_plan to payer_address | payer_address payer_plan | N | PM |
| payer_authorization_requirement | Payer Authorization Requirement table | payer | N | PM |
| payer_state_code | Mapping of Payers to their individual state codes as configured in the practice setting for state reporting. One row per payer per state code. | payer firm | N | PM |
| appointment_type | Appointment type table | firm | N | PM |
| appointment_type_link | Appointment types mapping table | appointment_type | N | PM |
| appointment_group_block | Appointment Calendar preferences for appointment group and block categories. One row per preference category | staff firm | N | PM |
| appointment_group_block_link | Appointment group to appointment type mapping table. Only appointment groups can be linked to appointment types. | appointment_type appointment_group_block | N | PM |
| appointment_calendar | Appointment calendar showing scheduled group, block, and type preferences by provider and by facility. One row per preference category series. Modifications made to date/time columns are tracked in the appointment_calendar_edit table. | staff appointment_group_block facility firm | N | PM |
| appointment_calendar_access | Permission access configurations for appointment calendar. Access is granted to staff per provider calendar | facility staff | N | PM |
| appointment_calendar_edit | Reports any modifications made to the time columns of a preference category series. | appointment_calendar staff | Y | PM |
| division | Divisions are used to group locations and providers together for reporting and billing purposes. | firm | N | PM |
| division_staff | Division to staff mapping table. | division staff | N | PM |
| division_facility | Division to facility mapping table. | division facility | N | PM |
| referral_source | Referral Source Tracking as configured in the Practice Settings. One row per referral transaction. | referral_type firm | N | PM |
| referral_type | Referral types. One row per referral type. | firm | N |  |
| referral_source_link | Patient referral sources link table. One row per referral transaction | patient bill staff visit referral_institution referral_type appointment referral_contact referral_source firm | Y |  |
| provider_group | Provider groups are used to group providers together to a given fee schedule. | firm | N |  |
| provider_group_member | Providers to provider groups mapping table. | provider_group staff | N |  |
| patient_referring_provider | Patient to Referring Provider mapping table. | patient referral_contact firm | N | PM |
| patient_primary_care_provider | Patient to Primary Care Provider mapping table. | patient referral_contact firm | N | PM |
| visit_referral | Visit to referring provider mapping table. | patient visit referral_contact | N | PM |

## MIPS

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| mips_score | MIPS overall score and scores for each performance category. Calculated nightly, not directly entered by providers (see date_calculated field). Can be different that what is displayed in the EMA MIPS Overview. One row per provider. DISCLAIMER: The displayed scores and calculated values are estimated based on the data recorded within EMA. These estimated scores and values may differ from those determined by the Centers for Medicare & Medicaid Services. | gpro staff firm | N |  |
| mips_quality_measure_score | Quality measures scores as part of the overall Quality score. One row per MIPS score/Quality measure. | gpro mips_score staff | N |  |
| mips_pi_objective_score | PI objectives scores as part of the overall PI score. One row per MIPS score/PI objective. | mips_score | N |  |
| mips_quality_selection_ep | Quality measure selections for an Eligible Professional (single provider). One row per provider/measure. | staff | N |  |
| mips_quality_selection_gp | Quality measure selections for an Group Practice (GPRO). One row per GPRO/measure. | gpro | N |  |
| mips_pi_selection_ep | PI selections for objectives that are not computed from provider behavior (i.e. attestations) for an Eligible Professional (single provider). One row per provider/objective attested to. | staff | N |  |
| mips_pi_selection_gp | PI selections for objectives that are not computed from provider behavior (i.e. attestations) for a Group Practice (GPRO). One row per GPRO/objective attested to. | gpro | N |  |
| mips_ia_selection_ep | Improvement Activity selections for an Eligible Professional (single provider). One row per provider/activity. | staff | N |  |
| mips_ia_selection_gp | Improvement Activity selections for a Group Practice (GPRO). One row per GPRO/activity. | gpro | N |  |

## Patient

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| patient | Patient demographics, practice data, and single-response clipboard information | staff facility appointment firm referral_contact financial_category | N |  |
| guarantor | Patient's guarantor information. | patient | N | PM |
| patient_case | Patient's case information. Typically associated with workers compensation, auto accidents or personal injuries. | patient insurance_policy staff | Y |  |
| patient_race | Patient races. Zero or more races per patient | patient | N |  |
| patient_case_attachment | Patient case to file attachment mapping table. | patient patient_case file_attachment | N |  |
| patient_case_contact | Patient's contact information for case. | patient patient_case | N |  |
| insurance_policy_authorization | Insurance policy authorization. | patient staff insurance_policy referral_contact patient_case | N | PM |
| insurance_policy_authorization_attachment | Insurance policy to file attachment mapping table. | patient insurance_policy_authorization file_attachment | N | PM |
| insurance_policy_authorization_appt_type | Insurance policy authorization to specific appointment types mapping table. | patient insurance_policy_authorization appointment_type | N | PM |
| card_on_file | Patient credit cards documented in patient chart. One row per patient per card. | patient staff | N | PM |
| patient_business_unit_setting | Lookup for information on whether patient statements are enabled for a Patient, for a specific business unit. One row per patient per business unit. | patient business_unit | S | PM |
| patient_sticky_note_history | Patient Sticky Note History provides one row of history per patient edit of their sticky note | patient | L |  |
| insurance_group | Insurance group information. One row per patient/insurance group. Collected from PMS or manual entry. | patient | N |  |
| insurance_policy | Insurance policy information. One row per patient/insurance policy. Collected from PMS or manual entry. | patient payer_address payer payer_plan fee_schedule | N |  |
| insurance_group_policy | Insurance policy assigned to one or more groups. One row per group/policy | insurance_group patient insurance_policy | N |  |
| insurance_policy_phone_number | Phone number(s) associated with an insurance policy. One row per policy/phone number. | patient insurance_policy | N |  |
| insurance_policy_address | Address(es) associated with an insurance policy. One row per policy/address. | patient insurance_policy | N |  |
| patient_pharmacy | Pharmacies assigned to a patient. One row per patient/pharmacy. Collected from Surescripts or manual entry. | patient | N |  |
| patient_flag | Patient flags containing pertinent patient information that can be useful for scheduling | patient firm | N |  |
| patient_history | Patient history specific to the medical domain (single-response only). One row per patient. | patient | N |  |
| medical_history | Past medical history information. Includes conditions from generic Past Medical History and specialty-specific medical history. Zero or more entries per patient. Since 5.16, users can add custom conditions with SNOMED codes, so the snomed column contains the most accurate information. | patient | N |  |
| surgical_history | Surgical history details. Includes surgeries from generic Past Medical History and specialty-specific medical history. Zero or more rows per patient. Since 5.16, users can add custom conditions with SNOMED codes, so the snomed column contains the most accurate information. | patient | N |  |
| specialty_pediatric_history | Specialty-specific pediatric history. Zero or more entries per patient. Since 5.16, users can add custom conditions with SNOMED codes, so the snomed column contains the most accurate information. | patient | N | ORTHOPEDICS ENT RHEUMATOLOGY |
| specialty_family_history | Specialty-specific family history. Zero or more entries per patient. Since 5.16, users can add custom conditions with SNOMED codes, so the snomed column contains the most accurate information. | patient | N | DERMATOLOGY PLASTICS ORTHOPEDICS ENT GI RHEUMATOLOGY UROLOGY |
| specialty_history | Specialty-specific history that does not fit into medical, surgical, pediatric, or family history. Zero or more entries per patient. Since 5.16, users can add custom conditions with SNOMED codes, so the snomed column contains the most accurate information. | patient | N | PLASTICS ORTHOPEDICS |
| social_history | Social history details. Includes alcohol, drug use, sexual activity, and driving. Zero or more rows per patient. | patient | N |  |
| medication | Patient current medication list. Zero or more entries per patient | patient rx | L |  |
| allergy | Zero or more allergies per patient. Based on FirstDataBank (FDB). | patient | L |  |
| family_history | Patient family history conditions list, may be zero or more entries per patient. Based on SNOMED family history terms. | patient | L |  |
| problem_list | Patient problem list, may be zero or more entries per patient. Based on ICD9, ICD10, and SNOMED. Codes generated from a diagnosis and conditions selected in the clipboard add codes to this table. | patient diagnosis | L |  |
| procedure_log | Patient procedure log, may ber zero or more entries per patient. Based on SNOMED and LOINC. Some procedures recorded in the procedure table do not add entries this table. May include codes that are not procedures, see type column. | patient | L |  |
| immunization | Immunization recorded in the patient clipboard. One row per patient/immunization. NOTE: does not include immunizations given from a procedure or plan. | patient staff | N |  |
| gyn_history | Patient gynecological medical history information. | patient | N |  |
| patient_reproductive_stage | Contains data about a patient's reproductive stage. | patient | N |  |
| patient_menstrual_history | Contains data about a patient's menstrual history. | patient | N |  |
| patient_hpv_vaccine_history | Contains data about a patient's hpv vaccination history. | patient | N |  |
| patient_pregnancy | Contains data about a patient's ongoing or past pregnancy. | patient patient_pregnancy_history facility staff | N |  |
| patient_pregnancy_baby | Contains the names and sex of the baby or babies in an ongoing or past patient's pregnancy. | patient patient_pregnancy | N |  |
| patient_pregnancy_exposure_questionnarie | Contains the results of the 'Genetic and Environmental Exposures' questionnaire for a pregnant patient. One record for each answered question. | patient patient_pregnancy | N |  |
| pregnancy_chart_patient_vitals | Contains vital signs of the baby or babies related to a patient's pregnancy, captured during an OB/GYN visit. | patient visit patient_pregnancy | N |  |
| pregnancy_chart_baby_vitals | Contains vital signs of the baby or babies related to a patient's pregnancy, captured during an OB/GYN visit. | patient visit patient_pregnancy | N |  |
| patient_pregnancy_delivery_procedure | Contains the list of procedures applied during a pregnancy delivery. | patient patient_pregnancy | N |  |
| patient_pregnancy_history | Contains data about a patient's pregnancy history. | patient | N |  |
| patient_pregnancy_history_baby | Contains data about a baby in a patient's pregnancy history. | patient patient_pregnancy_history | N |  |
| patient_pregnancy_history_complication | Complications related to a patient's pregnancy history. | patient patient_pregnancy_history | N |  |
| chart_note | Stores comments associated with a patient’s chart. One row per chart note. | patient visit staff firm | N |  |
| chart_segmentation_event | Chart segementation report table, one row per event. | patient staff | N |  |
| chart_note_signature | Stores signatures associated with a patient's chart notes. One row per chart note signature. | patient chart_note staff | N |  |

## Document Management

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| document_category | Document categories for file attachments, faxes, etc. One row per firm/category. | firm | L |  |
| document_firm | Stores metadata about documents associated with a firm. One row per document, per firm. | document_category firm | N |  |
| file_attachment | Log of file attachments, including those not assigned to a patient. One row per file. NOTE: file contents are not included in this table. | patient document_category staff procedure visit elab_order lab_request procedure_body_location diagnosis document_firm firm | L |  |
| fax_template | Stores metadata associated with fax templates. One row per firm/template. | firm | N |  |
| fax_management | One row per outbound fax. This table contains additional metadata associated with outbound faxes. | patient visit staff fax_template | N |  |
| fax_outbound | Queued and sent outbound faxes. One row per outbound fax. | fax_template patient staff visit referral_institution fax_management referral_contact | N |  |
| fax_inbound | Inbound faxes. One row per inbound fax. | patient fax_line file_attachment | N |  |

## eLab

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| result_log | Log of test result received and their status | patient elab_order_result staff facility visit elab_order referral_institution pathology_log file_attachment firm | L |  |
| result_log_note | Notes associated with result_log records. | patient staff facility result_log firm | L |  |
| result_log_attachment | Linking table for file attachments associated with a result | patient facility result_log file_attachment firm | L |  |
| result_log_detail | Flexible metadata associated with a result. | patient body_location order_log result_log | L |  |
| result_log_sub_detail | Additional details for results received | patient body_location result_log_detail | L |  |
| result_log_detail_diagnosis | Diagnosis associated with a result_log_detail record. | patient diagnosis result_log_detail | L |  |
| order_log | Contains metadata associated with patient’s orders. | patient staff facility procedure visit elab_order insurance_policy patient_case firm | L |  |
| order_log_detail | Flexible metadata values associated with patient's orders. | patient order_log_detail order_log | L |  |
| order_log_detail_cpt_code | CPT codes associated to order_log_detail. | patient order_log_detail order_log | L |  |
| order_log_note | Notes associated with a patient's order | patient order_log facility staff | L |  |
| order_log_attachment | Metadata about file attachments associated with patient's orders. | patient order_log file_attachment facility | L |  |
| result_log_order | Linking table for results to orders | patient order_log result_log | L |  |
| elab_order | Outbound lab order. Includes all lab types (clinical, pathology, and radiology). There can be multiple tests in one order (see lab_order_test). One row per order. | patient lab_facility staff visit lab | Y |  |
| elab_order_test | Test for an outbound lab order. There can be multiple tests in one order. One row per order/test. | patient elab_order pathology_log diagnosis | Y |  |
| elab_order_result | These are the results or messages back from a lab about an order | patient elab_order firm | Y |  |
| elab_result | Inbound lab results. Includes ALL results, including unassigned and unsolicited results. There can be multiple results for one order or test (see order_number and test_number). One row per result. | patient staff elab_order pathology_log elab_order_test | Y |  |
| lab_request | Contains lab/path requests | patient elab_order pathology_log | N |  |
| lab_result | Contains lab results | patient lab_request lab_note | Y |  |
| lab_attachment | Lab attachments associated with lab requests or lab results | patient lab_result lab_request staff | N |  |
| lab_note | Notes that are created and viewed across all lab specific fields. Can be created within a request for labs or viewed when reviewing lab requests, results, orders and attachments. | patient lab_attachment elab_order lab_result lab_request | Y |  |

## Pathology

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| pathology_log | Pathology specimen result log. Captures entries in all statuses - pending results, results received, and action plan completed | patient facility staff visit procedure_body_location | L |  |
| pathology_log_notification | Patient notification for a pathology log entry. Zero or more notifications per entry. | patient pathology_log | Y |  |
| pathology_log_action | Action for a biopsy log entry. Zero or more actions per biopsy log entry | patient pathology_log | L |  |
| pathology_log_plan | Plan for a biopsy log entry action. One or more plans per action | pathology_log_action patient | L |  |
| cancer_log | Detailed information for cancerous and precancerous pathology results. | patient pathology_log staff referral_contact | L |  |
| cancer_log_pathology_treatment | Pathology log entries for excisions associated as a treatment for a cancer. One row per cancer log entry/pathology log entry. | patient pathology_log cancer_log | L |  |
| cancer_log_problem | Links problems from the problem list to a cancer log entry. | patient problem_list cancer_log | L |  |
| cancer_log_procedure | Links procedures from the procedure log to a cancer log entry. | patient cancer_log procedure_log | L |  |
| cancer_log_medication | Links medications from the medication list to a cancer log entry. | patient medication cancer_log | L |  |
| cancer_log_visit | Cancer interval history | patient visit cancer_log | Y |  |

## Office Flow

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| facility_resource | Facility Resources. Can be either a room, a piece of equipment, or both. One row per facility per resource. | firm | N | PM |
| facility_resource_detail | Relationships between facility resources and locations / providers / appointment types. One row per relationship to either Facility, Provider, or Appointment Type. | appointment_type facility_resource facility staff | N | PM |
| appointment_facility_resource_reservation | Shows all reservations of facility resources by appointments. One row for every instance of an Appointment reserving a Facility Resource. | patient appointment facility_resource | Y | PM |
| facility_resource_utilization_log | Utilization Log Facility Resources, primarily patients checking in and out of rooms. Table including room times and reasons for leaving. One row per room/check in (not per event) | patient facility staff visit facility_resource | Y | PM |

## Prescription

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| rx | Prescriptions written from the application. A prescription can be written as part of a visit, or separate from a visit. | patient facility staff compound_medication diagnosis | Y |  |
| compound_medication | A record describing a compound medication. | compound_medication firm | Y |  |
| glasses_rx | Eyeglass prescriptions. One entry for each prescription, zero or more entries per patient. Linked to visit if the prescription was written as part of a visit. | patient visit facility staff | L | OPHTHALMOLOGY OPTOMETRY |
| contacts_rx | Contact lens prescriptions. One entry for each prescription, zero or more entries per patient. Linked to visit if the prescription was written as part of a visit. | patient visit facility staff | L | OPHTHALMOLOGY OPTOMETRY |
| rgp_contacts_rx | RGP/Hybrid contact lens prescriptions. One entry for each prescription, zero or more entries per patient. Linked to visit if the prescription was written as part of a visit. | patient visit facility staff | L | OPHTHALMOLOGY OPTOMETRY |
| ss_prescriber | Users authorized to generate SureScripts ePrescriptions. | staff staff_facility_rx_registration facility firm | Y |  |
| staff_facility_rx_registration | Staff DEA registrations. Zero or more per staff member/facility. | facility staff | N |  |

## Ophth Pretesting

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| wearing_glasses | Glasses the patient is wearing when presenting for the visit (WRx). Includes visual acuity with the glasses. One or more entries for each prescription. | patient | Y | OPHTHALMOLOGY OPTOMETRY |
| wearing_rgp_contacts | RGP/Hybrid contact lenses the patient is wearing when presenting for the visit (WRx). Includes visual acuity with the contacts. One or more entries for each prescription. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| wearing_contacts | Contact lenses the patient is wearing when presenting for the visit (WRx). Includes visual acuity with the contacts. One or more entries for each prescription. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| refraction | Refraction taken during the eye exam (Arx, MRx, CRx). Includes visual acuity with the refraction. One or more entries for each refraction. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| contacts_trial | Contact lens trial(s) given during the eye exam. Includes visual acuity with the contacts. One entry for each trial. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| rgp_contacts_trial | RGP/Hybrid contact lens trials given during the eye exam. Includes visual acuity with the contacts. One entry for each trial. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| visual_acuity | Visual acuity sets. Distance corrected (Dcc), near corrected (Ncc), distance uncorrected (Dsc), and near uncorrected (Nsc) can be recorded in each set. One or more entries per visual acuity set. NOTE: Visual acuities measured from wearing (WRx) tables get copied into this table, but are not linked. If visual acuity is edited the change does not occur to the source wearing table. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| infant_vision | Infant vision recorded using the CSM method. One entry for each visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| keratometry | Indicate keratometry reading(s) were taken during the eye exam. Zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| keratometry_reading | Keratometry reading for a specific eye. One row per reading, zero or more entries per visit. | patient keratometry | Y | OPHTHALMOLOGY OPTOMETRY |
| binocular | Binocular tests (Near Point Conv., Near Point Accom., Phorias-D, Phorias-N, Vergence, Cross-Cylinder, Relative Accom., AC/A Ratio, Fusion/Stereopsis, Worth, Titmus, Dominance, Accomodative Facility, MEM Retinoscopy) | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| pupil | Pupil exam. Zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| motility | Motility result. Zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| duction | Ductions and versions motility tests. One entry per duction test, zero or more entries per visit. | patient motility | Y | OPHTHALMOLOGY OPTOMETRY |
| cover_test | Cover-Uncover and Alternate Cover motility tests. One entry per test, zero or more entries per visit. | patient motility | Y | OPHTHALMOLOGY OPTOMETRY |
| light_reflex | Light Reflex motility tests. One entry per test, zero or more entries per visit. | patient motility | Y | OPHTHALMOLOGY OPTOMETRY |
| visual_field | Visual Fields test. One entry per test, zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| iop | Intraocular pressure (IOP) reading. One entry per eye/reading, zero or more entries per visit. | patient | Y | OPHTHALMOLOGY OPTOMETRY |
| diagnostic_drops | Dilation performed during the eye exam. One entry per eye/dilation, zero or more entries per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| central_retinal_thickness | Central Retinal Thickness. One entry per test, zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| rnfl_thickness | Retinal nerve fiber layer thickness. One entry per test, zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| pachymetry | Corneal pachymetry thickness. One entry per test, zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| endothelial_counts | Endothelial cell counts. One entry per test, zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| amsler_grid | Amsler grid test. One entry per test, zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |
| color_vision | Color vision tests (Pseudoisochromatic Plates and Farnsworth). Zero or one entry per visit. | patient visit | Y | OPHTHALMOLOGY OPTOMETRY |

## Appointment

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| appointment | Appointments table, one row per appointment. | patient insurance_policy_authorization appointment_reminder facility staff business_unit visit appointment_type financial_category appointment facility_resource insurance_policy referral_contact patient_case firm | Y | PM |
| appointment_log | Appointment log table. One row per event created by changes in a appointment. | patient appointment facility staff | N | PM |
| appointment_authorization | Appointments to insurance policy authorizations mapping table | patient insurance_policy_authorization appointment | Y | PM |
| appointment_waitlist | Patient appointment wait list table. | patient staff appointment_type appointment firm | Y | PM |
| appointment_facility_waitlist | Appointments_waitlist to facility mapping table | patient appointment_waitlist facility | Y | PM |
| appointment_provider_waitlist | Appointments_waitlist to provider mapping table | patient appointment_waitlist staff | Y | PM |
| appointment_reminder | Appointment_reminder table. One row for each time a reminder is sent. | patient appointment staff | Y | PM |
| appointment_insurance_policy | Appointments to patient insurance policy mapping table. | patient appointment insurance_policy staff | Y | PM |
| appointment_attachment | Appointment to file_attachment mapping table. | patient appointment file_attachment | N | PM |
| appointment_insurance_policy_snapshot | Appointments to patient insurance policy mapping history table. | patient appointment insurance_policy | Y | PM |
| appointment_attachment_snapshot | Appointments to patient attachments mapping history table. | patient appointment file_attachment | Y | PM |
| recall_type | Types of recalls associated with an appointment type. One appointment type per recall type. | appointment_type firm | N |  |
| recall | Recall table, also referred to as returning appointments. | patient staff visit appointment_type recall_type appointment | N |  |
| recall_activity | Recall action activity | recall patient staff | Y |  |

## Visit

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| visit | Individual patient encounter. | patient facility staff fee_schedule referral_contact patient_case | Y |  |
| visit_attendee | Additional attendees for a visit. Zero or more entries per visit. | patient visit staff | Y |  |
| visit_finalization_phase | Visit finalization phases. Each row is a visit's finalization phase, status, and date run. | patient visit | Y |  |
| ros | Review of systems. One row per visit/ros item reviewed. Items that are not reviewed do not show up in this table. | patient visit | Y |  |
| vitals | Vitals taken during a visit. One row per visit/vitals measurement set. May enter multiple measurement sets in one visit. | patient visit staff | Y |  |
| bill_cash | Final bill: Charges for self-pay (cash) procedures. NOTE: Preliminary or held visits will not have entries in this table. | patient visit | Y |  |
| final_bill_procedure | Final visit bill: CPT/HCPCS code line item. NOTE: This table records the final bill that was sent upon finalization, including all overrides. Preliminary or held visits will not have entries in this table. | patient visit | Y |  |
| final_bill_diagnosis | Final visit bill: Diagnosis code(s) for each CPT/HCPCS code in the bill_procedure table | patient icd9 icd10 final_bill_procedure | Y |  |
| final_bill_modifier | Final visit bill: Modifier(s) for each CPT/HCPCS code in the bill_procedure table | patient final_bill_procedure | Y |  |
| original_bill_procedure | Originally computed bill before any overrides: CPT/HCPCS code line item. NOTE: This table gets populated upon finalization, preliminary or held visits will not have entries in this table. | patient visit | Y |  |
| original_bill_diagnosis | Originally computed bill before any overrides: Diagnosis code(s) for each CPT/HCPCS code in the original_bill_procedure table | patient original_bill_procedure icd9 | Y |  |
| original_bill_modifier | Originally computed bill before any overrides: Modifier(s) for each CPT/HCPCS code in the original_bill_procedure table | patient original_bill_procedure | Y |  |
| visit_follow_up | Follow up(s) set for a visit. One row per visit/follow up setting. | patient visit | Y |  |
| visit_follow_up_reason | Follow up reason(s) set for a visit follow up. One row per visit follow up/reason. | patient visit_follow_up | Y |  |
| outcome_measurement | Outcome measurement generated from a visit. One row per visit/outcome measurement. May be created as part of a chief complaint, exam, or procedure. Only one of hpi_response_id, exam_element_id, procedure_id, or procedure_body_location_id will be non-null per row. | patient procedure visit exam_element procedure_body_location hpi_response | Y |  |
| visit_quality_measure | Quality measures calculated for a visit. Only for finalized visits. One row per visit/quality measure. | patient facility staff visit quality_measure | Y |  |
| visit_code | All the descriptive codes documented in a patient visit. One visit to many codes. | patient visit | Y |  |

## CC/HPI

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| hpi_response | Chief complaint and History of Present Illness (HPI) taken during a visit. NOTE: All hpi questions are patient-reported, and thus may differ from other structured information inputted by a physician. | patient visit | Y |  |
| hpi_response_body_location | One or more body locations associated with a chief complaint. Body locations are selected using a pre-defined anatomical atlas. | patient hpi_response | Y |  |
| hpi_response_metadata | Additional information collected about each chief complaint. Metadata items are defined and entered for each chief complaint. Records all question, single-input, and single-select responses. | patient hpi_response hpi_option_value | Y |  |
| hpi_response_metadata_selection | Multi-select responses for hpi_response_metadata. One or more rows per hpi_response_metadata_id. | patient hpi_response_metadata | Y |  |
| hpi_follow_up | Records patients following up on a previous visit. Different than a chief complaint collected in the hpi_response_* tables. | patient visit diagnosis | Y |  |
| hpi_follow_up_value | Additional information collected for each follow up. Multi-select responses for each question. One row per follow up/question/value. | patient hpi_follow_up | Y |  |
| hpi_follow_up_measurement | One or more measurements associated with a follow up. Measurements are defined and entered for each diagnosis the patient is following up on. | patient hpi_follow_up | Y |  |
| hpi_option | Contains details about the list of questions asked during assessment. | patient hpi_response | Y |  |
| hpi_option_value | This table contains details associated to the options selected in hpi_option. | patient hpi_option | Y |  |

## Exam

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| exam_set | Exam set performed during a visit. | patient visit | Y |  |
| exam_element | Exam element reviewed during an exam | patient visit exam_set | Y |  |
| exam_element_metadata | Additional data for an exam element. Records all questions, single-input, and single-select responses. | patient exam_element | Y |  |
| exam_element_metadata_selection | Multi-select responses for exam_element_metadata. One or more rows per exam_element_metadata_id | exam_element_metadata patient | Y |  |

## Diagnosis

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| diagnosis | Individual finding/impression during a visit. May be multiple entries per visit. Does not indicate that this is the first time a patient is diagnosed with the condition. Each time a procedure is performed, a diagnosis must first be selected. | patient visit | Y |  |
| diagnosis_ddx | Differential diagnosis. One row per diagnosis/ddx. Zero or more records per diagnosis. | patient diagnosis | Y |  |
| diagnosis_adx | Associated diagnosis. One row per diagnosis/adx. Zero or more records per diagnosis. | patient diagnosis | Y |  |
| diagnosis_cause_dx | Cause diagnosis. One row per diagnosis/cause dx. Zero or more records per diagnosis. | patient diagnosis | Y |  |
| diagnosis_body_location | One or more body locations associated with a diagnosis. | patient diagnosis | Y |  |
| diagnosis_body_location_morphology | One or more morphologies for the given diagnosis body location. | patient diagnosis_body_location | Y |  |
| diagnosis_morphology | One or more morphologies for the given diagnosis. | patient diagnosis | Y |  |
| diagnosis_measurement | One or more measurements associated with a diagnosis. Measurements are defined and entered for each diagnosis. | patient diagnosis | Y |  |
| diagnosis_lab | One or more lab orders for the given diagnosis. Lab results are not recorded in this table. | patient loinc diagnosis staff | Y |  |
| diagnosis_lab_set | One or more lab set orders for the given diagnosis. Lab results are not recorded in this table. | patient diagnosis | Y |  |
| diagnosis_lab_set_lab | One or more lab test for the given diagnosis lab set. Lab results are not recorded in this table. | patient loinc diagnosis_lab_set | Y |  |
| diagnosis_referral | Referral as part of a diagnosis in the VE Room (Referral plan). This table records the provider and specialty that the patient is being referred to. One row per diagnosis/referral contact. NOTE: there will also be an entry in the procedure table with a procedure_name of "Referral". | patient diagnosis referral_contact | Y |  |
| diagnosis_referral_correspondence | Referral correspondence as part of a diagnosis in the VE Room (Referral Correspondence plan). This table records the provider and specialty the correspondence is sent to. One row per diagnosis/referral contact. NOTE: there will also be an entry in the procedure table with a procedure_name of "Referral Correspondence". | patient diagnosis referral_contact | Y |  |

## Procedure

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| procedure | Procedure performed during a visit, associated with a diagnosis. | patient diagnosis | Y |  |
| procedure_body_location | One or more body locations associated with a procedure. Body locations are selected using a pre-defined anatomical atlas. | procedure patient | Y |  |
| procedure_metadata | Additional data recorded for each procedure. May be recorded for the procedure as a whole or for a specific body location. Records all questions, single-input, and single-select responses. Due to processing time requirements this table is refreshed weekly on Saturday. | procedure procedure_body_location patient | Y |  |
| procedure_metadata_selection | Multi-select responses for procedure_metadata. One or more rows per procedure_metadata_id. Due to processing time requirements this table is refreshed weekly on Saturday. | patient procedure_metadata | Y |  |
| procedure_metadata_nested_value | Nested multi-select responses for procedure_metadata_values | patient procedure_metadata_selection | Y |  |
| procedure_mips_quality | Responses for the "MIPS Quality" plan. One row per plan/question/response. Due to processing time requirements this table is refreshed weekly on Saturday. | procedure patient | Y |  |

## Medical Lookup

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| static_body_location | Static lookup table for body_location tables. |  | S |  |
| static_hpi_response | Static lookup table for CC/HPI related medical content: hpi_response table. One row per unique chief complaint. |  | S |  |
| static_hpi_response_metadata | Static lookup table for CC/HPI related medical content: hpi_response_metadata table. One row per unique chief complaint / metadata variable. | static_hpi_response | S |  |
| static_hpi_response_metadata_selection | Static lookup table for CC/HPI related medical content: hpi_response_metadata table. One row per unique chief complaint / metadata variable / metadata value. | static_hpi_response_metadata | S |  |
| static_exam_set | Static lookup table for exam related medical content: exam_set table. One row per unique exam set. |  | S |  |
| static_exam_element | Static lookup table for exam related medical content: exam_set_element table. One row per unique exam element. Elements can be re-used across exam sets, see static_exam_set_element table. |  | S |  |
| static_exam_set_element | Static lookup table for exam related medical content: exam_set_element table. Identifies exam elements that are associated with each exam set. One row per exam set / element. | static_exam_set static_exam_element | S |  |
| static_exam_element_metadata | Static lookup table for exam related medical content: exam_element_metadata table. One row per unique exam set / element / metadata variable. | static_exam_element | S |  |
| static_exam_element_metadata_selection | Static lookup table for exam related medical content: exam_element_metadata_selection table. One row per unique exam set / element / metadadata variable / metadata value. | static_exam_element_metadata | S |  |
| static_diagnosis | Static lookup table for diagnosis related medical content: diagnosis table. One row per unique diagnosis. |  | S |  |
| static_diagnosis_measurement | Static lookup table for diagnosis measurement medical content: hpi_follow_up_measurement and diagnosis_measurement tables. One row per unique diagnosis / measurement. | static_diagnosis | S |  |
| static_diagnosis_measurement_title | Static lookup table for diagnosis measurement medical content: hpi_follow_up_measurement and diagnosis_measurement tables. Titles associated with select numeric values, if applicable. One row per unique diagnosis / measurement / value title. | static_diagnosis_measurement | S |  |
| static_diagnosis_morphology | Static lookup table for diagnosis medical content: diagnosis_morphology and diagnosis_body_location_morphology tables. NOTE: users can add custom morphologies, this table only includes the default morphologies. One row per unique diagnosis / morphology. | static_diagnosis | S |  |
| static_procedure | Static lookup table for procedure medical content: procedure table. One row per unique procedure. |  | S |  |
| static_procedure_metadata | Static lookup table for procedure medical content: procedure_metadata table. One row per unique procedure / metadata variable. | static_procedure | S |  |
| static_procedure_metadata_selection | Static lookup table for procedure medical content: procedure_metadata_selection table. One row per unique procedure / metadata variable / metadata value. | static_procedure_metadata | S |  |
| static_outcome_measurement | Static lookup table for outcome medical content: outcome_measurement table. One row per unique outcome measurement. |  | S |  |
| static_pathology_result | Static lookup table for pathology medical content: pathology_log table. One row per unique pathology result. |  | S |  |
| static_pathology_action | Static lookup table for pathology medical content: pathology_log_action table. One row per unique pathology action. |  | S |  |
| static_pathology_plan | Static lookup table for pathology medical content: pathology_log_plan table. One row per unique pathology plan. |  | S |  |

## PM Financials

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| bill_diagnosis_pm | Bill diagnosis table maps the diagnosis to bills. One row per diagnosis per bill. | patient bill | N | PM |
| custom_code | Custom codes for procedures configured by the practice. One row per per firm per custom code. | firm | Y | PM |
| custom_cpt_code | Custom codes for procedures configured by the practice. One row per firm per custom code. Includes codes that haven't been used | firm | Y | PM |
| custom_code_procedure_link | Custom code to procedure mapping table. A custom code can be linked to more than one procedure. One row per procedure per custom code. | procedure custom_code patient | Y | PM |
| charges | Charges provide details on charges rendered for services. One row per charge item per patient for posted charges only. Bill item is represented by the bill item id. Non-bill charges will not have a bill_item_id. | patient provider_level_adjustment patient_product package_sale batch appointment package_item_sale bill_assignee billing_quote business_unit fee_schedule insurance_policy bill_item firm facility division custom_non_bill_code code_category bill payer_address staff bill_insurance payer | N | PM |
| product_sales | Product sales table includes data related to charges including state and local taxes. One row per product charge item per patient. The MM Inventory products are not included in this table. | patient facility staff business_unit division custom_non_bill_code code_category | N |  |
| unposted_charges | Unposted charges includes bill charges that have not yet been posted. One row per bill item per patient. Non-bill charges are not included. | patient facility staff business_unit payer division custom_non_bill_code bill_item financial_category | N | PM |
| unbilled_posted_charges | Unbilled posted charges includes charges that have been posted but have not been submitted to the responsible party (either patient or payer). One row per bill item per patient. | patient patient_business_unit_setting facility staff business_unit payer division custom_non_bill_code bill_item | N | PM |
| payments_posted | Payments Posted table provide details on payments made for services rendered. One row per payment posted for patient. This table represents payments that have been allocated to a service and may not be representative of all payments received. | patient provider_level_adjustment package_sale batch package_item_sale bill_assignee billing_quote business_unit fee_schedule insurance_policy custom_payment_method bill_item firm facility division custom_non_bill_code code_category bill payer_address staff bill_insurance payer | N | PM |
| era_received | Electronic Remittances Advice (ERA) Received table includes payments that have or have not yet been accepted into ModMed PM. Some of the payments in this table may not be reflected in payments received as they have not yet been accepted by the practice. One row represents ERA payment received per payer. | business_unit payer facility firm | N | PM |
| transfer_funds | This report is a view of patient payment transactions specific to external credit, patient to patient, or business unit transfers. One row represents payments moved per patient via external credit, patient to patient, or business unit transfer. | patient facility staff business_unit code_category firm | N | PM |
| provider_level_adjustment | Provider Level Adjustment includes data for provider-level adjustments derived from payer payments. Provider level adjustments can be informational only, offset charge, or post to service line. The adjustment type selected will determine how adjustment is linked to additional tables. One row per adjustment per payer payment. | business_unit payer facility staff | N | PM |
| patient_statement | A list of statements generated and sent to patients, for a specific firm. One row per patient per firm. | patient business_unit firm | N | PM |
| patient_statement_charge | Mapping table that links individual charges on a patient statement with charges table. One row per patient per charge. | patient patient_statement | N | PM |
| patient_payments_unposted | Patient Payments unallocated table reflects patient payment transactions that have been received but have not been fully posted to a specific charge item. This table includes payments that have been partially posted or not posted. One row per transaction per patient per business unit. | patient facility staff business_unit package_sale appointment custom_payment_method | N | PM |
| payer_adjustments | Payer Adjustment includes data for payer adjustment details posted to bill items. One row per adjustment per bill item. Practice Financials -> Payer Payments -> Transaction -> Payment Transaction | patient era_received package_sale package_item_sale billing_quote business_unit fee_schedule insurance_policy bill_item firm facility division custom_non_bill_code code_category bill payer_address staff bill_insurance payer | N | PM |
| payer_adjustments_detail | Payer Adjustment includes data for payer adjustment details posted to bill items. One row per adjustment per CARC and RARC codes. | patient claim_bill_item claim bill_item firm | N | PM |
| payer_adjustments_rarc | RARC code information associated with the payer_adjustments table. | payer_adjustments patient staff | N | PM |
| payer_payments_unposted | Payer Payment Unposted table provides details about payer payments which have not been posted to service. One row per payer payment per check. | staff facility business_unit payer firm | N | PM |
| transaction_settlement | Transaction Settlements for Payments submitted to Payment Processor. Includes details about transaction fees, processing fees, and interchange fees. | business_unit | N | PM |
| transaction_settlement_refund | Transaction Settlements for Refunds submitted to Payment Processor. Includes details about transaction fees, processing fees, and interchange fees. | business_unit transaction_settlement | N | PM |
| payments_received | Payments Received details all payments that have been received and accepted into ModMed PM regardless of payment posting status. One row per payment by busines unit for either payers or patients. | patient bill_assignee facility staff business_unit payer package_sale batch appointment code_category custom_payment_method | N | PM |
| patient_adjustments | Patient adjustment includes patient adjustment details for bill items or charges. One row per adjustment. | patient bill facility staff billing_quote business_unit package_sale division custom_non_bill_code fee_schedule code_category custom_patient_adjustment_code bill_item package_item_sale firm | Y | PM |
| claim | Claim table contains all claims created by the practice. One row per claim identifier. | patient bill_assignee staff bill_insurance payer firm | N | PM |
| claim_bill_item | Claim bill item table provides additional details about bill items linked to claims. One row per bill item id. | bill_assignee patient bill_insurance division claim bill_item | N | PM |
| claim_log | Contains a claim's history of events and status changes. | patient claim staff firm | N | PM |
| claim_bill_item_denial_category | claim_bill_item to denial_category mapping table. | patient claim claim_bill_item | N | PM |
| claim_submission | claim_submission table provides information on claim submissions. One row per claim submission | patient payer_address claim | N | PM |
| claim_submission_bill_item | claim_submission_bill_item table links claim submissions to bill items. One row per claim submission bill item | patient claim_submission bill_item | N | PM |
| claim_submission_change | claim_submission_change table provides attribute-level change submissions for claims. One row per claim submission change | patient claim_submission claim | Y | PM |
| bill | Bill table contains all bills generated at the practice. One row per bill. | patient bill_assignee bill facility staff billing_quote business_unit visit package_sale referral_institution division financial_category appointment fee_schedule referral_contact patient_case firm | N | PM |
| bill_item | Bill item table provides additional details about the individual procedures, services, or products linked to the bill. A flag indicates whether a bill item has been deleted. One row per bill item id. | patient bill code_category | N | PM |
| pm_note | PM note table includes all notes written by the practice and associated with PM tables. One row per note. | patient bill patient_statement facility staff | N | PM |
| bill_item_modifier | Bill Item modifier provides details about the billing modifiers associated with each bill item. One row per modifier per bill item. | patient bill_item | N | PM |
| bill_item_diagnosis | Bill Item diagnosis table maps the diagnosis pointer to individual bill items. One row per diagnosis per bill item. | patient bill_item | N | PM |
| bill_insurance | Bill insurance tabe maps patient insurance policies to bills. A bill can have multiple insurance policies. One row per insurance | patient bill insurance_policy_authorization staff fee_schedule insurance_policy | N | PM |
| bill_insurance_timely_filing | Bill insurance timely filing table captures timely filing information for bills. Dates are calculated using the date of service (DOS). One row per timely filing. | bill_insurance patient | N | PM |
| bill_assignee | Staff member assigned to bill. One row per bill_assignee per bill_id. For unassigned bills this field will be empty. This table will be deprecated in release 1.24. Use table financial_assignee instead. | staff firm | N | PM |
| financial_assignee | Staff member assigned to bill. One row per financial_assignee per bill_id. For unassigned bills this field will be empty. | staff firm | N | PM |
| production_summary | Production summary table summarizes the charges, payments, and patient and payer writeoff adjustments as well as provider level adjustments, specifically 'post to service line' and 'offset charge'. This table does not include 'ignore' or 'transfer' payer adjustments as well as informational provider level adjustments because these adjustments to do not impact the total balance. One row per item. | patient provider_level_adjustment package_sale batch package_item_sale bill_assignee billing_quote business_unit charges patient_adjustments fee_schedule insurance_policy custom_payment_method payer_adjustments bill_item firm payments_posted facility division custom_non_bill_code code_category bill payer_address staff bill_insurance payer | Y | PM |
| accounts_receivable | The accounts receivable table provides details on outstanding balances for services. To be included in this table, a charge item must have a balance associated with it. The bill item id represents a charge item, and a non-bill charge is represented by one row per charge item per patient. | patient bill patient_business_unit_setting pm_note facility staff business_unit payer division referral_institution custom_non_bill_code fee_schedule code_category referral_contact bill_item firm | N | PM |
| code_category | Code Categories can be associated to charges, payments, cpts and custom codes. One row represents a code category per firm. | firm | N | PM |
| code_category_item | One row represents a category item within a category. | code_category firm | N | PM |
| code_category_patient_payment_log | Patient payments to code category transaction history. One row represents a patient payment to code category transaction. | patient business_unit code_category staff | Y | PM |
| batch | Batches are used to associate payments, charges, and refunds together in order to reconcile funds and close financials on a specific date. One row per batch per business unit. | business_unit staff | Y | PM |
| batch_payment_refund_amount | Stores counted amounts from the Payments and Refunds section under Batch Details. One row per payment/refund per batch. | batch | N | PM |
| billing_quote | Billing Quote settings. One row per quote per patient. | patient facility staff business_unit fee_schedule insurance_policy firm | N | PM |
| billing_quote_verbiage | Textual data associated with a billing quote. One row per verbiage. | firm | N | PM |
| billing_quote_verbiage_link | Linking table between billing quotes and verbiage. One row per verbiage per billing quote. | patient billing_quote_verbiage billing_quote | N | PM |
| billing_quote_charge | Charges associated with a billing quote. One row per charge per billing quote. | patient product billing_quote_charge_discount billing_quote custom_non_bill_code custom_code code_category_item | N | PM |
| billing_quote_charge_discount | Discounts associated with a billing quote charge. | firm | N | PM |
| custom_patient_adjustment_code | Custom adjustment codes for patient outstanding balances. | firm | N | PM |
| custom_payment_method | Custom Payment Methods. | firm | N | PM |
| custom_non_bill_code | Custom product and non bill charges codes for PM enabled firms. | firm | N | PM |
| custom_non_bill_code_facility | Custom_non_bill_code to facility mapping table. | custom_non_bill_code facility | N | PM |
| appointment_missing_charges | These are appointments that don't have an associated bill with the same date of service, service location, and provider. The following appointments are excluded: appointments with the status of cancelled or no show, appointments which are for today or in the future. One row per appointment id per patient. | patient facility staff business_unit visit payer appointment | N | PM |
| refunds | Data for all patient and payer refunds. One row per refund id. In Practice Management there isn’t a direct link between a charge and a specific refund. To issue a refund, staff must reverse allocated payments from the charge. Once funds are considered unallocated, then the staff can proceed with the refund. Two workflows: - Patient->Patient Financials->Payment Transaction->Create Refund - Practice Financials->Payer Payments->Payment Transaction->Payer Refunds | patient facility staff business_unit payer package_sale batch appointment code_category custom_payment_method | N | PM |
| patient_collections_setting | Patient Pre-Collection firm level setting. | custom_patient_adjustment_code firm_group staff firm | N | PM |
| patient_collections_access_restriction | Mapping table for Patient Pre-Collection when Do Not Allow is selected and for Bulk Adjustment Settings Users/Groups. | firm_group patient_collections_setting staff | N | PM |

## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| staff_preference | Staff Preferences. One row per staff member. | staff | N |  |
| staff_preference_assign_pathology_results | Staff Preferences. One row per Pathology Result Assignee, where assignees can be Staff or a Staff Group. | staff | N |  |
| staff_preference_attendee | Staff Preferences. One row per Preferred Attendee | staff | N |  |
| staff_preference_biller | Staff Preferences. One row per Preferred Biller | staff | N | PM |
| staff_preference_facility | Staff Preferences. One row per Preferred Facility. | facility staff | N |  |
| staff_preference_follow_up_reason | Staff Preferences. One row per Preferred Follow Up Reason | staff | N |  |
| staff_preference_hpi | Staff Preferences. One row per Preferred Hpi | staff | N |  |
| staff_preference_medical_domain | Staff Preferences. One row per Preferred Medical Domain | staff | N |  |
| staff_preference_patient_chief_complaint | Staff Preferences. One row per Preferred Patient Chief Complaint | staff | N |  |
| staff_preference_provider | Staff Preferences. One row per Preferred Provider | staff | N |  |
| staff_preference_room | Staff Preferences. One row per Preferred Room | facility_resource facility staff | N |  |

## Inventory

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| product | Table containing all products and corresponding manufacturer and package information | manufacturer product_category staff firm | N |  |
| stock | Stocking options for firm products | product cabinet firm | N |  |
| cabinet | Table containing all system and firm level products | staff facility firm | N |  |
| patient_product | Table containing all system and firm level products | stock product staff cabinet | N | PM |
| manufacturer | Table containing all system and firm level manufacturers | staff firm | N |  |
| product_category | Table containing all firm level product categories | staff firm | N |  |
| package | Table containing info on Packages configured in Firm Admin. | fee_schedule facility firm | N | PM |
| package_item | Table containing info on the Items in a Packages configured in Firm Admin. | custom_non_bill_code product custom_code package | N | PM |
| package_location | List of Locations (Facilities) at which a Package is available. | facility package | N | PM |
| package_sale | Packages that have been sold to Patients | patient staff facility package business_unit division financial_category | Y | PM |
| package_item_sale | Itemized breakdown of Patient Packages | patient product facility package staff business_unit package_sale division custom_non_bill_code custom_code financial_category | Y | PM |
| package_item_sale_utilization | Utilization of Sold Package Items | patient product facility package staff business_unit package_sale division custom_non_bill_code custom_code package_item_sale financial_category | Y | PM |
| package_sale_to_bill | Bridge table between `package_sale` and `bill` | patient bill package_sale staff | N | PM |
| package_sale_to_appointment | Bridge table between `package_sale` and `appointment` | patient appointment package_sale | N | PM |
| stock_transaction | Tracks changes in stock due to product orders, patient visits, or reconciliations | stock product cabinet firm | N |  |
| stock_reconciliation | Reconciliations against inventory stock audits | product facility staff stock stock_transaction cabinet | N |  |
| cabinet_preference | Staff preferred cabinets | staff cabinet | N |  |
| product_facility_pricing | Product pricing for specific locations | product facility | N |  |
| product_vendor | Product vendor details | firm | N |  |
| product_order_item | Items in a Product Order | product_vendor product facility staff | N |  |

## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| consent_form | Consent forms are documents that can be created by a firm or a staff member in order to enter an agreement with a patient for care, treatment, or services. One patient to many forms. | staff firm | N |  |
| consent_form_facility | Facility specific patient waiver forms. | facility consent_form | N |  |
| consent_form_patient | Patient assigned consent form table. | patient consent_form | N |  |

## Office Flow

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| task | Task table contains all the tasks created in Ema. | patient facility staff visit business_unit task appointment result_log firm | Y |  |
| task_note | Contains the notes related to a task. | patient task task_note | Y |  |
| task_attachment | This table contains the relationship ids between a task and its attachments. | patient task file_attachment | N |  |
| task_fax_inbound | This table contains the relationship ids between a task and its faxes received. | patient task fax_inbound | N |  |
| task_staff_assignee | This table contains the list of persons assigned to a task. | patient task staff | N |  |
| task_group_assignee | This table contains the list of groups assigned to a task. | patient task firm_group | N |  |
| task_order_log | Links tasks with order log records | patient task order_log | N |  |
| task_additional | Contains additional FKs to Task table. | intra_mail task chart_note patient | N |  |

## Appointment

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| calendar_event | Calendar event table. One row per event date, per facility, and per provider. | staff facility firm | L | PM |

## Patient

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| intra_mail | intra_mail table contains all the IntraMail messages created in Ema. | patient staff visit chart_note lab_request firm | Y |  |
| intra_mail_recipient | Links IntraMail messages with the message recipients. | intra_mail firm_group patient staff | N |  |
| merge_patient | Data for a patient merge operation. | patient staff firm | N |  |

## PM Financials

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| pre_collections | Pre-collections are tasks for patients with an overdue balance who are at risk of that balance being sent to a collection agency. | patient facility staff business_unit task appointment | N | PM |
| pre_collections_charge_detail | Charge specific amounts that make up the pre_collections.overdue_balance | patient facility business_unit division task pre_collections | N | PM |

## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| region | A region is a defined administrative area comprised of facilities and staff members, used to restrict access to patient data outside that specific region. | staff firm | N |  |
| staff_region | Staff members that are assigned to a region | staff region | N |  |
| restricted_chart_event_log | Each rows logs changes to patients restricted status and when a staff member accesses a restricted patient chart or region. | patient staff | Y |  |
| restricted_chart_notifications | Staff members or firm groups assigned to receive notifications when a restricted chart is accessed | firm_group staff firm | N |  |

## PM Financials

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| claim_scrub_rule | Contains all the Scrub Rules created in Ema. | bill_assignee business_unit staff firm | N | PM |
| claim_scrub_rule_payer | Contains the relationship between Claim Scrub Rules and Payers. | claim_scrub_rule payer firm | N | PM |
| claim_scrub_rule_primary_biller | Contains the relationship between Claim Scrub Rules and Primary Billers. | claim_scrub_rule staff firm | N | PM |
| claim_scrub_rule_primary_provider | Contains the relationship between Claim Scrub Rules and Primary Billers. | claim_scrub_rule staff firm | N | PM |
| claim_scrub_rule_service_location | Contains the relationship between Claim Scrub Rules and its Service Locations. | claim_scrub_rule facility firm | N | PM |
| claim_scrub_rule_policy_type | Contains the relationship between Claim Scrub Rules and its Policy Types. | claim_scrub_rule firm | N | PM |
| claim_scrub_rule_payer_plan | Contains the relationship between Claim Scrub Rules and its Payer Plans. | claim_scrub_rule payer payer_plan firm | N | PM |
| claim_scrub_rule_division | Contains the relationship between Claim Scrub Rules and Divisions. | claim_scrub_rule division firm | N | PM |
| claim_scrub_rule_referral_contact | When option 'Require Referring Provider' is set to 'Yes', allows to set the relationship between a Scrub Rule and its Referring Provider(s). | claim_scrub_rule referral_contact referral_institution firm | N | PM |
| claim_scrub_rule_procedure | Contains the relationship between Claim Scrub Rules and its Procedure Codes And Modifiers | claim_scrub_rule firm | N | PM |
| claim_scrub_rule_procedure_code_category | Contains the relationship between a Claim Scrub Rules Procedure and its associated code categories. | claim_scrub_rule code_category claim_scrub_rule_procedure firm | N | PM |
| claim_scrub_rule_diagnosis | Contains the relationship between a Claim Scrub Rules and its associated Diagnosis Codes. | claim_scrub_rule firm | N | PM |
| claim_payer | Contains relationship between Claims and ERAs | era_received patient payer claim firm | N | PM |
| custom_claim_scrub_rule | Contains all the Scrub Rules created in Ema. | bill_assignee business_unit firm | N | PM |

## Practice

| Table | Description | Relationships (FK -> table) | Longitudinal | Vertical |
|---|---|---|---|---|
| staff_payer_identifiers | Staff member specific payer information | payer staff | N | PM |
| staff_society_associations | Staff member's societies and associations | staff | N | PM |
| staff_state_industrial_accident | Staff member's industrial accident state information | staff | N | PM |
| staff_state_license | Staff member's state license information | staff | N |  |
| staff_state_provider | Staff member's associated provider information | staff | N |  |
