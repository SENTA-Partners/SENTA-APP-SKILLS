# Column Dictionary: Patient (904 columns)


## patient

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_id | patient table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| primary_provider_id | staff table id | string | True | 20 | Primary Provider |  |
| primary_care_provider_id | referral_contact table id | string | True | 20 | Primary Care Provider (Referral contact) |  |
| referring_provider_id | referral_contact table id. *Note*: This column will be deprecated on our next release. Please join to `patient_referring_provider` on `patient_id`. Relationship will be one to many. | string | True | 20 | Referring Provider (Referral contact) | True |
| financial_category_id | financial_category table id (PM Column) | string | True | 20 |  |  |
| patient_created_by_id | id associated with the creation of a patient record | string | True | 20 |  |  |
| last_appointment_id | Appointment table id of the patient's last appointment | string | True | 20 |  |  |
| next_appointment_id | Appointment table id of the patient's last appointment | string | True | 20 |  |  |
| nursing_room_facility_id | facility table id | string | True | 20 |  |  |
| universal_identifier | Single ID users can use to login into any of the firms they are associated with. | string | True | 100 |  |  |
| universal_identifier_type | Type of universal identifier. | string | True | 100 |  |  |
| last_name | Last Name | string | True | 100 |  |  |
| first_name | First Name | string | True | 100 |  |  |
| middle_name | Middle Name | string | True | 50 |  |  |
| prefix | Name - Prefix | string | True | 50 |  |  |
| suffix | Name - Suffix | string | True | 50 |  |  |
| nick_name | Nick Name | string | True | 50 |  |  |
| marital_status | Marital Status | string | True | 50 | UNSPECIFIED, MARRIED, LIVING_TOGETHER |  |
| previous_name | Previous Name | string | True | 200 |  |  |
| employment_status | Patient's employment status | string | True | 25 | UNEMPLOYED FULL_TIME_STUDENT PART_TIME_STUDENT RETIRED UNKNOWN EMPLOYED OTHER |  |
| date_of_birth | Date of Birth | timestamp | True |  |  |  |
| age_in_years | Age of the patient, in years. | int | True |  |  |  |
| age_in_months | Age of the patient, in years. | int | True |  |  |  |
| birth_city | Birth City | string | True | 255 |  |  |
| birth_state | Birth State | string | True | 50 |  |  |
| birth_zipcode | Birth Zipcode | string | True | 50 |  |  |
| birth_country | Birth Country | string | True | 30 |  |  |
| deceased | If patient is deceased | boolean | True |  |  |  |
| date_of_death | Date of Death | timestamp | True |  |  |  |
| sex | Patient's birth sex | string | True | 20 | MALE, FEMALE, etc. |  |
| sexual_orientation | Patient's sexual orientation. | string | True | 20 | ASEXUAL BISEXUAL HETEROSEXUAL HOMOSEXUAL NON_CONFORM_GENDER OTHER UNDISCLOSED UNKNOWN UNSPECIFIED |  |
| sexual_orientation_other_text | Free text field for when patient selects other as sexual orientation. | string | True | 100 |  |  |
| language | Language | string | True | 75 | English, Spanish, French, etc. |  |
| language_code | Language code | string | True | 4 | en, es, fre, etc. |  |
| race_american_indian_or_alaska_native | Race - American Indian or Alaska Native | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race_asian | Race - Asian | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race_black_african_american | Race - Black or African American | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race_native_hawaiian_pacific_islander | Race - Native Hawaiian or Other Pacific Islander | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race_white | Race - White | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race_other | Race - Other | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race_unknown | Race - unknown | boolean | True |  | Based on HL7-0005, see patient_race table for more detailed race selections. |  |
| race | Collapsed race for the patient (derived from the race_* boolean flags). For patient's with a single known race, this column reflects that. If the patient has more than one race, this column will be marked OTHER. If no races are recorded, this will column will be marked UNKNOWN. | string | True | 50 | AMERICAN_INDIAN_OR_ALASKA_NATIVE ASIAN BLACK_OR_AFRICAN_AMERICAN NATIVE_HAWAIIAN_OR_OTHER_PACIFIC_ISLANDER WHITE OTHER UNKNOWN |  |
| ethnic_group | Ethnic group | string | True | 30 | HISPANIC_OR_LATINO, NOT_HISPANIC_OR_LATINO, etc. |  |
| gender_identity | Patient's gender identity. | string | True | 20 | FEMALE FEMALE_TO_MALE GENDER_QUEER MALE MALE_TO_FEMALE OTHER UNDISCLOSED UNSPECIFIED NON_CONFORM_GENDER |  |
| gender_identity_other_text | Free text field for when patient selects other as gender identity. | string | True | 100 |  |  |
| patient_preferred_pronoun | Patient's preferred pronoun. | string | True | 20 | HE_HIM_HIS SHE_HER_HERS THEY_THEM_THEIR ZE_ZIR_ZIR XIE_HIR_HIR CO_CO_COS EN_EN_ENS EY_EM_EIR YO_YO_YOS VE_VIS_VER |  |
| preferred_contact_method | Preferred Contact Method. May have a null value. | string | True | 100 | PHONE, EMAIL, etc. |  |
| emergency_contact_name | Emergency Contact Full Name | string | True | 300 |  |  |
| emergency_contact_phone_number | Emergency Contact Phone Number | string | True | 30 |  |  |
| receive_appointment_text_reminders | Patient indicates whether they would like to receive text reminders on their most recently modified appointment | boolean | True |  |  |  |
| last_appointment_date | Date of patient's last appointment | timestamp | True |  |  |  |
| last_appointment_type | Type of patient's last appointment | string | True | 50 |  |  |
| next_appointment_date | Date of patient's next appointment | timestamp | True |  |  |  |
| next_appointment_type | Type of patient's next appointment | string | True | 50 |  |  |
| spouse_name | Spouse Full Name | string | True | 300 |  |  |
| spouse_phone_number | Spouse Phone Number | string | True | 30 |  |  |
| caretaker_name | Caretaker Full Name | string | True | 300 |  |  |
| caretaker_phone_number | Caretaker Phone Number | string | True | 30 |  |  |
| preferred_phone | Preferred Phone. May have a null value. | string | True | 20 | HOME WORK MOBILE GUARANTOR_HOME OTHER |  |
| mobile_phone_number | Mobile Phone Number | string | True | 50 |  |  |
| home_phone_number | Home Phone Number | string | True | 50 |  |  |
| work_phone_number | Work Phone Number | string | True | 50 |  |  |
| home_fax_phone_number | Home Fax Phone Number | string | True | 50 |  |  |
| work_fax_phone_number | Work Fax Phone Number | string | True | 50 |  |  |
| emergency_phone_number | Emergency Phone Number | string | True | 50 |  |  |
| pager_phone_number | Pager Phone Number | string | True | 50 |  |  |
| other_phone_number | Other Phone Number | string | True | 50 |  |  |
| preferred_phone_number | Patient's Preferred Phone Number | string | True | 50 |  |  |
| preferred_phone_number_type | Preferred Phone Type. May have a null value. | string | True | 20 | HOME WORK MOBILE GUARANTOR_HOME OTHER |  |
| ok_to_leave_detailed_message | Is it OK to leave a detailed message? | boolean | True |  |  |  |
| email | Email address | string | True | 255 |  |  |
| alternate_email | Alternate email address | string | True | 255 |  |  |
| email_opt_in | Opt in to email notifications | boolean | True |  |  |  |
| declined_email_address | Firm level configuration requesting if patient agrees to provide email address | boolean | True |  |  |  |
| home_street1 | Home Address Street 1 | string | True | 255 |  |  |
| home_street2 | Home Address Street 2 | string | True | 255 |  |  |
| home_city | Home Address City | string | True | 255 |  |  |
| home_state | Home Address State | string | True | 50 |  |  |
| home_zipcode | Home Address Zipcode | string | True | 50 |  |  |
| home_country | Home Address Country | string | True | 50 |  |  |
| home_start_date | Home address start date | timestamp | True |  |  |  |
| home_end_date | Home address end date | timestamp | True |  |  |  |
| seasonal_street1 | Seasonal Address Street 1 | string | True | 255 |  |  |
| seasonal_street2 | Seasonal Address Street 2 | string | True | 255 |  |  |
| seasonal_city | Seasonal Address City | string | True | 255 |  |  |
| seasonal_state | Seasonal Address State | string | True | 50 |  |  |
| seasonal_zipcode | Seasonal Address Zipcode | string | True | 50 |  |  |
| seasonal_country | Seasonal Address Country | string | True | 30 |  |  |
| seasonal_start_date | Seasonal address start date | timestamp | True |  |  |  |
| seasonal_end_date | Seasonal address end date | timestamp | True |  |  |  |
| primary_type | Primary Address Type | string | True | 50 |  |  |
| primary_street1 | Primary Address Street 1 | string | True | 255 |  |  |
| primary_street2 | Primary Address Street 2 | string | True | 255 |  |  |
| primary_city | Primary Address City | string | True | 255 |  |  |
| primary_state | Primary Address State | string | True | 50 |  |  |
| primary_zipcode | Primary Address Zipcode | string | True | 50 |  |  |
| primary_country | Primary Address Country | string | True | 30 |  |  |
| primary_start_date | Primary address start date | timestamp | True |  |  |  |
| primary_end_date | Primary address end date | timestamp | True |  |  |  |
| employer_name | Employer Name | string | True | 100 |  |  |
| occupation | Occupation | string | True | 255 |  |  |
| occupation_code | Occupation Code | string | True | 4 |  |  |
| industry | Industry | string | True | 255 |  |  |
| industry_code | Industry Code | string | True | 4 |  |  |
| mrn | MRN | string | True | 20 |  |  |
| pqrs_id | PQRS Patient Identifier | string | True | 20 |  |  |
| established_patient | Established Patient | boolean | True |  |  |  |
| rx_history_consent | Rx History Consent. May have a null value. | string | True | 1 | Y: Yes, N: No, P: Prescriber only |  |
| last_visit_date | Last Visit Date | timestamp | True |  |  |  |
| last_payment_plan_status | Indicates the status of a patient's most recent payment plan | string | True | 30 | DELINQUENT CANCELLED COMPLETED ACTIVE INACTIVE PENDING |  |
| medicare_number | Medicare Number | string | True | 30 |  |  |
| medicaid_number | Medicaid Number | string | True | 25 |  |  |
| immunization_registry_status | Immunization Registry Status | string | True | 20 |  |  |
| immunization_registry_status_effective_date | Immunization Registry Status Effective Data | timestamp | True |  |  |  |
| immunization_registry_protection_indicator | Immunization Registry Protection Indicator | boolean | True |  |  |  |
| immunization_registry_protection_indicator_effective_date | Immunization Registry Protection Indicator | timestamp | True |  |  |  |
| immunization_registry_publicity_setting | Immunization Registry Publicity Setting | string | True | 4 | See Appendix A |  |
| immunization_registry_publicity_setting_effective_date | Immunization Registry Publicity Setting Effective Date | timestamp | True |  |  |  |
| pms_id | PMS ID | string | True | 50 |  |  |
| pms_id_type | PMS ID Type | string | True | 100 |  |  |
| archived | If the patient is archived | boolean | True |  |  |  |
| portal_enabled | Patient Portal Enabled | boolean | True |  |  |  |
| username | Username | string | True | 50 |  |  |
| last_login | Time of last login to the patient portal | timestamp | True |  |  |  |
| good_login_count | Number of good logins to the patient portal | int | True |  |  |  |
| bad_login_count | Number of bad logins to the patient portal | int | True |  |  |  |
| account_locked | If the patient's portal account is locked | boolean | True |  |  |  |
| representative_portal_enabled | Representative Account Enabled | boolean | True |  |  |  |
| representative_last_name | Patient Representative Last Name | string | True | 100 |  |  |
| representative_first_name | Patient Representative First Name | string | True | 100 |  |  |
| representative_middle_name | Patient Representative Middle Name | string | True | 100 |  |  |
| representative_username | Username | string | True | 50 |  |  |
| representative_last_login | Time of last login to the patient representative portal | timestamp | True |  |  |  |
| representative_account_locked | If the patient's portal account is locked | boolean | True |  |  |  |
| sticky_note | Patient's latest sticky note | string | True | -1 |  |  |
| sticky_note_last_edit | Last date note was edited | timestamp | True |  |  |  |
| last_menstrual_period | Last Menstrual Period | timestamp | True |  |  |  |
| last_pelvic_exam | Last Pelvic Exam | timestamp | True |  |  |  |
| last_mammogram | Last Mammogram | timestamp | True |  |  |  |
| last_pap_smear | Last Pap Smear | timestamp | True |  |  |  |
| gravida | Gravida | int | True |  |  |  |
| para | Para | int | True |  |  |  |
| tab | Tab | int | True |  |  |  |
| sab | Sab | int | True |  |  |  |
| gest_age_birth | Gestational Age at Birth (in weeks) | int | True |  |  |  |
| birth_lbs | Birth Weight (lbs) | int | True |  |  |  |
| birth_oz | Birth Weight (oz) | int | True |  |  |  |
| maternal_illness | Maternal illness during pregnancy | string | True | 1000 |  |  |
| forceps_delivery | Forceps delivery | boolean | True |  |  |  |
| medication_other | Other Medications (free-text) | string | True | -1 |  |  |
| allergy_nkda | No known drug allergies | boolean | True |  |  |  |
| allergy_other | Other Allergies (free-text) | string | True | -1 |  |  |
| smoking_status | Smoking Status | string | True | 40 |  |  |
| smoking_start_date | Smoking start date | timestamp | True |  |  |  |
| smoking_quit_date | Smoking quit date | timestamp | True |  |  |  |
| smoking_packs_per_day | Smoking - number of packs per day | string | True | 5 | 0, < 1, 1, 2, ... |  |
| smoking_total_years | Smoking - Total years smoking | string | True | 5 | 0, < 1, 1, 2, ... |  |
| smoking_additional_details | Smoking - Additional Details | string | True | 1000 |  |  |
| alcohol_screening | How many times in the past year have you had 5 or more drinks in a day for men, or 4 or more drinks in a day for women or any adult older than 65? | int | True |  |  |  |
| exercise_status | How often do you exercise? May have null value. | string | True | 30 | UNSPECIFIED SEVERAL_TIMES_A_DAY ONCE_A_DAY A_FEW_TIMES_A_WEEK A_FEW_TIMES_A_MONTH NEVER OTHER |  |
| caffeine_use | What is your caffeine use? Value may be null. | string | True | 30 | UNSPECIFIED SEVERAL_TIMES_A_DAY ONCE_A_DAY A_FEW_TIMES_A_WEEK A_FEW_TIMES_A_MONTH NEVER OTHER |  |
| occupation_and_workplace | Occupation and Workplace | string | True | 255 |  |  |
| place_of_residence | Place of Residence | string | True | 255 |  |  |
| nursing_room_facility_name | Name of the Nursing Room Facility | string | True | 100 |  |  |
| nursing_room_identifier | Room Identifier for the patient nursing room. | string | True | 20 |  |  |
| pneumonia_vaccination | For patients 65 and older: Have you received a pneumonia vaccination? | boolean | True |  |  |  |
| health_care_proxy | Do you have a health care proxy in the event you are unable to make your own medical decisions? | boolean | True |  |  |  |
| health_care_proxy_designee_name | Health care proxy designee's name | string | True | 300 |  |  |
| health_care_proxy_designee_phone_number | Health care proxy designee's phone number | string | True | 30 |  |  |
| living_will | Do you have a living will? | boolean | True |  |  |  |
| do_not_intubate | Do Not Intubate: I do not wish to have a breathing tube, even if it is necessary to save my life. | boolean | True |  |  |  |
| do_not_resuscitate | Do Not Resuscitate: If my heart were to stop, I do not wish to have chest compressions or an automated external defibrillator to restart my heart, even if its necessary to save my life. | boolean | True |  |  |  |
| ema_test_patient | Flag indicates whether patient record is a Test. This flag is manually set by the practice | boolean | True |  |  |  |
| has_card_on_file | If the patient has a card on file. | boolean | True |  |  |  |
| card_on_file_expiration_date_max | The max expiration date amongst all cards on file. | string | True | 7 |  |  |
| full_cardiopulmonary_resuscitation | Full Cardiopulmonary Resuscitation: I want full cardiopulmonary resuscitation efforts to be made. | boolean | True |  |  |  |
| family_history_other | Other family histores (free-text) | string | True | -1 |  |  |
| account_status | Patient's account status. | string | True | -1 |  |  |
| status_date_modified | Patient's status last updated time. | timestamp | True |  |  |  |
| restricted | If the patient chart is restricted. | boolean | True |  |  |  |
| has_active_payment_plan | If patient has active payment plan flag. | boolean | True |  |  |  |
| payment_plan_types | Designates the type(s) of payment plans associated with a patient. | string | True | -1 |  |  |
| has_pre_collections | If patient has pre-collections status | boolean | True |  |  |  |
| date_last_seen_by_pcp | Date when a patient was last seen by their Primary Care Provider. | date | True |  |  |  |
| portal_enabled_date | Date patient portal was enabled for a patient. | timestamp | True |  |  |  |
| is_pregnant | Boolean value designating if the patient is currently pregnant. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## guarantor

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| guarantor_id | guarantor table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| relation_to_patient | Patient's Relationship to Guarantor | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| last_name | Guarantor's last name | string | True | 100 |  |  |
| first_name | Guarantor's first name | string | True | 100 |  |  |
| middle_name | Guarantor's middle name | string | True | 50 |  |  |
| prefix | Guarantor's name prefix | string | True | 50 |  |  |
| suffix | Guarantor's name suffix | string | True | 50 |  |  |
| date_of_birth | Guarantor's date of birth. | timestamp | True |  |  |  |
| same_as_patient_address | Guarantor's contact information is the same as the patient's. | boolean | True |  |  |  |
| country | Guarantor's address country | string | True | 30 |  |  |
| street1 | Guarantor's address street | string | True | 255 |  |  |
| street2 | Guarantor's address street line 2 | string | True | 255 |  |  |
| city | Guarantor's address city | string | True | 255 |  |  |
| state | Guarantor's address state | string | True | 50 |  |  |
| zipcode | Guarantor's address Zipcode | string | True | 50 |  |  |
| home_phone_number | Guarantor's home phone number | string | True | 25 |  |  |
| work_phone_number | Guarantor's work phone number | string | True | 25 |  |  |
| mobile_phone_number | Guarantor's mobile phone number | string | True | 30 |  |  |
| email | Guarantor's email | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_case

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_case_id | patient_case table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | False | 20 |  |  |
| case_type | Patient case Type | string | False | 40 | WORKERS_COMP AUTO_ACCIDENT PERSONAL_INJURY MEDICAL OTHER |  |
| case_name | Patient case name | string | False | 50 |  |  |
| case_number | Patient case number | string | False | 30 |  |  |
| injury_date | The date which the injury occurred | timestamp | False |  |  |  |
| injury_state | State in which the injury occurred | string | False | 2 |  |  |
| unable_to_work_start_date | Start date in which patient was unable to work | timestamp | True |  |  |  |
| unable_to_work_end_date | End date in which patient was unable to work | timestamp | True |  |  |  |
| active | Patient case status | boolean | False |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_race

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_race_id | patient_race table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| race | Race | string | True | 50 | WHITE, BLACK_OR_AFRICAN_AMERICAN, ASIAN, etc. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_case_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_case_attachment_id | patient_case_attachment table id | string | False | 20 |  |  |
| patient_case_id | patient_case table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_case_contact

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_case_contact_id | patient_case_contact table id | string | False | 20 |  |  |
| patient_case_id | patient_case table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| first_name | Contact's first name | string | False | 30 |  |  |
| last_name | Contact's last name | string | False | 30 |  |  |
| contact_type | Patient's contact Type | string | False | 40 | ATTORNEY CASE_MANAGER OTHER |  |
| phone_number | Contact's phone number | string | True | 50 |  |  |
| email | Contact's email address | string | True | 250 |  |  |
| fax_phone_number | Contact's fax phone number | string | True | 50 |  |  |
| active | Patient's contact status | boolean | False |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_policy_authorization

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_policy_authorization_id | insurance_policy_authorization table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | False | 20 |  |  |
| patient_case_id | patient_case table id | string | True | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| referral_contact_id | referral_contact table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| authorization_type | Patient's contact Type | string | False | 40 | Referral Authorization |  |
| authorization_number | Authorization Number | string | False | 50 |  |  |
| authorization_entry_date | Date in which authorization was entered. | timestamp | True |  |  |  |
| authorization_start_date | Start date of authorization. | timestamp | True |  |  |  |
| authorization_end_date | End date of authorization. | timestamp | True |  |  |  |
| number_of_authorized_visits | Number of approved authorized visits | int | True |  |  |  |
| authorized_visits_remaining | Number of approved authorized visits remaining | int | True |  |  |  |
| unlimited_visits | Unlimited authorized visits | boolean | True |  |  |  |
| description | Description | string | True | 500 |  |  |
| additional_notes | Additional notes | string | True | 500 |  |  |
| active | Patient's contact status | boolean | False |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_policy_authorization_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_policy_authorization_attachment_id | insurance_policy_authorization_attachment table id | string | False | 20 |  |  |
| insurance_policy_authorization_id | insurance_policy_authorization table id | string | False | 20 |  |  |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_policy_authorization_appt_type

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_policy_authorization_appt_type_id | insurance_policy_authorization_appt_type table id | string | False | 20 |  |  |
| insurance_policy_authorization_id | insurance_policy_authorization table id | string | False | 20 |  |  |
| appointment_type_id | insurance_policy_authorization table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## card_on_file

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| card_on_file_id | card_on_file table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| brand | Brand (payment processor network) of the credit card on file (ie Visa, Mastercard) | string | True | 10 | AMEX CUP DINERS DISCOVER JCB MAESTRO MC VISA |  |
| status | Whether or not the card on file is active. | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| expiration_date | The expiration date of the card on file, in the format 'YYYY/MM' | string | True | 7 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## patient_business_unit_setting

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_business_unit_id | patient_business_unit table id | string | False | 30 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_business_unit_statement_preference | Patient statement status for a given business unit. | string | True | 5 | ON HOLD OFF |  |
| patient_business_unit_auto_pay_status | Status of Patient's Auto Pay | string | True | 20 | ACTIVE CANCELLED DEACTIVATED DECLINED PENDING |  |
| last_statement_status | The patient's last statement status. | string | True | 20 |  |  |
| last_statement_date | Date that the last statement for a given business unit was sent to a patient. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_sticky_note_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_sticky_note_history_id | patient_sticky_note_history table id | string | False | 30 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| sticky_note | Patient's sticky note | string | True | -1 |  |  |
| sticky_note_date_created | Date sticky note created (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_group

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_group_id | insurance_group table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| active | If insurance group is active | boolean | True |  |  |  |
| name | Group Name | string | True | 255 |  |  |
| payer_scenario | Group Payer Scenario | string | True | 255 |  |  |
| description | Group Description | string | True | 4000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_policy

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_policy_id | insurance_policy table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| payer_id | payer table id (PM Column) | string | True | 20 |  |  |
| payer_address_id | payer_address table id (PM Column) | string | True | 20 |  |  |
| facility_payer_address_id | Facility specific payer_address table id (PM Column) | string | True | 20 |  |  |
| payer_plan_id | payer_plan table id (PM Column) | string | True | 20 |  |  |
| fee_schedule_id | fee_schedule table id (PM Column) | string | True | 20 |  |  |
| source_of_payment_typology | Source of Payment Typology | string | True | 100 |  |  |
| patient_self_paying | If policy is patient self paying | boolean | True |  |  |  |
| active | If insurance is active | boolean | True |  |  |  |
| insurance_company_name | Insurance Company Name | string | True | 255 |  |  |
| plan_name | Plan Name (PM column) | string | True | 100 |  |  |
| policy_type | Policy Type; may have null value. | string | True | 50 | EPO, FeeForService, HDHP, PPO, etc. |  |
| policy_number | Policy Number | string | True | 100 |  |  |
| group_number | Group Number | string | True | 100 |  |  |
| payer_id_number | Policy Payer Id | string | True | 50 |  |  |
| insurance_code | Insurance Code | string | True | 100 |  |  |
| insurance_phone_number | Insurance Phone # | string | True | 50 |  |  |
| ranking | Ranking | int | True |  |  |  |
| policy_effective_date | Policy Effective Date | timestamp | True |  |  |  |
| policy_term_date | Policy Term Date | timestamp | True |  |  |  |
| eligibility_active | Eligibility Status | boolean | True |  |  |  |
| eligibility_last_updated_time | Time stamp since elegibility was last updated. | timestamp | True |  |  |  |
| copay_type | Copay Type; may have null value. | string | True | 50 | COPAY_AMOUNT DEDUCTIBLE PERCENTAGE |  |
| copay_amount | Policy Copay Amount | double | True |  |  |  |
| copay_deductible | Policy Copay Deductible | double | True |  |  |  |
| deductible_remaining | Policy Copay Deductible remaining balance | double | True |  |  |  |
| copay_percent | Policy Copay Percent | double | True |  |  |  |
| out_of_pocket_amount | Out-of-pocket amount | double | True |  |  |  |
| out_of_pocket_remaining_amount | Remaining out-of-pocket amount | double | True |  |  |  |
| referral_needed | Policy Referral Needed | boolean | True |  |  |  |
| referral_number | Policy Referral Number | string | True | 50 |  |  |
| referral_number_of_visits | Policy Referral Number Of Visits | int | True |  |  |  |
| referral_effective_date | Policy Referral Effective Date | timestamp | True |  |  |  |
| referral_expiration_date | Policy Referral Expiration Date | timestamp | True |  |  |  |
| insurance_street1 | Insurance Address Street1 | string | True | 255 |  |  |
| insurance_street2 | Insurance Address Street2 | string | True | 255 |  |  |
| insurance_city | Insurance Address City | string | True | 255 |  |  |
| insurance_state | Insurance Address State | string | True | 50 |  |  |
| insurance_zipcode | Insurance Address Zipcode | string | True | 50 |  |  |
| insurance_country | Insurance Address Country | string | True | 30 |  |  |
| insurance_card_name_override | Flag if patient name is different than in insurance card (PM column) | boolean | True |  |  |  |
| patient_first_name | Patient's first name | string | True | 100 |  |  |
| patient_last_name | Patient's last name | string | True | 100 |  |  |
| patient_middle_name | Patient's middle name | string | True | 100 |  |  |
| patient_name_prefix | Patient's name prefix | string | True | 50 |  |  |
| patient_name_suffix | Patient's name suffix | string | True | 50 |  |  |
| relationship_to_policy_holder | Relationship To Policy Holder. May have a null value. | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| policy_patient_name | Name of the policy holder listed for insurance. | string | True | 200 |  |  |
| policy_holder_last_name | Policy Holder Last Name | string | True | 100 |  |  |
| policy_holder_first_name | Policy Holder First Name | string | True | 100 |  |  |
| policy_holder_middle_name | Policy Holder Middle Name | string | True | 50 |  |  |
| policy_holder_gender | Policy holder Gender. May have a null value. | string | True | 20 | MALE, FEMALE, etc. |  |
| policy_holder_marital_status | Policy Holder Marital Status. May have a null value. | string | True | 50 | MARRIED, SINGLE, etc. |  |
| policy_holder_date_of_birth | Policy Holder Date Of Birth | timestamp | True |  |  |  |
| policy_holder_race | Policy Holder Race | string | True | 50 | Based on HL7-0005 |  |
| policy_holder_home_phone_number | Policy Holder Home Phone # | string | True | 50 |  |  |
| policy_holder_work_phone_number | Policy Holder Work Phone # | string | True | 50 |  |  |
| policy_holder_mobile_phone_number | Policy Holder Mobile Phone # | string | True | 50 |  |  |
| policy_holder_street1 | Policy Holder Address Street1 | string | True | 255 |  |  |
| policy_holder_street2 | Policy Holder Address Street2 | string | True | 255 |  |  |
| policy_holder_city | Policy Holder Address City | string | True | 255 |  |  |
| policy_holder_state | Policy Holder Address State | string | True | 50 |  |  |
| policy_holder_zipcode | Policy Holder Address Zipcode | string | True | 50 |  |  |
| policy_holder_country | Policy Holder Address Country | string | True | 30 |  |  |
| billing_address_same_as_patient | Policy Holder's billing address is same as patient's | boolean | True |  |  |  |
| policy_holder_employer_name | Policy Holder Employer Name | string | True | 100 |  |  |
| policy_holder_employer_phone_number | Policy Holder Employer Phone # | string | True | 50 |  |  |
| policy_holder_employer_street1 | Policy Holder Employer Address Street1 | string | True | 255 |  |  |
| policy_holder_employer_street2 | Policy Holder Employer Address Street2 | string | True | 255 |  |  |
| policy_holder_employer_city | Policy Holder Employer Address City | string | True | 255 |  |  |
| policy_holder_employer_state | Policy Holder Employer Address State | string | True | 50 |  |  |
| policy_holder_employer_zipcode | Policy Holder Employer Address Zipcode | string | True | 50 |  |  |
| policy_holder_employer_country | Policy Holder Employer Address Country | string | True | 30 |  |  |
| relationship_to_guarantor | Patient Relationship To Guarantor. May have a null value. | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| guarantor_last_name | Guarantor Last Name | string | True | 100 |  |  |
| guarantor_first_name | Guarantor First Name | string | True | 100 |  |  |
| guarantor_middle_name | Guarantor Middle Name | string | True | 50 |  |  |
| guarantor_gender | Guarantor Gender. May have a null value. | string | True | 20 | MALE, FEMALE, etc. |  |
| guarantor_marital_status | Guarantor Marital Status. May have a null value. | string | True | 100 | MARRIED, SINGLE, etc. |  |
| guarantor_date_of_birth | Guarantor Date Of Birth | timestamp | True |  |  |  |
| guarantor_mrn | Guarantor MRN | string | True | 20 |  |  |
| guarantor_chart_number | Guarantor Chart Number | string | True | 50 |  |  |
| guarantor_race | Guarantor Race | string | True | 50 | Based on HL7-0005 |  |
| guarantor_street1 | Guarantor Address Street1 | string | True | 255 |  |  |
| guarantor_street2 | Guarantor Address Street2 | string | True | 255 |  |  |
| guarantor_city | Guarantor Address City | string | True | 255 |  |  |
| guarantor_state | Guarantor Address State | string | True | 50 |  |  |
| guarantor_zipcode | Guarantor Address Zipcode | string | True | 50 |  |  |
| guarantor_country | Guarantor Address Country | string | True | 30 |  |  |
| guarantor_home_phone_number | Guarantor Home Phone # | string | True | 50 |  |  |
| guarantor_work_phone_number | Guarantor Work Phone # | string | True | 50 |  |  |
| facility_plan_name | Payer facility specific plan name (PM Column) | string | True | 100 |  |  |
| facility_policy_number | Payer facility specific policy number (PM Column) | string | True | 20 |  |  |
| facility_group_number | Payer facility specific group number (PM Column) | string | True | 20 |  |  |
| facility_same_as_professional | True if facility specific claim address is the same as Payer (PM Column) | boolean | True |  |  |  |
| authorization_for_office_visit | Referral/Authorization for office visit (PM Column) | boolean | True |  |  |  |
| inpatient_services_precertification | Pre-Cert for In-Patient Services (PM Column) | boolean | True |  |  |  |
| outpatient_services_preauthorization | Pre-Auth for Out-Patient Services (PM Column) | boolean | True |  |  |  |
| insurance_card_front_image | Flag for insurance card scanned front image (PM Column) | boolean | True |  |  |  |
| insurance_card_back_image | Flag for insurance card scanned back image (PM Column) | boolean | True |  |  |  |
| customer_service_street1 | Customer Service Street 1 (PM Column) | string | True | 255 |  |  |
| customer_service_street2 | Customer Service Street 2 (PM Column) | string | True | 255 |  |  |
| customer_service_city | Customer Service City (PM Column) | string | True | 255 |  |  |
| customer_service_state | Customer Service State (PM Column) | string | True | 50 |  |  |
| customer_service_zipcode | Customer Service Zip Code (PM Column) | string | True | 50 |  |  |
| customer_service_email_address | Customer Service Email Address (PM Column) | string | True | 100 |  |  |
| customer_service_website_address | Customer Service Website (PM Column) | string | True | 255 |  |  |
| customer_service_phone_number | Customer Service Phone Number (PM Column) | string | True | 50 |  |  |
| customer_service_fax_phone_number | Customer Service Fax Number (PM Column) | string | True | 50 |  |  |
| claims_street1 | Claims Street 1 (PM Column) | string | True | 255 |  |  |
| claims_street2 | Claims Street 2 (PM Column) | string | True | 255 |  |  |
| claims_city | Claims City (PM Column) | string | True | 255 |  |  |
| claims_state | Claims State (PM Column) | string | True | 50 |  |  |
| claims_zipcode | Claims Zip Code (PM Column) | string | True | 50 |  |  |
| claims_email_address | Claims Email Address (PM Column) | string | True | 100 |  |  |
| claims_website_address | Claims Website (PM Column) | string | True | 255 |  |  |
| claims_phone_number | Claims Phone Number (PM Column) | string | True | 50 |  |  |
| claims_fax_phone_number | Claims Fax Number (PM Column) | string | True | 50 |  |  |
| appeals_street1 | Appeals Street 1 (PM Column) | string | True | 255 |  |  |
| appeals_street2 | Appeals Street 2 (PM Column) | string | True | 255 |  |  |
| appeals_city | Appeals City (PM Column) | string | True | 255 |  |  |
| appeals_state | Appeals State (PM Column) | string | True | 50 |  |  |
| appeals_zipcode | Appeals Zip Code (PM Column) | string | True | 50 |  |  |
| appeals_email_address | Appeals Email Address (PM Column) | string | True | 100 |  |  |
| appeals_website_address | Appeals Website (PM Column) | string | True | 255 |  |  |
| appeals_phone_number | Appeals Phone Number (PM Column) | string | True | 50 |  |  |
| appeals_fax_phone_number | Appeals Fax Number (PM Column) | string | True | 50 |  |  |
| precertification_street1 | Precertification Street 1 (PM Column) | string | True | 255 |  |  |
| precertification_street2 | Precertification Street 2 (PM Column) | string | True | 255 |  |  |
| precertification_city | Precertification City (PM Column) | string | True | 255 |  |  |
| precertification_state | Precertification State (PM Column) | string | True | 50 |  |  |
| precertification_zipcode | Precertification Zip Code (PM Column) | string | True | 50 |  |  |
| precertification_email_address | Precertification Email Address (PM Column) | string | True | 100 |  |  |
| precertification_website_address | Precertification Website (PM Column) | string | True | 255 |  |  |
| precertification_phone_number | Precertification Phone Number (PM Column) | string | True | 50 |  |  |
| precertification_fax_phone_number | Precertification Fax Number (PM Column) | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_group_policy

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_group_policy_id | insurance_group_policy table id | string | False | 20 |  |  |
| insurance_group_id | insurance_group table id | string | True | 20 | Insurance group policy is a part of. |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 | Insurance policy that belongs to the group. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| rank | Ranking of policy in insurance group. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## insurance_policy_phone_number

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_policy_phone_number_id | insurance_policy_phone_number table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 | Insurance policy that belongs to the group. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| type | Phone number type | string | True | 20 |  |  |
| phone_number | Phone number | string | True | 50 |  |  |
| visible | Visible | boolean | True |  |  |  |
| phone_number_date_created | ema.phone_number.date_created | timestamp | True |  |  |  |
| phone_number_date_modified | ema.phone_number.date_modified | timestamp | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## insurance_policy_address

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| insurance_policy_address_id | insurance_policy_address table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 | Insurance policy that belongs to the group. |  |
| patient_id | patient table id | string | False | 20 |  |  |
| is_primary_address |  | boolean | True |  |  |  |
| type | Address type | string | True | 50 |  |  |
| street1 | Address Street 1 | string | True | 255 |  |  |
| street2 | Address Street 2 | string | True | 255 |  |  |
| city | Address City | string | True | 255 |  |  |
| state | Address State | string | True | 50 |  |  |
| zipcode | Address Zipcode | string | True | 50 |  |  |
| country | Address Country | string | True | 30 |  |  |
| start_date | Start date | timestamp | True |  |  |  |
| end_date | End date | timestamp | True |  |  |  |
| address_date_created | ema.address.date_created | timestamp | True |  |  |  |
| address_date_modified | ema.address.date_modified | timestamp | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## patient_pharmacy

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pharmacy_id | patient_pharmacy table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| surescripts_pharmacy | If the pharmacy was added from the Surescripts database. | boolean | True |  |  |  |
| ncpdpid | National Council for Prescription Drug Programs ID. NULL if surescripts_pharmacy is False | string | True | 7 |  |  |
| default | If the pharmacy is the patient's default pharmacy. | boolean | True |  |  |  |
| name | Name of the pharmacy | string | True | 100 |  |  |
| phone_number | Phone number | string | True | 50 |  |  |
| fax_number | Fax number | string | True | 50 |  |  |
| street1 | Address Street 1 | string | True | 255 |  |  |
| street2 | Address Street 2 | string | True | 255 |  |  |
| city | Address City | string | True | 255 |  |  |
| state | Address State | string | True | 50 |  |  |
| zipcode | Address Zipcode | string | True | 50 |  |  |
| country | Address Country | string | True | 30 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_flag

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_flag_id | patient_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_first_name | Patient's first name | string | True | 100 |  |  |
| patient_last_name | Patient's last name | string | True | 100 |  |  |
| patient_mrn | MRN | string | True | 20 |  |  |
| flag_name | Flag name | string | True | 20 |  |  |
| flag_description | Flag description | string | True | 200 |  |  |
| flag_active | Indicates if patient flag is active. | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_history_id | patient_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| sunscreen | Do you wear sunscreen? (defaults to false if unanswered) | boolean | True |  |  |  |
| sunscreen_spf | If yes, what SPF? | int | True |  |  |  |
| tanning_salon | Do you tan in a tanning salon? (defaults to false if unanswered) | boolean | True |  |  |  |
| melanoma_fh | (Skin history) Do you have a family history of Melanoma? (defaults to false if unanswered) | boolean | True |  |  |  |
| breast_cancer_fh | (Plastic Surgery History) Do you have a family history of breast cancer? (defaults to false if unanswered) | boolean | True |  |  |  |
| malignant_hyperthermia_fh | (Plastic Surgery History) Do you have a family history of malignant hyperthermia or severe reactions to anesthesia? (defaults to false if unanswered) | boolean | True |  |  |  |
| herbal_medications | (Plastic Surgery History) Do you take any herbal medications or supplements? (defaults to false if unanswered) | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## medical_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| medical_history_id | medical_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| source | Screen in the application the condition was entered in | string | False | 50 | PAST_MEDICAL_HISTORY SKIN_DISEASE_HISTORY OCULAR_HISTORY PLASTIC_SURGERY_HISTORY MUSCULOSKELETAL_HISTORY ENT_HISTORY GI_HISTORY RHEUMATOLOGICAL_HISTORY UROLOGICAL_HISTORY |  |
| value | Medical history condition | string | True | 255 | See Appendix B |  |
| snomed | Medical history condition (SNOMED) | string | True | 255 |  |  |
| secondary_snomed | Medical history condition (secondary SNOMED). Only populated if primary snomed does not fully describe the condition. | string | True | 255 |  |  |
| other_value | Additional text added to the condition | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## surgical_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| surgical_history_id | surgical_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| source | Screen in the application the condition was entered in | string | False | 50 | PAST_MEDICAL_HISTORY SKIN_DISEASE_HISTORY OCULAR_HISTORY PLASTIC_SURGERY_HISTORY MUSCULOSKELETAL_HISTORY ENT_HISTORY GI_HISTORY RHEUMATOLOGICAL_HISTORY UROLOGICAL_HISTORY |  |
| value | Surgical history | string | True | 255 | See Appendix B |  |
| snomed | Surgical history (SNOMED) | string | True | 255 |  |  |
| secondary_snomed | Surgical history (secondary SNOMED). Only populated if primary snomed does not fully describe the condition. | string | True | 255 |  |  |
| other_value | Additional text added to the condition | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## specialty_pediatric_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| specialty_pediatric_history_id | specialty_pediatric_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| source | Screen in the application the condition was entered in | string | False | 50 | MUSCULOSKELETAL_HISTORY ENT_HISTORY RHEUMATOLOGICAL_HISTORY |  |
| value | Pediatric history (enum value) | string | True | 255 | See Appendix B |  |
| snomed | Pediatric history (SNOMED) | string | True | 255 |  |  |
| secondary_snomed | Pediatric history (secondary SNOMED). Only populated if primary snomed does not fully describe the condition. | string | True | 255 |  |  |
| other_value | Additional text added to the condition | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## specialty_family_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| specialty_family_history_id | specialty_family_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| source | Screen in the application the condition was entered in | string | False | 50 | MELANOMA BREAST_CANCER MAL_HYPER_ANESTHESIA MUSCULOSKELETAL_HISTORY ENT_HISTORY GI_HISTORY RHEUMATOLOGICAL_HISTORY UROLOGICAL_HISTORY |  |
| value | Family history (enum value) | string | True | 255 | See Appendix B |  |
| snomed | Family history (SNOMED) | string | True | 255 |  |  |
| secondary_snomed | Family history (secondary SNOMED). Only populated if primary snomed does not fully describe the condition. | string | True | 255 |  |  |
| other_value | Additional text added to the condition | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## specialty_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| specialty_history_id | specialty_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| source | Screen in the application the condition was entered in | string | False | 50 | HERBAL_MEDICATIONS_AND_SUPPLEMENTS INTERVENTIONAL_PAIN_HISTORY |  |
| value | History entry (enum value) | string | True | 255 | See Appendix B |  |
| snomed | History entry (SNOMED) | string | True | 255 |  |  |
| secondary_snomed | History entry (secondary SNOMED). Only populated if primary snomed does not fully describe the condition. | string | True | 255 |  |  |
| other_value | Additional text added to the condition | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## social_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| social_history_id | social_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| value | Social history option | string | True | 255 | See Appendix B |  |
| other_value | Additional text added to the condition | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## medication

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| medication_id | medication table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| rx_id | rx table id | string | True | 20 | Rx that the medication entry was created from. NULL if manually entered or imported from pharmacy or CCD (not prescribed from EMA). |  |
| drug_name | Drug name | string | True | 4000 |  |  |
| generic_name | generic name of drug, may be same as drug_name if generic was prescribed, may be null for some OTC drugs | string | True | 50 |  |  |
| is_generic | If the medication is a generic drug | boolean | True |  |  |  |
| strength | Strength | string | True | 100 |  |  |
| strength_units | Strength Units | string | True | 25 |  |  |
| route | Route | string | True | 50 |  |  |
| source | Source of the medication info (Patient Portal, CCDA Integration, etc) | string | False | 20 | CCDA EMA_MANUAL_ENTRY EMA_PRESCRIBE PATIENT_PORTAL SURESCRIPTS THIRD_PARTY UNKNOWN |  |
| dose | Dose | string | True | 50 |  |  |
| dose_form | Dose Form | string | True | 100 |  |  |
| frequency | Frequency | string | True | 100 |  |  |
| indication | Indication | string | True | 100 |  |  |
| date_started | Date started. If linked to rx from EMA, date the prescription was sent to the pharmacy, can be manually modified | timestamp | True |  |  |  |
| date_ended | Date ended | timestamp | True |  |  |  |
| during_visit | Administered During Visit | boolean | True |  |  |  |
| active | If the medication is active | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## allergy

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| allergy_id | allergy table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| allergen_type | Type of allergen. May have a null value. | string | True | 20 | Ingredient Drug Name Allergen Group |  |
| allergen_description | Description of the allergy. | string | True | 1000 | Based on FirstDataBank (FDB) allergy repository |  |
| allergy_status | Status of the allergy | string | True | 25 |  |  |
| date_recorded | Date allergy was recorded | timestamp | True |  |  |  |
| date_started | Date allergy started. | date | True |  |  |  |
| date_ended | Date allergy ended. | date | True |  |  |  |
| severity | Severity of the allergy. May have a null value. | string | True | 100 | Unspecified Mild MildToModerate Moderate ModerateToSevere Severe Fatal |  |
| reaction_anaphylaxis | Anaphylaxis | boolean | True |  |  |  |
| reaction_angioedema | Angioedema | boolean | True |  |  |  |
| reaction_hives | Hives | boolean | True |  |  |  |
| reaction_rash | Rash | boolean | True |  |  |  |
| reaction_shortness_of_breath | Shortness of breath | boolean | True |  |  |  |
| reaction_swelling | Swelling | boolean | True |  |  |  |
| reaction_weal | Weal | boolean | True |  |  |  |
| reaction_diarrhea | Diarrhea | boolean | True |  |  |  |
| reaction_dizziness | Dizziness | boolean | True |  |  |  |
| reaction_fatigue | Fatigue | boolean | True |  |  |  |
| reaction_gi_upset | GI upset | boolean | True |  |  |  |
| reaction_liver_toxicity | Liver toxicity | boolean | True |  |  |  |
| reaction_nausea | Nausea | boolean | True |  |  |  |
| reaction_other | Other | boolean | True |  |  |  |
| reaction_other_value | Allergy response other value. | string | True | 4000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## family_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| family_history_id | family_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| snomed | SNOMED code | string | True | 25 |  |  |
| condition | Snomed description term for the family history condition | string | True | 200 |  |  |
| status | Status of the family history condition. NOTE: Users often do not mark items as inactive. | string | True | 25 | ACTIVE INACTIVE COMPLETED |  |
| date_recorded | Date the family history condition was recorded. | timestamp | True |  |  |  |
| mother | True if the particular relative has the specified condition | boolean | True |  |  |  |
| father | True if the particular relative has the specified condition | boolean | True |  |  |  |
| sister | True if the particular relative has the specified condition | boolean | True |  |  |  |
| brother | True if the particular relative has the specified condition | boolean | True |  |  |  |
| daughter | True if the particular relative has the specified condition | boolean | True |  |  |  |
| son | True if the particular relative has the specified condition | boolean | True |  |  |  |
| uncle | True if the particular relative has the specified condition | boolean | True |  |  |  |
| aunt | True if the particular relative has the specified condition | boolean | True |  |  |  |
| nephew | True if the particular relative has the specified condition | boolean | True |  |  |  |
| niece | True if the particular relative has the specified condition | boolean | True |  |  |  |
| grandmother | True if the particular relative has the specified condition | boolean | True |  |  |  |
| grandfather | True if the particular relative has the specified condition | boolean | True |  |  |  |
| grandson | True if the particular relative has the specified condition | boolean | True |  |  |  |
| granddaughter | True if the particular relative has the specified condition | boolean | True |  |  |  |
| none | True if the particular relative has the specified condition | boolean | True |  |  |  |
| other | True if the particular relative has the specified condition | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## problem_list

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| problem_list_id | problem_list table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_id | diagnosis table id | string | True | 20 | Diagnosis entry that produced this problem list item. NULL if problem not linked to row in diagnosis table |  |
| date_diagnosed | Date the problem was entered. Often the visit_date if linked to a diagnosis (can be modified afterwards). | timestamp | True |  |  |  |
| problem_modified_date | Date the problem was last modified. NOTE: manually entered and often NULL | timestamp | True |  |  |  |
| end_date | Date the problem ended. NOTE: manually entered and often NULL | timestamp | True |  |  |  |
| problem_type | Problem list item type. May have a null value. | string | True | 50 | PROBLEM CONDITION DIAGNOSIS SYMPTOM FINDING COMPLAINT FUNCTIONAL_LIMITATION HEALTH_STATUS HEALTH_CONCERN |  |
| status | Problem list item status. NOTE: Users often do not update the status. | string | True | 50 | ACTIVE INACTIVE CHRONIC RESOLVED ABORTED |  |
| icd9 | ICD9 code | string | True | 25 |  |  |
| icd10 | ICD10 code | string | True | 25 |  |  |
| snomed | SNOMED code | string | True | 25 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## procedure_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| procedure_log_id | procedure_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| procedure_date | Date the procedure was recorded | timestamp | True |  |  |  |
| procedure_snomed | SNOMED code for the procedure | string | True | 25 |  |  |
| site_snomed | SNOMED code for the procedure site | string | True | 25 |  |  |
| reason_snomed | SNOMED code for the procedure reason | string | True | 25 |  |  |
| loinc | LOINC number | string | True | 25 |  |  |
| type | Type of record. May have a null value. | string | True | 30 | PROCEDURE GOAL PLAN EXAM FINDING SURVEY SOCIALHISTORY |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## immunization

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| immunization_id | immunization table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| administered_by_id | staff table id | string | True | 20 | Administered By |  |
| ordered_by_id | staff table id | string | True | 20 | Ordered By |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| cvx_code | CVX code for the vaccine | string | True | 255 |  |  |
| short_description | Short description of the vaccine | string | True | 255 |  |  |
| full_vaccine_name | Full name of the vaccine | string | True | 255 |  |  |
| lot_number | Lot Number | string | True | 255 |  |  |
| expiration_date | Expiration Date | timestamp | True |  |  |  |
| manufacturer | Short description of the vaccine | string | True | 255 |  |  |
| amount | Amount administered | string | True | 25 |  |  |
| units | Units of measure for amount | string | True | 50 |  |  |
| coding_system | Coding system for amount/units | string | True | 50 | Based on HL7-0396 |  |
| body_site | Site of administration | string | True | 50 | Based on HL7-0163 |  |
| route | Route of administration | string | True | 50 | Based on HL7-0162 |  |
| start_date | Start Date | timestamp | True |  |  |  |
| end_date | End Date | timestamp | True |  |  |  |
| source | Immunization Information Source | string | True | 50 | Based on CDC NIP001 (HL7 0396-NIP001) |  |
| refusal_reason | Substance Refusal Reason | string | True | 50 | Based on CDC NIP002 (HL7 0396-NIP002) |  |
| administration_note | Administration note (free-text) | string | True | -1 |  |  |
| vfc_class | VFC Financial Class | string | True | 3 | Based on HL7-0064 |  |
| status | Status of the immunization entry | string | True | 20 | PRELIMINARY FINALIZED AMENDED INVLIDATED |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## gyn_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| gyn_history_id | gyn_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| source | Section of the form where the information was entered in. | string | False | 50 |  |  |
| value | Value associated with the source field. It may be prefixed with the name of the source field. | string | True | 255 |  |  |
| snomed | GYN history condition (SNOMED) | string | True | 255 |  |  |
| secondary_snomed | GYN history condition (secondary SNOMED). Only populated if primary snomed does not fully describe the condition. | string | True | 255 |  |  |
| notes | Additional text associated with the value field. | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_reproductive_stage

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_reproductive_stage_id | patient_reproductive_stage table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| reproductive_stage | Patient reproductive stage. | string | False | 50 | Female of child bearing age Perimenopausal Postmenopausal Pre-pubertal |  |
| pregnancy_intent | Indicates if the patient wants to get pregnant within a year. | string | True | 50 |  |  |
| is_trying_to_conceive | Indicates if the patient is trying to conceive or not. | boolean | True |  |  |  |
| is_lactating | Indicates if the patient is lactating or not. | boolean | True |  |  |  |
| notes | Additional text added to the patient reproductive stage. | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_menstrual_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_menstrual_history_id | patient_menstrual_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| age_at_menarche | Age in years at which the patient had the menarche. | int | True |  |  |  |
| average_cycle_length | Average duration of the menstrual cycle. | int | True |  |  |  |
| average_cycle_unit | Unit used to specify the average cycle length. | string | True |  | Days Weeks Months |  |
| menses_duration_days | Average duration in days of the menstrual bleeding. | int | True |  |  |  |
| notes | Comments associated with the menstrual history event. | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_hpv_vaccine_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_hpv_vaccine_history_id | patient_hpv_vaccine_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| has_received_hpv_vaccine | Indicates if the patient has received the HPV vaccine. | string | True |  | Yes No Unsure |  |
| number_of_doses | Indicates the number of doses of the HPV vaccine the patient has received. | string | True |  | 1 2 3 Unsure |  |
| was_less_than_15_when_received | Indicates if the patient was less than 15 years old when the first dose of the HPV vaccine was administered. | string | True |  | Yes No Unsure |  |
| notes | Comments associated with the vaccination event. | string | True | -1 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_id | patient_pregnancy table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| patient_pregnancy_history_id | patient_pregnancy_history table id | string | True | 20 |  |  |
| primary_obstetrician_id | staff table id | string | True | 20 |  |  |
| internal_delivery_provider_id | staff table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| assisting_provider_id | staff table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| pregnancy_modified_by_id | staff table id | string | True | 20 |  |  |
| last_menstrual_period_date | Date of the patient's last menstrual period. | date | True |  |  |  |
| is_not_sure_of_last_menstrual_period | Indicates if the patient is unsure of the date of the last menstrual period. | boolean | True |  |  |  |
| first_ultrasound_date | Date of the patient's first ultrasound exam. | date | True |  |  |  |
| gestational_age_at_first_ultrasound_weeks | Patient's pregnancy gestational age at first ultrasound exam (in weeks). | int | True |  |  |  |
| gestational_age_at_first_ultrasound_days | Patient's pregnancy gestational age at first ultrasound exam (in days). | int | True |  |  |  |
| ivf_estimated_delivery_date | Estimated delivery date based on the date of when an in vitro fertilisation (IVF) procedure was performed. | date | True |  |  |  |
| estimated_delivery_date | Estimated delivery date. | date | True |  |  |  |
| method_of_dating | Method of determining the estimated delivery date. | string | True |  | Date of IVF Last Menstrual Period Ultrasound |  |
| pre_pregnancy_weight | Patient's pre-pregnancy weight. | double | True |  |  |  |
| pre_pregnancy_weight_unit | Unit of measure used to indicate the patient's pre-pregnancy weight. | string | True | 30 | Kg Lbs |  |
| fetus_count | Fetus count. | string | True | 30 |  |  |
| registered_to_deliver_at | Place where the patient is registered to have the delivery. | string | True | 100 |  |  |
| father_name | Name of the father of the baby. | string | True | 50 |  |  |
| partner_name | Name of the partner of the patient, if different than the baby's father name. | string | True | 50 |  |  |
| conclusion_date | Date when the pregnancy concluded. | date | True |  |  |  |
| conclusion_reason | Reason why the pregnancy concluded. | string | True | 30 | Delivery Ectopic Pregnancy Elected Abortion Error Multi-birth Delivery Patient Transferred Care Spontaneous Abortion |  |
| delivery_date | If the pregnancy concluded in delivery, date when the delivery happened. | date | True |  |  |  |
| mode_of_delivery | Mode of delivery. | string | True | 30 |  |  |
| delivery_provider_type | Indicates if the delivery provider was internal or external. | string | True | 30 |  |  |
| place_of_delivery | Name of the facility or location where the delivery occurred. | string | True | 100 |  |  |
| include_in_billing_for_internal_provider | Allows to select what should be included in the billing for the provider. | string | True | 30 | Delivery Only Delivery and Postpartum Care Total OB Care |  |
| include_in_billing_for_external_provider | Allows to select what should be included in the billing for the provider. | string | True | 30 | Antepartum Only Antepartum and Postpartum Care Postpartum Only |  |
| bill_em_codes_at_initial_visit | Indicates if EM codes may be billed during the patient's initial visit. | boolean | True |  |  |  |
| is_active_pregnancy | Indicates if the record corresponds to an ongoing pregnancy. | boolean | True |  |  |  |
| contains_sensitive_health_information | Indicates if the record contains sensitive health information. | boolean | True |  |  |  |
| is_mfm_visit | Indicates if the visit is associated with a Maternal-Fetal Medicine (MFM) provider. | boolean | True |  |  |  |
| pregnancy_modified_date | Date when the pregnancy record was last modified. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy_baby

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_baby_id | patient_pregnancy_baby table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| patient_pregnancy_id | patient_pregnancy table id | string | False | 20 |  |  |
| baby_name | Name of the baby. | string | True | 100 |  |  |
| sex | Sex of the baby. | string | True | 10 | Female Male Surprise |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy_exposure_questionnarie

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_exposure_questionnarie_id | patient_pregnancy_exposure_questionnarie table id | string | False | 80 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| patient_pregnancy_id | patient_pregnancy table id | string | False | 20 |  |  |
| question_category | Category of the question. | string | True | 100 | Genetic Screening Teratogen Exposure Since Pregnancy Infection History |  |
| question | Question asked to the patient. | string | True | 100 |  |  |
| patient_answer | Answer to the question, related to the patient. | string | True | 100 |  |  |
| father_answer | Answer to the question, related to the father of the baby. | string | True | 100 |  |  |
| partner_answer | Answer to the question, related to the patient's parter. | string | True | 100 |  |  |
| other_answer | Answer to the question, related to the other persons related to the patient, like family members. | string | True | 100 |  |  |
| notes | Additional notes related to the question. | string | True | 1000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pregnancy_chart_patient_vitals

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pregnancy_chart_patient_vitals_id | pregnancy_chart_patient_vitals table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_pregnancy_id | patient_pregnancy table id | string | False | 20 |  |  |
| fetal_movement | Indicates if there was fetal movement during the visit. | string | True | 20 |  |  |
| fundal_height | Measurement of the distance from the top of the uterus to the pubic bone, in centimeters | double | True |  |  |  |
| cervix_dilation | Cervix dilation, in centimeters, during the visit. | string | True | 20 |  |  |
| cervix_effacement | Percentage of cervix effacement during the visit. | string | True | 20 |  |  |
| cervix_station | Indicates how far a baby’s head has descended into the patient pelvis. Stations range from -5 to +5, with 0 station meaning the head is aligned with the ischial spines. | string | True | 20 |  |  |
| had_contractions | Indicates if there were contractions present during the visit. | boolean | True |  |  |  |
| had_fluid_leakage | Indicates if there was fluid leakage present during the visit. | boolean | True |  |  |  |
| had_bleeding | Indicates if there was bleeding present during the visit. | boolean | True |  |  |  |
| had_preterm_labor_symptoms | Indicates if preterm labor symptoms were detected during the visit. | boolean | True |  |  |  |
| comments | Comments added to the patient vitals during the visit. | string | True | 500 |  |  |
| note_to_visit | Additional comments added to the patient vitals during the visit. | string | True | 1000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pregnancy_chart_baby_vitals

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pregnancy_chart_baby_vitals_id | pregnancy_chart_baby_vitals table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_pregnancy_id | patient_pregnancy table id | string | False | 20 |  |  |
| heart_rate | Baby's hearth rate. | int | True |  |  |  |
| presentation | Indicates the way the baby is positioned in the uterus. | string | True | 20 | Breech Cephalic Transverse |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy_delivery_procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_delivery_procedure_id | patient_pregnancy_delivery_procedure table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| patient_pregnancy_id | patient_pregnancy table id | string | False | 20 |  |  |
| cpt_code | CPT code of the delivery procedure. | string | True | 5 |  |  |
| procedure_description | Description of the delivery procedure. | string | True | 1000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy_history

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_history_id | patient_pregnancy_history table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| pregnancy_type | Pregnancy type. | string | True | 20 | Delivery Ectopic Pregnancy Elective Abortion Miscarriage Multi-birth Delivery |  |
| pregnancy_type_snomed_code | Snomed code for the pregnancy type. | string | True | 15 |  |  |
| mode_of_delivery | Mode of delivery. | string | True | 30 |  |  |
| mode_of_delivery_snomed_code | Snomed code for the mode of delivery. | string | True | 15 |  |  |
| gestational_age_at_delivery_in_weeeks | Gestational age (in weeks) at the date of delivery. | int | True |  |  |  |
| length_of_labor_in_hours | Length of labor in hours. | int | True |  |  |  |
| anesthesia | Type of anesthesia used during the delivery. | string | True | 25 |  |  |
| anesthesia_snomed_code | Snomed code for the type of anesthesia used during the delivery. | string | True | 15 |  |  |
| place_of_delivery | Place where the delivery occurred. | string | True | 100 |  |  |
| gestational_age_at_miscarriage_in_weeks | Gestational age (in weeks) at the date of the miscarriage. | int | True |  |  |  |
| miscarriage_treatment | Treatment applied for the miscarriage. | string | True | 50 |  |  |
| ectopic_treatment | Treatment applied for the ectopic pregnancy. | string | True | 50 |  |  |
| abortion_treatment | Treatment applied for the abortion. | string | True | 50 |  |  |
| comments | Additional comments related to the patient's previous pregnancy. | string | True | 1000 |  |  |
| status | Pregnancy record status in the UI. | string | True | 15 | CONFIRMED DELETED EDITED PENDING |  |
| year_pregnancy_end | Year when the pregnancy ended. | int | True |  |  |  |
| date_delivery | Date when the delivery happened. | date | True |  |  |  |
| date_added | Date when the record was added to the patient clipboard. | date | True |  |  |  |
| date_last_edited | Date when the record was last edited. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy_history_baby

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_history_baby_id | patient_pregnancy_history_baby table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| patient_pregnancy_history_id | patient_pregnancy_history table id | string | False | 20 |  |  |
| mode_of_delivery | Mode of delivery. | string | True | 30 | Cesarean Forceps Assisted Vaginal Repeat Cesarean Vacuum Assisted Vaginal Vaginal Vaginal after Cesarean |  |
| baby_name | Name of the baby. | string | True | 100 |  |  |
| birth_weight_lbs | Baby's birth weight in lbs. | int | True |  |  |  |
| birth_weight_oz | Baby's birth weight in oz. | int | True |  |  |  |
| birth_weight_grams | Baby's birth weight in grams. | int | True |  |  |  |
| sex | Sex of the baby. | string | True | 10 |  |  |
| apgar_score_1_min | Apgar is a quick test performed on a baby at 1 and 5 minutes after birth. The 1-minute score determines how well the baby tolerated the birthing process. | int | True |  |  |  |
| apgar_score_5_min | Apgar is a quick test performed on a baby at 1 and 5 minutes after birth. The 5-minute score tells the health care provider how well the baby is doing outside the mother's womb. | int | True |  |  |  |
| was_living | Indicate if the baby was alive at the time of delivery. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_pregnancy_history_complication

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_pregnancy_history_complication_id | patient_pregnancy_history_complication table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| patient_pregnancy_history_id | patient_pregnancy_history table id | string | False | 20 |  |  |
| snomed_code | Snomed code of the complication. | string | True | 30 |  |  |
| complication | Name of the complication. | string | True | 100 |  |  |
| had_no_complication | True if there were no complications during the delivery. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## chart_note

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| chart_note_id | chart_note table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| author_patient_id | patient table id. Indicates the id of the patient associated with the chart. | string | True | 20 |  |  |
| author_staff_id | staff table id. Indicates the id of the staff user who created the note. | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| assigned_staff_id | staff table id. Id of the staff member who has to sign the note. | string | True | 20 |  |  |
| author_name | Name of the author of the note | string | True | 150 |  |  |
| assigned_staff_name | Name of the member of the staff who is assigned to sign the note | string | True | 150 |  |  |
| note_title | Title of the note | string | True | 100 |  |  |
| note_text | Text in the body of the chart note. | string | True | -1 |  |  |
| note_type | Type of chart note | string | True | 50 | COMMUNICATION COMPLETED_TASK COSMETIC DOCTOR_REFERRAL ELIGIBILITY IME INTERVAL MEDICAL_RECORD_REQUEST NON_VISIT_ORDER NO_SHOW ORDER OTHER PATHOLOGY PRE_OP PRIOR_AUTH PREGNANCY PROCEDURE PROGRESS REFILL RESEARCH RESULTS SCHOOL SPA TRANSCRIPTION VISIT WORK |  |
| note_status | Status of the chart note | string | True | 50 | CHARGES_SENT CODED FINAL FINALIZING HELD_FOR_BILLING HELD_FOR_RESULTS HELD_FOR_TRANSCRIPTION PRELIMINARY RECORDING_IN_PROGRESS TRANSCRIPTION_FAILED TRANSCRIPTION_READY |  |
| note_sub_status | Sub status of the chart note | string | True | 50 |  |  |
| communication_method | Communication method | string | True | 50 | DECLINED EMAIL FAX LETTER PHONE PORTAL UNSPECIFIED |  |
| sub_communication_method | Sub-communication method | string | True | 50 | GENERAL_PHONE_CALL PATIENT_PARTNER_STUDY_PHONE_CALL |  |
| visible | Indicates if the note is visible or hidden in the UI. | boolean | True |  |  |  |
| patient_visible | Indicates if the note is visible or hidden for the patient in the UI. | boolean | True |  |  |  |
| patient_account_expired | Indicates if the patient account has expired. | boolean | True |  |  |  |
| display_at_top | Whether to display the chart note at the top of the visit note. | boolean | True |  |  |  |
| archived | Indicates if the note was marked as archived in the UI. | boolean | True |  |  |  |
| note_created_date | Date when the chart note was created. | timestamp | True |  |  |  |
| date_sent | Date when the note was sent. | timestamp | True |  |  |  |
| finalized_date | Date when the note was marked as finalized in the UI. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## chart_segmentation_event

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| chart_segmentation_event_id | chart_segmentation_event table id | string | False | 20 |  |  |
| patient_id | patient table id. Indicates the id of the patient associated with the chart. | string | False | 20 |  |  |
| staff_id | Staff table id. | string | False | 20 |  |  |
| patient_last_name | Patient last name. | string | True | 100 |  |  |
| patient_first_name | Patient first name. | string | True | 100 |  |  |
| patient_mrn | patient table id. | string | True | 20 |  |  |
| staff_last_name | Staff last name. | string | True | 100 |  |  |
| staff_first_name | Staff first name. | string | True | 100 |  |  |
| event_type | Event Type | string | True | 150 |  |  |
| event_reason | Reason for event. | string | True | 255 |  |  |
| event_status | Sub status of the chart note | string | True | 50 |  |  |
| event_start_date | Timestamp event started. | timestamp | True |  |  |  |
| event_end_date | Timestamp event ended. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## chart_note_signature

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| chart_note_signature_id | chart_note_signature table id | string | False | 20 |  |  |
| chart_note_id | chart_note table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| signature_staff_id | Staff table id. Id of the staff member who has signed the note. | string | True | 20 |  |  |
| signature_note | Additional note to accompany the staff member's signature. | string | True | -1 |  |  |
| signature_date | Specific date on which the note is signed. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## intra_mail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| intra_mail_id | intra_mail table id | string | False | 60 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| author_patient_id | patient table id. Id of the patient who created the IntraMail message. | string | True | 20 |  |  |
| author_staff_id | staff table id. Id of the staff user who created the IntraMail message. | string | True | 20 |  |  |
| patient_id | patient table id. Id of the patient referenced in the IntraMail message. | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| lab_request_id | lab_request table id | string | True | 20 |  |  |
| chart_note_id | chart_note table id | string | True | 20 |  |  |
| patient_representative | Representative of the patient | string | True | 60 |  |  |
| subject | Subject of the IntraMail message. | string | True | 255 |  |  |
| message_body | Body of the IntraMail message. | string | True | -1 |  |  |
| priority | Indicates the priority of the IntraMail message. | string | True | 10 | HIGH LOW NORMAL |  |
| is_draft | Indicates if the IntraMail message was saved as a draft. | boolean | True |  |  |  |
| is_auto_reply | Indicates if a reply to an IntraMail message was automatic. | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## intra_mail_recipient

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| intra_mail_recipient_id | intra_mail table id | string | False | 60 |  |  |
| intra_mail_id | intra_mail table id | string | False | 20 |  |  |
| recipient_patient_id | patient table id. Id of the patient who received the IntraMail message. | string | True | 20 |  |  |
| recipient_staff_id | staff table id. Id of the staff user who received the IntraMail message. | string | True | 20 |  |  |
| firm_group_id | firm_group table id. Id of the group that received the IntraMail message. | string | True | 20 |  |  |
| recipient_type | Indicates the type of recipient of the IntraMail message. | string | True | 3 | CC TO |  |
| message_flagged | Indicates if the IntraMail message is flagged. | boolean | True |  |  |  |
| message_read | Indicates if the IntraMail message was read by the recipient. | boolean | True |  |  |  |
| message_archived | Indicates if the IntraMail message was archived by the recipient. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## merge_patient

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| merge_patient_id | merge_patient table id | string | False | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| patient_source_id | patient table id for the source patient in the merge operation. | string | True | 20 |  |  |
| patient_target_id | patient table id for the target patient in the merge operation. | string | True | 20 |  |  |
| performed_by_id | staff table id | string | True | 20 |  |  |
| created_by_id | staff table id | string | True | 20 |  |  |
| modified_by_id | staff table id | string | True | 20 |  |  |
| status | Status of the patient merge operation | string | True | 50 | COMPLETED FAILED IN_PROGRESS |  |
| merge_completed | Determines if the patient merge operation completed successfully. | boolean | True |  |  |  |
| date_performed | Date and time when the patient merge process was performed. | timestamp | True |  |  |  |
| date_completed | Date and time when the patient merge operation was completed. | timestamp | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |
