# Column Dictionary: Practice (866 columns)


## _info

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_id | Database ID of the firm included in the dataset (comma-separated list if more than one firm) | string | False | 20 |  |  |
| firm_global_id | Global ID of the firm included in the dataset (comma-separated list if more than one firm) | string | True | 200 |  |  |
| url_prefix | URL of the firm included in the dataset (comma-separated list if more than one firm) | string | True | 100 |  |  |
| providers | Comma-separated list of providers included in the dataset | string | True | -1 |  |  |
| unassociated_data | Include data for patients not associated to providers | boolean | True |  |  |  |
| execution_date | Date for which dataset was pulled | date | True |  |  |  |

## firm

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_id | firm table id | string | False | 20 |  |  |
| url_prefix | Firm URL prefix | string | True | 50 |  |  |
| global_identifier | ModMed internal firm global identifier | string | False | 10 |  |  |
| oid | Organization OID Note: This column will be deprecated in release 1.24 and removed in release 1.25. Please use organization_identifier instead. | string | True | 128 |  | True |
| organization_identifier | Facility Organization ID | string | True | 128 |  |  |
| name | Firm name | string | True | 255 |  |  |
| mmpay_enabled | Whether mmpay is enabled | boolean | True |  |  |  |
| data_explorer_enabled | If data explorer is enabled for the practice, and there is at least one user assigned to it. | boolean | True |  |  |  |
| division_additional_reporting_enabled | Flag to enable charges, payments and adjustment linked to a bill to be reported under a Division. | boolean | True |  |  |  |
| division_bill_nonbill_enabled | Flag to make division field required in a bill or non-bill charge prior to Saving or Posting a charge. | boolean | True |  |  |  |
| referral_source_patient_level_enabled | Display the referral source fields on the Edit Patient Screen and Create New Patient screens. | boolean | True |  |  |  |
| referral_source_appointments_bills_visit_level_enabled | Display the Referral Source field on the Schedule New Appointment, Manage Existing Appointment, Patient Checkin, Patient Checkout, Manage Visit Settings, Create a Bill, and Manage Bill screens. | boolean | True |  |  |  |
| referral_source_default_behavior_enabled | Default tracking of appointments, visits, and bills to patient's referral sources. | boolean | True |  |  |  |
| referral_source_new_patient_appointment_required_enabled | Require a Referral Source for New Patient Appointments. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## gpro

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| gpro_id | gpro table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| routing | Registry data should be sent to. | string | True | 50 | CMS: CMS via ModMed Registry Healthmonix |  |
| reporting_year | Reporting year | int | True |  |  |  |
| name | GPRO name | string | True | 100 |  |  |
| tax_id | Tax identification number | string | True | 20 |  |  |
| email | Email address | string | True | 255 |  |  |
| ia_practice_size | Practice size selection for MIPS Improvement Activies (IA). NULL if IA report has never been generated. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| facility_id | facility table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | True | 20 |  |  |
| region_id | region table id | string | True | 20 |  |  |
| name | Facility name | string | True | 100 |  |  |
| facility_street1 | Facility Address Street 1 | string | True | 255 |  |  |
| facility_street2 | Facility Address Street 2 | string | True | 255 |  |  |
| facility_city | Facility Address City | string | True | 255 |  |  |
| facility_state | Facility Address State | string | True | 50 |  |  |
| facility_zipcode | Facility Address Zipcode | string | True | 50 |  |  |
| facility_country | Facility Address Country | string | True | 30 |  |  |
| tax_id | Facility Tax ID (TIN) | string | True | 128 |  |  |
| tax_id_type | Facility Tax ID EIN / SSN | string | True | 20 |  |  |
| oid | Facility OID Note: This column will be deprecated in release 1.24 and removed in release 1.25. Please use organization_id instead. | string | True | 128 |  | True |
| organization_identifier | Facility Organization ID | string | True | 128 |  |  |
| billing_provider_name | Billing Provider Name | string | True | 255 |  |  |
| billing_provider_tax_id | Billing Provider Tax ID | string | True | 50 |  |  |
| billing_provider_tax_id_type | Billing Provider Tax ID EIN / SSN | string | True | 255 |  |  |
| billing_provider_npi | Billing Provider NPI (CMS-1500 Field 33a) | string | True | 20 |  |  |
| billing_provider_group_number | Billing Provider Group Number (CMS-1500 Field 33b) | string | True | 20 |  |  |
| billing_provider_street1 | Billing Provider Address Street 1 | string | True | 255 |  |  |
| billing_provider_street2 | Billing Provider Address Street 2 | string | True | 255 |  |  |
| billing_provider_city | Billing Provider Address City | string | True | 255 |  |  |
| billing_provider_state | Billing Provider Address State | string | True | 50 |  |  |
| billing_provider_zipcode | Billing Provider Address Zipcode | string | True | 50 |  |  |
| billing_provider_country | Billing Provider Address Country | string | True | 30 |  |  |
| billing_claims_street1 | Billing Claims Address Street 1 | string | True | 255 |  |  |
| billing_claims_street2 | Billing Claims Address Street 2 | string | True | 255 |  |  |
| billing_claims_city | Billing Claims Address City | string | True | 255 |  |  |
| billing_claims_state | Billing Claims Address State | string | True | 50 |  |  |
| billing_claims_zipcode | Billing Claims Address Zipcode | string | True | 50 |  |  |
| billing_claims_country | Billing Claims Address Country | string | True | 30 |  |  |
| business_name | Location business name | string | True | 255 |  |  |
| same_as_practice_name | Flag if business name if different than parent location name | boolean | True |  |  |  |
| email | Location email | string | True | 100 |  |  |
| location_type | If location is billing or place of service, may be have a NULL value if the location_type has not been defined | string | True | 100 | BILLING POS |  |
| place_of_service_code | Place of service code | string | True | 5 |  |  |
| place_of_service_name | Place of service name | string | True | 255 |  |  |
| facility_type | Autogenerated facility type from location type, may have a NULL value | string | True | 15 | FACILITY NON_FACILITY UNKNOWN |  |
| external_therapy_location | External Therapy Location flag | boolean | True |  |  |  |
| require_practice_location | Flag that indicates whether the Billing location requires a Practice Location (POS 11) within a bill. | boolean | True |  |  |  |
| location_npi | CMS issued unique location number | string | True | 10 |  |  |
| custom_bill_prefix | Two digit custom bill prefix | string | True | 2 |  |  |
| billing_type | Billing type for facility charges; may have a NULL value | string | True | 35 | PROFESSIONAL_AND_FACILITY PROFESSIONAL FACILITY |  |
| use_tax_rates | flag for custom tax rates when calculating product charges | boolean | True |  |  |  |
| state_tax_rate | State Tax Rate | double | True |  |  |  |
| local_tax_rate | Local Tax Rate | double | True |  |  |  |
| location_dea_number | Location's DEA Number | string | True | 10 |  |  |
| location_clia_number | Location's CLIA Number | string | True | 50 |  |  |
| pay_to_address_street1 | Pay-to Address Street 1 | string | True | 255 |  |  |
| pay_to_address_street2 | Pay-to Address Street 2 | string | True | 255 |  |  |
| pay_to_address_city | Pay-to Address City | string | True | 255 |  |  |
| pay_to_address_state | Pay-to Address State | string | True | 50 |  |  |
| pay_to_address_zipcode | Pay-to Address Zipcode | string | True | 50 |  |  |
| pms_id | Facility PMS ID | string | True | 50 |  |  |
| pms_id_type | Facility PMS Type | string | True | 100 |  |  |
| time_zone | Time Zone; may have a NULL value. | string | True | 30 | America/Puerto_Rico, US/Alaska, US/Arizona, US/Central, US/East-Indiana, US/Eastern, US/Hawaii, US/Indiana-Starke, US/Michigan, US/Mountain, US/Pacific, US/Samoa, UTC |  |
| active | Active status of facility. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## facility_phone_number

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| facility_phone_number_id | facility_phone_number table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| type | Phone number type | string | True | 20 | HOME, WORK, MOBILE |  |
| phone_number | Phone number | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## billing_provider_phone_number

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| billing_provider_phone_number_id | billing_provider_phone_number table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| type | Phone number type | string | True | 20 | HOME, WORK, MOBILE |  |
| phone_number | Phone number | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_id | staff table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| primary_facility_id | facility table id | string | True | 20 | Primary facility |  |
| supervisor_id | staff table id | string | True | 20 | Supervisor |  |
| universal_identifier | Single ID users can use to login into any of the firms they are associated with. | string | True | 100 |  |  |
| last_name | Last Name | string | True | 100 |  |  |
| first_name | First Name | string | True | 100 |  |  |
| middle_name | Middle Name | string | True | 50 |  |  |
| prefix | Name - Prefix | string | True | 50 |  |  |
| suffix | Name - Suffix | string | True | 50 |  |  |
| nick_name | Nick Name | string | True | 50 |  |  |
| username | Username | string | True | 50 |  |  |
| role | Role | string | True | 50 | DOCTOR, PHYSICIAN_ASSISTANT, MEDICAL_ASSISTANT etc. |  |
| title | Job title. | string | True | 35 |  |  |
| professional_designation | Professional designation. | string | True | 5 | DO MD NP PA Other |  |
| other_designation | Professional designation other. | string | True | 5 |  |  |
| erx_privilege | eRx Privilege | boolean | True |  |  |  |
| billing_privilege | Billing Privilege | boolean | True |  |  |  |
| sticky_update_own | Always update own sticky | boolean | True |  |  |  |
| sticky_update_by_others | Allow others to update sticky | boolean | True |  |  |  |
| must_reset_password | Must Reset Password Upon Next Login | boolean | True |  |  |  |
| account_disabled | Account Disabled | boolean | True |  |  |  |
| account_locked | Account Locked | boolean | True |  |  |  |
| last_login_date | Time of last login date for a staff | timestamp | True |  |  |  |
| allow_emergency_access | Allow Emergency Access | boolean | True |  |  |  |
| time_zone | Time Zone | string | True | 30 | US_EASTERN, US_CENTRAL |  |
| email | Email Address | string | True | 100 |  |  |
| email_updated_date | Date the staff member’s email address was updated | timestamp | True |  |  |  |
| hisp | Direct Mail (HISP) Address | string | True | 100 |  |  |
| alternate_hisp | Alternate Direct Mail (HISP) Address | string | True | 100 |  |  |
| date_of_birth | Date of birth | timestamp | True |  |  |  |
| display_findings_with_exam | Visit Note: Display findings with exam | boolean | True |  |  |  |
| billing_id_qualifier | Billing ID Qualifier (CMS-1500 Field 24i) | string | True | 2 |  |  |
| billing_provider_id | Billing ID (CMS-1500 Field 24j1) | string | True | 20 |  |  |
| npi | Provider NPI | string | True | 20 |  |  |
| display_detail_rx_education | Patient Handout: Display detail prescription education | boolean | True |  |  |  |
| drug_drug_warning_level | Drug-to-Drug Warning Levels | string | True | 30 | CONTRAINDICATED SEVERE MODERATE UNDETERMINED OFF |  |
| drug_allergen_warning_level | Drug-Allergen Warning Levels | string | True | 30 | ACTIVE_INGREDIENT INACTIVE_INGREDIENT OFF |  |
| duplicate_therapy_warning_level | Duplicate Therapy Warning Levels | string | True | 30 | ON OFF |  |
| include_supervisor_on_rx | Include Supervisor Name on Rx Script | boolean | True |  |  |  |
| rx_formulary_enabled | RX Formulary Enabled | boolean | True |  |  |  |
| rx_other_info | RX Formulary Enabled | string | True | 100 |  |  |
| nadean_number | Narcotic Addiction DEA Number | string | True | 10 |  |  |
| show_dea_in_printed_rx | Show DEA in Printed Rx | boolean | True |  |  |  |
| rx_coupon_enabled | Rx Patient Savings eCoupons Enabled | boolean | True |  |  |  |
| tax_id | Tax ID Number | string | True | 20 |  |  |
| pms_id | PMS ID | string | True | 50 |  |  |
| pms_id_type | PMS ID Type | string | True | 100 |  |  |
| default_appointment_interval | Default Appointment Interval (minutes) | int | True |  |  |  |
| allow_patients_to_send_intramail | Allow Patients to Send Intramail | boolean | True |  |  |  |
| has_schedule | Has Schedule | boolean | True |  |  |  |
| cancer_registry_state | Preferred Cancer Registry State | string | True | 2 |  |  |
| specialized_registry_enrollment | If the provider enrolled to submit to Modernizing Medicine Specialized Registry. See staff_specialized_registry table for the specific registries the provider enrolled in. | boolean | True |  |  |  |
| specialized_registry_enrollment_year | Reporting year the provider selected when enrolling to Specialized Registries | int | True |  |  |  |
| dea_number | DEA Number | string | True | 10 |  |  |
| calendar_enabled | Calendar feature enabled | boolean | True |  |  |  |
| epcs_authorized | Electronic Prescribing of Controlled Substances (EPSC) status | boolean | True |  |  |  |
| restrict_chart_permission | Indicates if the staff member has privileges to restrict a patient's chart. | boolean | True |  |  |  |
| user_recording_function_enabled | Used to designate if a user is enabled for Ambient Listening | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_clinical_registry_enrollment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_clinical_registry_enrollment_id | staff_clinical_registry_enrollment table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| registry_name | Registry name for which provider is enrolled for Data Delivery | string | True |  |  |  |
| enrollment_year | Year for which provider is enrolled for Data Delivery | int | True |  |  |  |
| firm_global_id | Firm global identifier (unique across pods) | string | False | 10 |  |  |

## staff_credentials

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_credentials_id | staff_credentials table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| start_date | Credentialed Start Date | timestamp | True |  |  |  |
| end_date | Credentialed End Date | timestamp | True |  |  |  |
| certified_number | Credentialed/Certified Number | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_specialty

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_specialty_id | staff_specialty table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| specialty | Specialty name | string | True | 255 | Allergy Immunology, Dermatologic Surgeon, Hematology, etc. |  |
| nucc_code | NUCC code for the specialty | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_phone_number

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_phone_number_id | staff_phone_number table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| type | Phone number type | string | True | 20 | HOME, WORK, MOBILE |  |
| phone_number | Phone number | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_cds_alert_setting

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_cds_alert_setting_id | staff_cds_alert_setting table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| alert | Alert that is enabled for the provider | string | True | 100 | TOBACCO_CESSATION_PLAN_FOR_SMOKERS, NUTRITIONAL_COUNSELING_FOR_BMI, HEMOGLOBIN, etc. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_specialized_registry

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_specialized_registry_id | staff_specialized_registry table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| registry | Registry that the provider is submitting data to. | string | True | 250 | Vitiligo, Pruritus, Melanoma, etc. |  |
| start_date | Start date | timestamp | True |  |  |  |
| end_date | End date | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_mips_settings

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_mips_settings_id | staff_mips_settings table id | string | False | 30 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| gpro_id | gpro table id | string | True | 20 | GPRO provider belongs to. NULL if reporting_option is INDIVIDUAL |  |
| reporting_year | Reporting year | int | True |  |  |  |
| reporting_option | Indicates if the provider is reporting as an individual Eligible Professional (EP) or with a Group Practice Reporting Option (GPRO). NULL if Quality Settings have not been entered. | string | True | 10 |  |  |
| gpro_authorizer | If the provider is the authorizer for the GPRO. NULL if reporting_option is INDIVIDUAL | boolean | True |  |  |  |
| ia_practice_size | Practice size selection for MIPS Improvement Activies (IA). NULL if IA report has never been generated. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_contact

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_contact_id | referral_contact table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| last_name | Last Name | string | True | 100 |  |  |
| first_name | First Name | string | True | 100 |  |  |
| middle_name | Middle Name | string | True | 50 |  |  |
| prefix | Name - Prefix | string | True | 50 |  |  |
| suffix | Name - Suffix | string | True | 50 |  |  |
| nick_name | Nick Name | string | True | 50 |  |  |
| npi | NPI | string | True | 20 |  |  |
| taxonomy_code | Unique 10-character code that designates referral's classification and specialization. | string | True | 20 |  |  |
| active | Status | boolean | True |  |  |  |
| work_phone_number | Work phone number | string | True | 50 |  |  |
| fax_phone_number | Fax phone number | string | True | 50 |  |  |
| mobile_phone_number | Mobile phone number | string | True | 50 |  |  |
| email | Email | string | True | 100 |  |  |
| alternate_email | Email | string | True | 100 |  |  |
| hisp | HISP address | string | True | 100 |  |  |
| alternate_hisp | Alternate HISP address | string | True | 100 |  |  |
| practice_name | Practice Name | string | True | 100 |  |  |
| street1 | Address Street 1 | string | True | 255 |  |  |
| street2 | Address Street 2 | string | True | 255 |  |  |
| city | Address City | string | True | 255 |  |  |
| state | Address State | string | True | 50 |  |  |
| zipcode | Address Zipcode | string | True | 50 |  |  |
| country | Address Country | string | True | 30 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_contact_specialty

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_contact_specialty_id | referral_contact_specialty table id | string | False | 20 |  |  |
| referral_contact_id | referral_contact table id | string | False | 20 |  |  |
| specialty | Specialty name | string | True | 255 | Allergy Immunology, Dermatologic Surgeon, Hematology, etc. |  |
| nucc_code | NUCC code for the specialty | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_institution

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_institution_id | referral_institution table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| name | Last Name | string | True | 100 |  |  |
| npi | NPI | string | True | 10 |  |  |
| active | Status | boolean | True |  |  |  |
| work_phone_number | Work phone number | string | True | 50 |  |  |
| fax_phone_number | Fax phone number | string | True | 50 |  |  |
| mobile_phone_number | Mobile phone number | string | True | 50 |  |  |
| email | Email | string | True | 100 |  |  |
| alternate_email | Email | string | True | 100 |  |  |
| hisp | HISP address | string | True | 100 |  |  |
| alternate_hisp | Alternate HISP address | string | True | 100 |  |  |
| street1 | Address Street 1 | string | True | 255 |  |  |
| street2 | Address Street 2 | string | True | 255 |  |  |
| city | Address City | string | True | 255 |  |  |
| state | Address State | string | True | 50 |  |  |
| zipcode | Address Zipcode | string | True | 50 |  |  |
| country | Address Country | string | True | 30 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_institution_specialty

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_institution_specialty_id | referral_institution_specialty table id | string | False | 20 |  |  |
| referral_institution_id | referral_institution table id | string | False | 20 |  |  |
| specialty | Specialty name | string | True | 255 | Allergy Immunology, Dermatologic Surgeon, Hematology, etc. |  |
| nucc_code | NUCC code for the specialty | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_id | lab table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| name | Name of the lab | string | True | 255 |  |  |
| routing_type | Routing type of the lab | string | True | 20 | E_LAB INTERNAL EXTERNAL FHIR CHC REDOX |  |
| active | If the lab is active (not deleted) | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_facility_id | lab_facility table id | string | False | 20 |  |  |
| lab_id | lab table id | string | False | 20 |  |  |
| street | Address Street | string | True | 255 |  |  |
| city | Address City | string | True | 255 |  |  |
| state | Address State | string | True | 50 |  |  |
| zipcode | Address Zipcode | string | True | 50 |  |  |
| phone_number | Phone Number | string | True | 30 |  |  |
| phone_number_ext | Phone Number Extension | string | True | 5 |  |  |
| pms_id | PMS ID | string | True | 50 |  |  |
| pms_id_type | PMS ID Type | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_account_staff

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_account_staff_id | lab_account_staff table id | string | False | 20 |  |  |
| lab_id | lab table id | string | False | 20 |  |  |
| staff_id | staff table id | string | True | 20 | Staff member for the lab account |  |
| account_number | Lab account number | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## lab_account_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| lab_account_facility_id | lab_account_facility table id | string | False | 20 |  |  |
| lab_id | lab table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 | Firm facility for the lab account |  |
| account_number | Lab account number | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## firm_group

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_group_id | firm_group table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| group_name | Name of group | string | True | 50 |  |  |
| group_type | Defines the type of group | string | True | 30 |  |  |
| visible | Indicates if group available for patients to intramail. | boolean | True |  |  |  |
| active | Active status of group | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## firm_group_member

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_group_member_id | firm_group_member table id | string | False | 20 |  |  |
| firm_group_id | firm_group table id | string | False | 20 |  |  |
| staff_id | Staff table id | string | False | 20 |  |  |
| staff_name | staff full name. | string | True | 200 |  |  |
| allow_patients_to_send_intramail | Designates if patients are allowed to send intra-mail to this group. | boolean | True |  |  |  |
| most_recent_intramail_date | Date-Time of the most recent intramail sent to the group. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## protocol

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| protocol_id | Protocol table id | string | False | 20 |  |  |
| staff_id | Staff table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| name | Protocol name | string | True | 255 |  |  |
| description | Protocol Summary | string | True | -1 |  |  |
| gender | Protocol gender; may have a null value | string | True | 20 | FEMALE MALE UNKNOWN |  |
| cross_gender_safe | If the protocol can be used in-between genders. | boolean | True |  |  |  |
| cross_gender_safe_body_locations | Indicates the specified body location is safe to use in-between genders. | string | True | 4000 |  |  |
| cross_gender_unsafe_body_locations | Indicates the specified body location is unsafe to use in-between genders | string | True | 4000 |  |  |
| medical_subdomain | Protocol medical subdomain | string | True | 50 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY RHEUMATOLOGY UROLOGY |  |
| shared | If the protocol is shared with a specific user or group. | boolean | True |  |  |  |
| archived | Protocol deleted flag. | boolean | True |  |  |  |
| protocol_created_date | Protocol date created | timestamp | True |  |  |  |
| protocol_modified_date | Protocol date modified | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## protocol_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| protocol_category_id | Protocol_category table id | string | False | 20 |  |  |
| protocol_id | Protocol table id | string | False | 20 |  |  |
| staff_id | Staff table id | string | False | 20 |  |  |
| modified_by_id | Staff table id | string | True | 20 |  |  |
| name | Protocol category name | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## protocol_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| protocol_log_id | Protocol_log table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| protocol_id | Protocol table id | string | False | 20 |  |  |
| applied_by_id | Staff table id | string | False | 20 | Staff member that applied the protocol to the visit |  |
| created_by_id | Staff table id | string | False | 20 |  |  |
| date_applied | Date applied. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## protocol_shared

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| protocol_shared_id | Protocol_shared table id | string | False | 20 |  |  |
| protocol_id | Protocol table id | string | False | 20 |  |  |
| firm_group_id | firm_group table id | string | True | 20 |  |  |
| staff_id | Staff table id | string | True | 20 |  |  |
| type | Determines if protocol is shared with provider or group | string | True | 45 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## business_unit

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| business_unit_id | Business_unit table id | string | False | 20 |  |  |
| firm_id | Firm table id | string | False | 20 |  |  |
| last_closed_report_by_staff_id | Staff table id associated with last closed report. | string | True | 20 |  |  |
| soft_closed_report_by_staff_id | Staff table id associated with soft closed report. | string | True | 20 |  |  |
| title | Business unit name. | string | False | 50 |  |  |
| organizational_npi | Business unit NPI number. | string | True | 10 |  |  |
| tax_identification_number | Business unit tax identification number | string | False | 9 |  |  |
| tax_identification_number_type | Tax identification number type | string | False | 9 | EIN SSN |  |
| group_taxonomy_code | A ten-digit alphanumeric code, issued by the NUCC to identify a provider's specialty | string | True | 50 |  |  |
| street1 | Business unit address street 1 | string | True | 255 |  |  |
| street2 | Business unit address street line 2 | string | True | 255 |  |  |
| city | Business unit address city | string | True | 255 |  |  |
| state | Business unit address state | string | True | 50 |  |  |
| zipcode | Business unit address Zipcode | string | True | 50 |  |  |
| phone_number | Business unit phone number | string | True | 50 |  |  |
| billing_type | Business unit type. Depends whether the business unit bills for facility charges or not | string | False | 35 | PROFESSIONAL_AND_FACILITY PROFESSIONAL FACILITY |  |
| additional_access_all_users | Flag if all facility users should also have access to this business unit. | boolean | False |  |  |  |
| closing_report_finalized_date | Date closing report was finalized | date | True |  |  |  |
| last_closed_report_date | Last closed report date. | timestamp | True |  |  |  |
| soft_closed_report_date | soft closed report date. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## business_unit_staff_access

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| business_unit_staff_access_id | Business_unit_staff_access table id | string | False | 20 |  |  |
| staff_id | Staff table id. | string | True | 20 |  |  |
| business_unit_id | Business_unit table id. | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## business_unit_payer_specific_identifier

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| business_unit_payer_specific_identifier_id | Business_unit_payer_specific_identifier table id | string | False | 20 |  |  |
| business_unit_id | Business_unit table id. | string | True | 20 |  |  |
| payer_id | Payer table id. | string | True | 20 |  |  |
| identifier | Payer identifier name. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## business_unit_batch_setting

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| business_unit_batch_setting_id | business_unit_batch_setting table id | string | False | 20 |  |  |
| business_unit_id | Business_unit table id. | string | True | 20 |  |  |
| charge_batch_required | If a batch is required for a charge associated with the business unit. | boolean | True |  |  |  |
| payment_batch_required | If a batch is required for a payment associated with the business unit. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## firm_denial_management_setting

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_denial_management_setting_id | firm_denial_management_setting table id | string | False | 40 |  |  |
| firm_id | firm table id | string | False | 40 |  |  |
| enabled | Indicates if the setting is enabled | boolean | True |  |  |  |
| default_bill_assignee | Firm denial manangement settings bill assignee group name. | string | True | 50 |  |  |
| default_bill_assignee_type | Indicates if a default bill assignee is bill assignee group, staff group or staff. | string | True | 30 |  |  |
| default_follow_up | Default number of days to follow up | int | True |  |  |  |
| clear_assignee_and_follow_up_days | Reset strategy | string | True | 40 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## firm_denial_management_specific_assignee_payer

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_denial_management_specific_assignee_payer_id | firm_denial_management_specific_assignee_payer table id | string | False | 40 |  |  |
| firm_id | Firm table id | string | False | 40 |  |  |
| payer_id | mav_contract_payer table id - table not currently in dw | string | False | 40 |  |  |
| firm_denial_management_setting_id | Firm table id | string | False | 40 |  |  |
| payer_matching_type | Payer matching type (MATCH_ANY_SELECTED, MATCH_ANY_UNSELECTED) | string | True | 40 |  |  |
| specific_assignee_type | Specific assignee type (PAYER, DENIAL_CATEGORY) | string | True | 40 |  |  |
| assignee | Firm denial manangement settings bill assignee name. | string | True | 30 |  |  |
| assignee_type | Indicates if an assignee is bill assignee group, staff group or staff. | string | True | 30 |  |  |
| url_prefix | Firm url prefix | string | True | 40 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## firm_denial_management_specific_assignee_denial_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| firm_denial_management_specific_assignee_denial_category_id | firm_denial_management_specific_assignee_denial_category table id | string | False | 40 |  |  |
| firm_id | Firm table id | string | False | 40 |  |  |
| firm_denial_management_specific_assignee_payer_id | firm_denial_management_specific_assignee_payer table id | string | True | 40 |  |  |
| denial_category | Denial Category | string | True | 40 |  |  |
| denial_name | Denial Code | string | True | 40 |  |  |
| denial_status | Denial Status | string | True | 40 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## fee_schedule

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fee_schedule_id | fee_schedule table id | string | False | 20 |  |  |
| provider_group_id | provider_group table id | string | False | 20 |  |  |
| fee_schedule_name | Fee schedule name | string | True | 50 |  |  |
| schedule_type | Fee schedule type. | string | False | 10 | PAYER PROVIDER |  |
| effective_date | Effective date. | date | True |  |  |  |
| end_date | End date. | date | True |  |  |  |
| rvu_cpt_default_calculation_method | Default fee calculation method for RVU-based CPTS | string | False | 5 | Fee For Service: FFS % of Medicare: MDC RVU: RVU |  |
| anesthesia_conversion_factor | Default anesthesia conversion factor . | double | True |  |  |  |
| rvu_services_conversion_factor | Default RVU services conversion factor. | double | True |  |  |  |
| percent_medicare_services | Default percent of medicare for services | double | True |  |  |  |
| percent_medicare_hcpcs_other | Default percent of medicare for fixed rate HCPCS other than DMEPO | double | True |  |  |  |
| percent_medicare_dmeposa | Default percent of medicare DMEPOS | double | True |  |  |  |
| billing_type | Fee Schedule billing type. Defaults to professional, unless a Professional / Facility location is selected. | string | False | 35 | PROFESSIONAL PROFESSIONAL_AND_FACILITY |  |
| payer_mpr_second_reduction | Second multiple procedure reduction expected | double | True |  |  |  |
| payer_mpr_third_reduction | Third multiple procedure reduction expected | double | True |  |  |  |
| payer_mpr_additional_reduction | Additional multiple procedure reduction expected | double | True |  |  |  |
| status | Fee schedule status. | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| includes_professional_facility | Fee schedule contains a facility with Professional / Facility billing type. | boolean | True |  |  |  |
| provider_schedule_available_for_patient_bills | Default Professional Fee Schedule. | boolean | True |  |  |  |
| provider_schedule_not_available_for_insurance_payers | Default Professional Fee Schedule. | boolean | True |  |  |  |
| provider_default_schedule | Default Professional Fee Schedule. | boolean | True |  |  |  |
| provider_default_facility_schedule | Default Facility Fee Schedule. | boolean | True |  |  |  |
| aca_exchange_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| auto_pip_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| champva_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| chip_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| commercial_other_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| epo_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| feca_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| ghp_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| government_other_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| hmo_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| ipa_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| medicaid_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| medicare_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| medicare_advantage_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| pos_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| ppo_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| tricare_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| vision_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| workers_comp_policy_enabled | Policy types for this schedule. Only valid for payer fee schedules. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fee_schedule_entry

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fee_schedule_entry_id | fee_schedule_entry table id | string | False | 20 |  |  |
| fee_schedule_id | fee_schedule table id | string | False | 20 |  |  |
| facility_id | facility table id. | string | False | 20 |  |  |
| provider_group_id | provider_group table id. | string | False | 20 |  |  |
| location_name | Name of facility | string | True | 100 |  |  |
| fee_schedule_name | Fee schedule name | string | True | 50 |  |  |
| provider_group_name | Provider group name. | string | True | 50 |  |  |
| effective_date | Effective date. | date | True |  |  |  |
| end_date | End date. | date | True |  |  |  |
| billing_type | Fee Schedule billing type. Defaults to PROFESSIONAL, unless a Professional / Facility location is selected. | string | False | 35 | PROFESSIONAL PROFESSIONAL_AND_FACILITY |  |
| schedule_status | Fee schedule status. | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| code | CPT or HCPCS Code. | string | True | 10 |  |  |
| code_numeric | Numeric portion of CPT or HCPCS Code. | int | True |  |  |  |
| code_prefix | CPT or HCPCS code prefix. | string | True | 1 |  |  |
| code_suffix | CPT or HCPCS code suffix. | string | True | 11 |  |  |
| code_description | CPT or HCPCS code description. | string | True | -1 |  |  |
| modifier | CPT or HCPCS code modifier. | string | True | 10 |  |  |
| calculation_method | Calculation method. | string | True | 5 |  |  |
| conversion_factor | Variable used to calculate fee in office based off RVU. | double | True |  |  |  |
| percent_medicare | Variable used to calculate fee in office based off percent of medicare. | double | True |  |  |  |
| fee_for_service | Variable used to calculate fee in office based off fee for service. | double | True |  |  |  |
| facility_fee_for_service | Variable used to calculate facility fee in office. Can be modified individually per facility, or globally from primary facility. | double | True |  |  |  |
| facility_conversion_factor | Facility specific variable used to calculate fee in office based off RVU. | double | True |  |  |  |
| facility_percent_medicare | Facility specific variable used to calculate fee in office based off percent of medicare. | double | True |  |  |  |
| fee_for_service_in_facility | Variable used to calculate facility fee in office. Can be modified individually per facility, or globally from primary facility. | double | True |  |  |  |
| quick_key | Quick Key used for CPT and HCPCS Codes. | string | True | 9 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fee_schedule_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fee_schedule_facility_id | fee_schedule_facility table id | string | False | 20 |  |  |
| fee_schedule_id | fee_schedule table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fee_schedule_payer

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fee_schedule_payer_id | fee_schedule_facility table id | string | False | 20 |  |  |
| fee_schedule_id | fee_schedule table id | string | False | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fee_schedule_import_file

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fee_schedule_import_file_id | fee_schedule_import_file table id | string | False | 20 |  |  |
| fee_schedule_id | fee_schedule table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| file_name | File name. | string | True | 40 |  |  |
| billing_type | Type of file template used for import. | string | True | 35 | PROFESSIONAL FACILITY |  |
| fee_schedule_file_import_status | The status of the file import (Pending, Completed of Failed). | string | True | 20 | COMPLETED FAILED IN_PROGRESS PENDING |  |
| number_of_lines | Number of lines in the import file. | int | True |  |  |  |
| facility_file_import_status | The status of the file import (Pending, Completed of Failed). Displays the import status per facility mapped to fee schedule. | string | True | 50 | IN_PROGRESS COMPLETED FAILED PENDING |  |
| lines_imported_count | Count of lines successfully imported. | int | True |  |  |  |
| lines_skipped_count | Count of lines skipped during import. | int | True |  |  |  |
| progress_last_updated_at | Last date of import progress (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_id | payer table id | string | False | 20 |  |  |
| firm_id | firm table id. | string | True | 20 |  |  |
| financial_category_id | financial_category table id. | string | True | 20 |  |  |
| payment_payer_id_number | Payment Payer ID Number | string | True | 20 |  |  |
| payer_id_number | Primary Payer ID number | string | False | 50 |  |  |
| eligibility_payer_id_number | Eligibility Payer ID Number | string | True | 20 |  |  |
| dme_payer_id_number | DME Payer ID | string | True | 50 |  |  |
| institutional_payer_id_number | Institutional Payer ID | string | True | 50 |  |  |
| other_payer_id_number | Other Payer ID | string | True | 50 |  |  |
| payer_name | Payer name | string | False | 255 |  |  |
| financial_category_name | Financial category name | string | True | 255 |  |  |
| facility_submission_form | Financial submission form type | string | True | 255 |  |  |
| eligibility_provider_identification_strategy | Eligibility request preference | string | True | 255 |  |  |
| claim_provider_identification_strategy | Billing provider (Box 33a) preference | string | True | 255 |  |  |
| primary_default_format | Default submission format when primary | string | True | 20 | Electronic: ELECTRONIC_5010, Paper: PAPER |  |
| primary_print_by_clearinghouse | Will this primary default submission format be printed by the clearinghouse? | boolean | True |  | Yes: TRUE, No: FALSE |  |
| sequential_default_format | Default submission format when sequential | string | True | 20 | Electronic: ELECTRONIC_5010, Paper: PAPER |  |
| sequential_print_by_clearinghouse | Will this sequential default submission format be printed by the clearinghouse? | boolean | True |  | Yes: TRUE, No: FALSE |  |
| workers_comp_default_format | Default submission format when worker's comp | string | True | 255 |  |  |
| auto_pip_default_format | Default submission format when auto/pip | string | True | 255 |  |  |
| vision_default_format | Default submission format when vision | string | True | 255 |  |  |
| contracted | If payer is contracted | boolean | True |  |  |  |
| accepts_assignment | If payer accepts assigments | boolean | True |  |  |  |
| is_medical | True if payer type is Medical | boolean | True |  |  |  |
| is_workers_comp | True if payer type is Worker's Comp | boolean | True |  |  |  |
| is_auto_pip | True if payer type is Auto/PIP | boolean | True |  |  |  |
| is_vision | True if payer type is Vision | boolean | True |  |  |  |
| is_bcbs_payer | True if payer type is BCBS | boolean | True |  |  |  |
| is_non_medicare_government_payer | True if payer type is Non Medicare Government | boolean | True |  |  |  |
| days_for_timely_filing | Number of days for timely filling. | int | True |  |  |  |
| days_timely_filing_warning | Number of days prior to timely filling for automated warning. | int | True |  |  |  |
| timely_filing_intramail_enabled | Flag to indicate if feature timely filing email reminder is enabled. | boolean | True |  |  |  |
| active | If payer status is active or not. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## additional_payer_identifier

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| additional_payer_identifier_id | additional_payer_identifier table id | string | False | 20 |  |  |
| firm_id | firm table id. | string | False | 20 |  |  |
| payer_id | payer table id. | string | True | 20 |  |  |
| payer_id_name | Name assigned to the additional payer identifier. | string | True | 200 |  |  |
| payer_id_type | Type of payer identifier | string | True | 20 |  |  |
| payer_id_number | The additional payer identifier. | string | True | 20 |  |  |
| position | Ordinal position of the additional payer identifier in the UI. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_address

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_address_id | payer_address table id | string | False | 20 |  |  |
| payer_id | Payer table id | string | False | 20 |  |  |
| billing_type | Payer's billing type. | string | False | 35 | PROFESSIONAL_AND_FACILITY FACILITY PROFESSIONAL |  |
| street1 | Payer's address street | string | True | 255 |  |  |
| street2 | Payer's address street line 2 | string | True | 255 |  |  |
| city | Payer's address city | string | True | 255 |  |  |
| state | Payer's address state | string | True | 50 |  |  |
| zipcode | Payer's address Zipcode | string | True | 50 |  |  |
| phone_number | Payer's home phone number | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_plan

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_plan_id | payer_plan table id | string | False | 20 |  |  |
| payer_id | Payer table id | string | False | 20 |  |  |
| payer_plan_name | Payer's plan name. | string | False | 100 |  |  |
| payer_policy_type | Payer's policy type. | string | False | 100 | EPO GHP HMO IPA MEDICARE_ADVANTAGE PPO POS COMMERCIAL_OTHER ACA_EXCHANGE CHAMPVA CHIP FECA MEDICARE MEDICAID TRICARE GOVERNMENT_OTHER VISION WORKERS_COMP AUTO_PIP B C Champus Choice Plus Exclusive Provider Organization (EPO) M O |  |
| payer_claim_filing_indicator | Payer's claim filing indicator | string | True | 100 | PATIENT_BILL OTHER_NON_FEDERAL_PROGRAMS PREFERRED_PROVIDER_ORGANIZATION_PPO POINT_OF_SERVICE_POS EXCLUSIVE_PROVIDER_ORGANIZATION_EPO INDEMNITY_INSURANCE HEALTH_MAINTENANCE_ORGANIZATION_HMO_MEDICARE_RISK DENTAL_MAINTENANCE_ORGANIZATION AUTOMOBILE_MEDICAL BLUE_CROSS_BLUE_SHIELD CHAMPUS COMMERCIAL_INSURANCE_CO DISABILITY FEDERAL_EMPLOYEES_PROGRAM HEALTH_MAINTENANCE_ORGANIZATION LIABILITY_MEDICAL MEDICARE_PART_A MEDICARE_PART_B MEDICAID OTHER_FEDERAL_PROGRAM TITLE_V VETERANS_AFFAIRS_PLAN WORKERS_COMPENSATION_HEALTH_CLAIM MUTUALLY_DEFINED |  |
| payer_payment_typology_code | Payer plan policy type; may have a null value | string | True | 100 | PT_1 PT_11 PT_111 PT_112 PT_113 PT_119 PT_12 PT_121 PT_122 PT_123 PT_129 PT_19 PT_2 PT_21 PT_211 PT_2111 PT_2112 PT_212 PT_213 PT_219 PT_22 PT_23 PT_24 PT_25 PT_29 PT_3 PT_31 PT_311 PT_3111 PT_3112 PT_3113 PT_3114 PT_3115 PT_3116 PT_3119 PT_312 PT_3121 PT_3122 PT_3123 PT_32 PT_321 PT_3211 PT_3212 PT_32121 PT_32122 PT_32123 PT_32124 PT_32125 PT_32126 PT_322 PT_3221 PT_3222 PT_3223 PT_3229 PT_33 PT_331 PT_332 PT_333 PT_334 PT_34 PT_341 PT_342 PT_343 PT_349 PT_35 PT_36 PT_361 PT_362 PT_369 PT_37 PT_371 PT_3711 PT_3712 PT_3713 PT_372 PT_379 PT_38 PT_381 PT_3811 PT_3812 PT_3813 PT_3819 PT_382 PT_389 PT_39 PT_4 PT_41 PT_42 PT_43 PT_44 PT_5 PT_51 PT_511 PT_512 PT_513 PT_514 PT_515 PT_519 PT_52 PT_521 PT_522 PT_523 PT_529 PT_53 PT_54 PT_55 PT_59 PT_6 PT_61 PT_611 PT_612 PT_613 PT_619 PT_62 PT_63 PT_64 PT_69 PT_7 PT_71 PT_72 PT_73 PT_79 PT_8 PT_81 PT_82 PT_821 PT_822 PT_823 PT_83 PT_84 PT_85 PT_89 PT_9 PT_91 PT_92 PT_93 PT_94 PT_95 PT_951 PT_953 PT_954 PT_959 PT_96 PT_98 PT_99 PT_ZZZ |  |
| active | If payer is active or not | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_plan_address

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_plan_address_id | payer_plan_address table id | string | False | 20 |  |  |
| payer_address_id | payer_address table id | string | False | 20 |  |  |
| payer_plan_id | payer_plan table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_authorization_requirement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_authorization_requirement_id | payer_authorization_requirement table id | string | False | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| policy_type | Authorization requirements policy type | string | True | 100 | EPO GHP HMO IPA MEDICARE_ADVANTAGE PPO POS COMMERCIAL_OTHER ACA_EXCHANGE CHAMPVA CHIP FECA MEDICARE MEDICAID TRICARE GOVERNMENT_OTHER VISION WORKERS_COMP AUTO_PIP B C Champus Choice Plus Exclusive Provider Organization (EPO) M O |  |
| authorization_for_office_visit | Referral/Authorization for office visit flag | boolean | True |  |  |  |
| inpatient_services_precertification | Pre-Cert for In-Patient Services flag | boolean | True |  |  |  |
| outpatient_services_preauthorization | Pre-Auth for Out-Patient Services flag | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_state_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_state_code_id | payer_state_code table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| payer_report_type | State (geographic subdivision) in which the code is applicable. | string | True | 60 |  |  |
| payer_state_code | Payer State Code. | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## appointment_type

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_type_id | appointment_type table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| name | Appointment type name | string | True | 25 |  |  |
| abbreviation | Appointment type abbreviation | string | True | 5 |  |  |
| default_duration | Appointment type default duration | int | True |  |  |  |
| mix_with_general_availability | General Availability flag | boolean | True |  |  |  |
| predefined | Pre-defined appointment type flag | boolean | True |  |  |  |
| active | Appointment type status | boolean | True |  |  |  |
| do_not_require_visit_creation | Indicates if a provider can address a patient's needs or provide a service without needing to schedule a formal, billed visit. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_type_link

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_type_link_id | appointment_type_link table id | string | False | 20 |  |  |
| parent_appt_type_id | appointment_type table id | string | False | 20 |  |  |
| child_appt_type_id | appointment_type table id | string | False | 20 |  |  |
| active | Active flag for appointment type link | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_group_block

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_group_block_id | appointment_group_block table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| last_modified_by_staff_id | staff table id | string | True | 20 |  |  |
| group_block_name | Appointment group or block name. | string | True | 25 |  |  |
| predefined | Pre-defined appointment group flag | boolean | True |  |  |  |
| active | Active flag for appointment group or block | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_group_block_link

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_group_block_link_id | appointment_group_block_link table id | string | False | 20 |  |  |
| appointment_group_block_id | appointment_group_block table id | string | False | 20 |  |  |
| appointment_type_id | appointment_type table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_calendar

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_calendar_id | Appointment calendar id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 | Provider associated with the calendar preference categories |  |
| appointment_group_block_id | appointment_group_block table id | string | False | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| last_modified_by_staff_id | staff table id | string | True | 20 |  |  |
| start_date | Start date | date | True |  |  |  |
| end_date | End date. If repeated event then the last repeated date | date | True |  |  |  |
| from_time | Start time of time slot | string | True | 5 |  |  |
| to_time | End time of time slot | string | True | 5 |  |  |
| number_of_patients | Number of patients permitted during the slot | int | True |  |  |  |
| monthly_on_same_date | Specifies the day of the month for monthly patterns | int | True |  |  |  |
| monthly_on_same_day | Specifies the day of the week for monthly patterns | string | True | 3 |  |  |
| monthly_on_week_of_month | Specifies the week number for day repeats | int | True |  |  |  |
| repeats | The frequency of repeated category slot | string | True | 20 | NONE WEEKLY MONTHLY |  |
| repeats_every | How frequently the repeated pattern occurs | int | True |  |  |  |
| weekly_days | The specified days for this category slot to repeat | string | True | 50 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_calendar_access

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_calendar_access_id | Appointment calendar access id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 | Location ID of specified calendar |  |
| provider_id | staff table id | string | False | 20 | Provider associated with the calendar |  |
| viewer_id | staff table id | string | True | 20 | Staff that have permissions to view provider calendar |  |
| type | Calendar permission access type | string | True | 30 | ACCESS_CALENDAR BOOK_UNAVAILABLE EXCEED_PT_MAX ACCESS_CALENDAR_EXCLUSION BOOK_UNAVAILABLE_EXCLUSION EXCEED_PT_MAX_EXCLUSION |  |
| max_count | Max count number of overbooked appointments. Null unless type is EXCEED_PT_MAX in which case count corresponds to overbook limit | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_calendar_edit

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_calendar_edit_id | Appointment calendar edit id | string | False | 20 |  |  |
| appointment_calendar_id | Appointment calendar id | string | False | 20 |  |  |
| created_by_id | staff table id | string | True | 20 | Staff member that edited calendar |  |
| instance_date | Date from which delete sequence begins | date | True |  |  |  |
| deleted | If edit is a deletion | boolean | True |  |  |  |
| instance_delete_date_from | Start date from which the delete sequence begins | date | True |  |  |  |
| instance_delete_date_to | End date from which the delete sequence ends | date | True |  |  |  |
| instance_delete_time_from_minutes | Start minutes from which delete sequence begins | int | True |  |  |  |
| instance_delete_time_to_minutes | End minutes from which delete sequence ends | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## division

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| division_id | division table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| division_name | Division name. | string | True | 35 |  |  |
| archived | Division archived flag. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## division_staff

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| division_staff_id | division_staff table id | string | False | 20 |  |  |
| division_id | division_staff table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## division_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| division_facility_id | division_facility table id | string | False | 20 |  |  |
| division_id | division table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_source

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_source_id | referral_source table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| referral_type_id | referral_type table id | string | True | 20 |  |  |
| referral_name | Referral source name. | string | True | 100 |  |  |
| referral_type_name | Referral type name. | string | True | 100 |  |  |
| referral_description | Referral source description. | string | True | 500 |  |  |
| status | Referral Source status flag. | boolean | True |  |  |  |
| built_in | Default built-in referral source flag (system generated). | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_type

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_type_id | referral_type table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| referral_type_name | Referral type name. | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## referral_source_link

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| referral_source_link_id | referral_source_link table id | string | False | 30 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| referral_source_id | referral_source table id | string | True | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| referring_patient_id | patient table id for referring patient. | string | True | 20 |  |  |
| referring_provider_id | referral_contact table id for referring provider. | string | True | 20 |  |  |
| referring_institution_id | referral_institution table id. | string | True | 20 |  |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| bill_id | bill table id | string | True | 20 |  |  |
| referral_type_id | referral_type table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| primary_source | Primary source flag. | boolean | True |  |  |  |
| referral_name | Source name. | string | True | 100 |  |  |
| referral_type | Source Type. | string | True | 100 |  |  |
| referral_description | Source description given by System Admin. | string | True | 500 |  |  |
| built_in | Default built-in source flag. | boolean | True |  |  |  |
| status | Referral Source status flag. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## provider_group

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| provider_group_id | provider_group table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| group_name | Division name. | string | True | 50 |  |  |
| provider_count | Number of providers in the given group. | int | True |  |  |  |
| status | Provider group status. | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## provider_group_member

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| provider_group_member_id | provider_group_member table id | string | False | 20 |  |  |
| provider_group_id | provider_group table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| first_name | First Name | string | True | 100 |  |  |
| last_name | Last Name | string | True | 100 |  |  |
| role | Role | string | True | 50 | DOCTOR, PHYSICIAN_ASSISTANT, MEDICAL_ASSISTANT etc. |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_referring_provider

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_referring_provider_id | patient_referring_provider table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| referring_provider_id | referral_contact table id | string | True | 20 |  |  |
| referring_provider_name | Name of Referring Provider | string | True | 1000 |  |  |
| is_latest | Whether the record contains the most-recently updated Referring Provider | boolean | True |  |  |  |
| date_last_seen | Date at which the patient was last seen | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_primary_care_provider

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_primary_care_provider_id | patient_primary_care_provider table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| primary_care_provider_id | referral_contact table id | string | True | 20 |  |  |
| primary_care_provider_name | Name of Primary Care Provider | string | True | 1000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visit_referral

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visit_referral_id | visit_referral table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| referring_provider_id | referral_contact table id | string | False | 20 |  |  |
| is_latest | Whether the record has the most recently modified referring provider | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_id | staff_preference table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| time_zone | Staff Time Zone | string | True | 30 |  |  |
| email | Staff email address. | string | True | 100 |  |  |
| date_of_birth | Staff date of birth. | date | True |  |  |  |
| phone_number_mobile | Staff mobile phone number. | string | True | 50 |  |  |
| follow_up_enabled | If True, follow up appointments will be enabled. | boolean | True |  | True: ON, False: OFF |  |
| follow_up_value | Default time until follow up appointment will be scheduled. | int | True |  |  |  |
| follow_up_unit | Unit of time for follow_up_value | string | True | 10 |  |  |
| follow_up_appointment_length | Default length of follow up appointment, in minutes. | int | True |  |  |  |
| follow_up_render_appointment_length | If True, will render Appointment Length on Visit Note and Encounter Form when Greater Than 0. | boolean | True |  |  |  |
| telemedicine_enabled | If True, will enable Telehealth | boolean | True |  | True: Checked, False: Unchecked |  |
| waitlist_prompting | If true, will prompt user to schedule waitlist entries on canceled appointments | boolean | True |  | True: Checked, False: Unchecked |  |
| override_default_toc_available | If True, will default the CCD Received option to "No" for all newly created New Patient or Transition of Care visits. | boolean | True |  | True: Yes, False: No |  |
| medications_allergies_enabled | If True, Medications / Allergies will be visible within Quick View | boolean | True |  | True: Checked, False: Unchecked |  |
| orders_results_enabled | If True, Orders / Results will be visible within Quick View | boolean | True |  | True: Checked, False: Unchecked |  |
| attachments_enabled | If True, Attachments will be visible within Quick View | boolean | True |  | True: Checked, False: Unchecked |  |
| problem_list_enabled | If True, Problem List will be visible within Quick View | boolean | True |  | True: Checked, False: Unchecked |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_assign_pathology_results

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_assign_pathology_results_id | staff_preference_assign_pathology_results table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| assignee_type | Type of the assignee. | string | True | 5 | staff group |  |
| assignee_name | Assignee Name | string | True | 100 |  |  |
| is_default | If True, Assignee is marked as default. | boolean | True |  | True: Checked, False: Unchecked |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_attendee

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_attendee_id | staff_preference_attendee table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| attendee_id | staff table id | string | False | 20 |  |  |
| attendee_name | Attendee name | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_biller

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_biller_id | staff_preference_biller table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| biller_id | staff table id | string | False | 20 |  |  |
| biller_name | Biller name | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_facility_id | staff_preference_facility table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| facility_name | Facility name | string | True | 100 |  |  |
| is_default | If True, Facility is marked as default. | boolean | True |  | True: DEFAULT, False: Make Default |  |
| kiosk_enabled | If True, Kiosk is marked as enabled. | boolean | True |  | True: Kiosk Enabled, False: (blank) |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_follow_up_reason

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_follow_up_reason_id | staff_preference_follow_up_reason table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| follow_up_reason | Reason for follow up | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_hpi

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_hpi_id | staff_preference_hpi table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| chief_complaint | Chief Complaint | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_medical_domain

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_medical_domain_id | staff_preference_medical_domain table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| medical_domain | Medical Domain | string | True | 50 | ALLERGY: Allergy, Asthma, and Immunology COSMETIC: Cosmetic DERMATOLOGY: Dermatology ENT: ENT FAMILY_MEDICINE: Family Medicine GI: GI INTERNAL_MEDICINE: Internal Medicine OB_GYN: OB/GYN OPHTHALMOLOGY: Ophthalmology OPTOMETRY: Optometry ORTHOPEDICS: Orthopedics PAIN_MANAGEMENT: Pain Management PEDIATRICS: Pediatrics PLASTICS: Plastics PODIATRY: Podiatry RHEUMATOLOGY: Rheumatology UROLOGY: Urology |  |
| is_default | If True, Medical Domain is default. | boolean | True |  | True: DEFAULT, False: Make Default |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_patient_chief_complaint

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_patient_chief_complaint_id | staff_preference_patient_chief_complaint table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| chief_complaint | Chief complaint | string | True | 255 |  |  |
| medical_domain | Medical domain | string | True | 50 |  |  |
| medical_subdomain | Medical subdomain | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_provider

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_provider_id | staff_preference_provider table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| provider_id | staff table id | string | False | 20 |  |  |
| provider_name | Provider name | string | True | 250 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_preference_room

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_preference_room_id | staff_preference_room table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| facility_resource_id | facility_resource table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| facility_resource_name | Facility Resource (Room) Name | string | True | 100 |  |  |
| facility_resource_type | Facility Resource (Room) Type | string | True | 20 |  |  |
| facility_name | Facility Name | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## consent_form

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| consent_form_id | consent_form table id. | string | False | 20 |  |  |
| firm_id | firm table id. | string | False | 20 |  |  |
| staff_id | staff table id. | string | True | 20 |  |  |
| consent_form_title | Consent title. | string | True | 255 |  |  |
| consent_form_description | Consent Description. | string | True | -1 |  |  |
| consent_form_legal_description | Consent Legal Description. | string | True | -1 |  |  |
| consent_form_category | Consent category. | string | True | 2000 |  |  |
| consent_form_type | Consent type, derived from workflow. | string | True | 40 | FIRM_GENERAL_CONSENT PATIENT_WAIVER USER_SPECIFIC_CONSENT |  |
| frequency_type | Patient waiver frequency setting. Patient waiver only field. | string | True | 40 |  |  |
| archived | Consent deleted flag. | boolean | True |  |  |  |
| active_all_facilities | Waiver available for all facilities. Patient waiver only field. | boolean | True |  |  |  |
| witness_consent_signature_required | Witness signature required. Consent field only. | boolean | True |  |  |  |
| nurse_consent_signature_required | Nurse signature required. Consent field only. | boolean | True |  |  |  |
| patient_consent_signature_required | Patient / Agent / Guardian signature required. Consent field only. | boolean | True |  |  |  |
| provider_consent_signature_required | Provider signature required. Consent field only. | boolean | True |  |  |  |
| anesthesia_provider_consent_signature_required | Anesthesia Provider signature required. Consent field only. | boolean | True |  |  |  |
| driver_consent_signature_required | Driver signature required. Consent field only. | boolean | True |  |  |  |
| pocket_patient_waiver_enabled | Waiver enabled for pocket patient app. Waiver field only. *Note*: This column will be deprecated on our next release. Please use `appatient_waiver_enabled` instead. | boolean | True |  |  |  |
| appatient_waiver_enabled | Waiver enabled for the appatient app. Waiver field only. | boolean | True |  |  |  |
| kiosk_patient_waiver_enabled | Waiver enabled for patient kiosk app. Waiver field only. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## consent_form_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| consent_form_facility_id | consent_form_facility table id | string | False | 20 |  |  |
| consent_form_id | consent_form table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## consent_form_patient

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| consent_form_patient_id | consent_form_patient table id | string | False | 20 |  |  |
| consent_form_id | consent_form table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| attachment_on_file | Record has a attachment on file flag. | boolean | True |  |  |  |
| declined | Patient declined consent form flag. | boolean | True |  |  |  |
| expired | Consent form assignment expired flag. | boolean | True |  |  |  |
| processed_date | Consent form processed date | timestamp | True |  |  |  |
| expiration_date | Consent form expiration date | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## region

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| region_id | region table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| created_by_staff_id | staff table id | string | False | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| name | Name of the region | string | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_region

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_region_id | staff_region table id | string | False | 20 |  |  |
| region_id | region table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| created_by_staff_id | staff table id | string | False | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## restricted_chart_event_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| restricted_chart_event_log_id | restricted_chart_event_log table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| accessed_by_staff_id | staff table id | string | False | 20 |  |  |
| event_type | When a staff member accesses a restricted chart/region or a chart's restricted status is updated. | string | True | 50 | MARKED_AS_RESTRICTED REGIONS RESTRICTED_CHART UNMARKED_AS_RESTRICTED |  |
| reason | Staff member's reason for accessing patient chart or region | string | True | -1 |  |  |
| event_start | Timestamp when staff member accessed restricted chart or region | timestamp | True |  |  |  |
| event_end | Timestamp when staff member stopped access of restricted chart or region | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## restricted_chart_notifications

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| restricted_chart_notifications_id | restricted_chart_notifications table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| firm_group_id | firm_group table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_payer_identifiers

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_payer_identifiers_id | staff_payerentifiers table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| payer_id | payer table id | string | True | 20 |  |  |
| payer_identifier | Payer identifier (from payer) | string | True | 50 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_society_associations

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_society_associations_id | staff_society_associations table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| organization_name | Society or association's name | string | True | 200 |  |  |
| member_number | Identifier associated with organization | string | True | 30 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_state_industrial_accident

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_state_industrial_accident_id | staff_state_industrial_accident table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| industrial_accident_identifier | Industrial accident identifier | string | True | 200 |  |  |
| state | State for industrial accident | string | True | 10 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_state_license

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_state_license_id | staff_state_license table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| license_number | License number | string | True | 20 |  |  |
| state | State for license | string | True | 10 |  |  |
| requires_rx_underwriting | If the license requires rx underwriting | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## staff_state_provider

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_state_provider_id | staff_state_provider table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| provider_identifier | Provider identifier | string | True | 20 |  |  |
| state | State of provider | string | True | 10 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
