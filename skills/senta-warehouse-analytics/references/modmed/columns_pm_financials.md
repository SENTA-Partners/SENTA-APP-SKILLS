# Column Dictionary: PM Financials (1727 columns)


## financial_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| financial_category_id | financial_category table id | string | False | 20 |  |  |
| firm_id | firm table id. | string | True | 20 |  |  |
| category_name | Category name. | string | True | 100 |  |  |
| is_self_pay | If category is used for self pay. | boolean | True |  |  |  |
| category_type | Category type. | string | True | 20 | RCM MANUAL |  |
| patient_responsible | If selected, this category can get used as a patient's financial category. | boolean | True |  |  |  |
| rcm_category | Patient Responsible RCM Financial Category Group; may have a NULL value. | string | True | 100 | MEDICARE MEDICARE_RAILROAD MEDICARE_ADVANTAGE MEDICAID MEDICAID_HMO HMO COMMERCIAL_PPO COMMERCIAL_POS COMMERCIAL_EPO THIRD_PARTY_LIABILITY VETERANS ACTIVE_MILITARY OTHER_COMMERCIAL RCM_PATIENT_RESPONSIBLE MEDI_MEDI |  |
| active | If fianancial category status is active or not. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_diagnosis_pm

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_diagnosis_pm_id | bill_diagnosis_pm table id | string | False | 20 |  |  |
| bill_id | bill table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_code | ICD 9 or ICD 10 diagnosis code linked to bill. | string | True | 40 |  |  |
| position | Position of ICD 9 or ICD 10 diagnosis code linked to bill. | int | True |  |  |  |
| eci_enabled | Flag for external Cause of Injury code selection in bill. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## custom_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_code_id |  | string | False | 40 |  |  |
| firm_id | Firm table id | string | False | 40 |  |  |
| code | Custom code name | string | True | 10 |  |  |
| code_description | Custom code description | string | True | 250 |  |  |
| status | Custom code status | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| billing_preference | Indicates whether a code is billed to insurance or not | string | True | 30 | NON_INSURABLE INSURABLE |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## custom_cpt_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_cpt_code_id | custom_cpt_code table id | string | False | 40 |  |  |
| firm_id | firm table id. | string | False | 20 |  |  |
| code_is_active | Custom code status | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| code | Custom code code | string | True | 250 |  |  |
| code_description | Custom code description | string | True | 250 |  |  |
| procedures | A concatenated list of the names of the procedures associated with the Custom CPT Code | string | True | -1 |  |  |
| billing_preference | Indicates whether a code is billed to insurance or not | string | True | 30 | NON_INSURABLE INSURABLE |  |
| code_category | Name of the Code Category associated with the Custom CPT Code | string | True | 75 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## custom_code_procedure_link

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_code_procedure_link_id | custom_code_procedure_link table id | string | False | 20 |  |  |
| procedure_id | Procedure table id | string | True | 20 |  |  |
| custom_code_id | custom_code table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## charges

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| charges_id | charges table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| primary_provider_id | staff table id | string | True | 20 | Primary provider listed on bill |  |
| payer_id | payer table id | string | True | 20 | Payer listed on bill |  |
| facility_id | facility table id | string | True | 20 | Service location |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| bill_item_id | bill_item table id | string | True | 20 | Individual services on bill |  |
| bill_insurance_id | bill_insurance table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| batch_id | batch table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| patient_product_id | Patient product table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| package_item_sale_id | package_item_sale table id | string | True | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| appointment_provider_id | staff table id for appointment provider. | string | True | 20 | Appointment Provider |  |
| bill_id | bill table id | string | True | 20 |  |  |
| original_bill_id | Bill table id. Indicates if a bill was recreated from a previous bill | string | True | 20 |  |  |
| sold_by_id | staff table id | string | True | 20 | The staff member selected in the Sold By field. The provider and the Sold by could be the same person depending on selection. |  |
| payer_address_id | payer_address table id | string | True | 20 |  |  |
| billing_quote_id | billing_quote table id | string | True | 20 |  |  |
| billing_quote_created_by_id | staff table id | string | True | 20 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| bill_assignee_id | bill_assignee table id | string | True | 20 |  |  |
| provider_level_adjustment_id | provider_level_adjustment table id. | string | True | 40 |  |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| bill_status | Current bill status | string | True | 40 | PRELIMINARY IN_PROGRESS REQUIRES_REVISION READY_FOR_REVIEW IN_REVIEW INACTIVE_OTHER RESOLVED_PAID RESOLVED_OTHER IN_DISPUTE PAYMENT_PENDING READY_FOR_POSTING |  |
| encounter_count | Stores the associated bill_id. If not null, indicates an encounter has occurred and the sum of units posted or reversed within the bill is greater than zero. | string | True | 20 |  |  |
| appointment_type | Appointment type. Types are confirmed by the practice at the firm admin level. | string | True | 25 |  |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| bill_type | Bill type. | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| responsible_insurance_policy_number | Insurance policy number. | string | True | 100 |  |  |
| policy_type | Insurance policy type. May have a null value. | string | True | 100 | EPO GHP HMO IPA MEDICARE_ADVANTAGE PPO POS COMMERCIAL_OTHER ACA_EXCHANGE CHAMPVA CHIP FECA MEDICARE MEDICAID TRICARE GOVERNMENT_OTHER VISION WORKERS_COMP AUTO_PIP B C Champus Choice Plus Exclusive Provider Organization (EPO) M O |  |
| policy_group_number | Insurance policy group number. | string | True | 100 |  |  |
| patient_relationship_to_policy_holder | Patient relationship to insurance policy holder. May have a null value. | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| policy_patient_name | Name of the policy holder listed for insurance. | string | True | 250 |  |  |
| policy_holder_gender | Policy holder Gender. May have a null value. | string | True | 20 | MALE, FEMALE, etc. |  |
| policy_holder_date_of_birth | Policy Holder Date Of Birth | timestamp | True |  |  |  |
| payer_plan_name | Payer's plan name. | string | True | 100 |  |  |
| cpt_frequency_unit | The number of times a service has been rendered. This value will be negative for voids. | int | True |  |  |  |
| product_category | Product category name | string | True | 100 |  |  |
| product_sku | Product sku | string | True | 100 |  |  |
| service_location_pos_code | Place of service code listed on the bill. | string | True | 5 |  |  |
| claim_employer_name | If applicable, this reflects the employer's name listed for the insurance policy. | string | True | 100 |  |  |
| quick_code | Reflects the quick code combination configured for the CPT/Modifier combination on the bill. These codes are configured by the practice. | string | True | 50 |  |  |
| authorization_number | Authorization number linked to insurance policy. | string | True | 50 |  |  |
| billing_quote_title | Title of billing quote | string | True | 100 |  |  |
| billing_quote_id_number | Client-facing billing quote id | string | True | 20 |  |  |
| source_of_payment_typology | Source of Payment Typology | string | True | 100 |  |  |
| is_referring_physician_data | Qlik flag if record is part of the referring physician report. | boolean | True |  |  |  |
| signature_on_file | If true, a practice can receive payment from an insurer on behalf of a patient. | boolean | True |  | True: Yes, False: No |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| package_sale_date_created_ld | Date on which the package was sold. | timestamp | True |  |  |  |
| firm_is_using_rcm | Whether using rcm is enabled | boolean | True |  |  |  |
| responsible | Responsible party. | string | True | 20 | PATIENT INSURANCE |  |
| bill_item_allowed | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| unit_charge | Charge per unit for services rendered | double | True |  |  |  |
| ledger_units | Number of units associated to the charge | double | True |  |  |  |
| coverage_type | Coverage type. May have a null value. | string | True | 20 | Primary Secondary Tertiary Self-Pay |  |
| link_state | Stores the current state of the insurance in relation to the bill | string | True | 20 | LINKED UNLINKED REMOVED LEGACY_REMOVED |  |
| activity_type | Activity Type | string | True | 100 | CHARGE VOID_CHARGE PLA_OFFSET_CHARGE VOID_PLA_OFFSET_CHARGE |  |
| ledger_charge_amount | Total amount calculated by multiplying unit charge amount multiplied by number of units. | double | True |  |  |  |
| subtotal | Product subtotal. | double | True |  |  |  |
| tax_rate_local | Product local tax rate. | double | True |  |  |  |
| tax_rate_state | Product state tax rate. | double | True |  |  |  |
| tax_amount_local | Product local tax amount. | double | True |  |  |  |
| tax_amount_state | Product state tax amount. | double | True |  |  |  |
| tax_amount | Product total tax amount, state and local combined. | double | True |  |  |  |
| discount_amount | Product discount amount. | double | True |  |  |  |
| discount_type | Product discount type. | string | True | 50 | PERCENT AMOUNT |  |
| discount_reason | Discount reason from standard_list or pipe separated custom discount reason(s) | string | True | 500 |  |  |
| notes | Charge notes. | string | True | 255 |  |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or inventory product description. | string | True | 500 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 100 |  |  |
| financial_category | The Financial Category listed for the payer | string | True | 100 |  |  |
| batch_name | Batch name. | string | True | 100 |  |  |
| pla_reason | Provider level adjustment reason | string | True | 100 |  |  |
| wrvu | CMS wRVU (work relative value units) for the associated Bill Item. | double | True |  |  |  |
| balance_amount_patient | Total balance for the patient. | double | True |  |  |  |
| balance_amount_insurance | Total balance for insurance. | double | True |  |  |  |
| package_name | Package name | string | True | 50 |  |  |
| bill_assignee_staff_name | Name of the staff member that is assigned to follow up on payments. | string | True | 200 |  |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| payer_check_key | Payer check key, used to link different payer payments to payment tables. | string | True | 20 |  |  |
| payer_check_notes | Payer check notes entered by the practice | string | True | 255 |  |  |
| payment_link | URL that links back to the payment transaction modal | string | True | 100 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| payment_method | Method of payment such as cash, check, e-check, credit card, gift card, etc. | string | True | 200 |  |  |
| payment_source | Source of payment | string | True | 40 | PAYER_REFUND ERA PATIENT_PAYMENT PATIENT_PAYMENT_VOID EOB LEGACY_PATIENT_EXTERNAL_TRANSFER LEGACY_PATIENT_EXTERNAL_TRANSFER_VOID LEGACY_PATIENT_PAYMENT LEGACY_PATIENT_PAYMENT_VOID PATIENT_REFUND PATIENT_EXTERNAL_TRANSFER_VOID PATIENT_EXTERNAL_TRANSFER PATIENT_EXTERNAL_TRANSFER_REFUND BUSINESS_UNIT_TRANSFER_RECEIVED BUSINESS_UNIT_TRANSFER_RECEIVE_REFUND BUSINESS_UNIT_TRANSFER_SENT |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| ledger_activity_date | Activity date of the financial transaction | timestamp | True |  |  |  |
| post_date_ld | Posted date of charge | date | True |  |  |  |
| adjudication_date_ld | The date when a payer approved payment for a claim. This field is automatically populated for ERAs but must be manually entered for EOBs. | timestamp | True |  |  |  |
| deposit_date_ld | Deposit date of payment | timestamp | True |  |  |  |
| follow_up_date | Date at which Financial Assignee will follow up on the Payer Payment. | date | True |  |  |  |
| service_date_from_ld | Date which service started. | timestamp | True |  |  |  |
| service_date_to_ld | Date which service ended. | timestamp | True |  |  |  |
| ledger_activity_date_ld | Activity date of the financial transaction | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## product_sales

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| product_sales_id | product_sales table id | string | False | 40 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| staff_id | staff table id | string | False | 20 | The staff member that performs the transaction |  |
| provider_id | staff table id | string | True | 20 | The provider designated on the transaction. |  |
| facility_id | facility table id | string | False | 20 | The facility location where the transcation was performed |  |
| sold_by_id | staff table id | string | True | 20 | The staff member selected in the Sold By field. The provider and the Sold by could be the same person depending on selection. |  |
| division_id | division table id | string | True | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 100 |  |  |
| charge_status | Charge Status | string | True | 10 | VOIDED NON_VOIDED |  |
| cpt_product | The code for the product or charge, or an inventory product code. In this table, bill related cpt/product will be stored as none. | string | True | 100 |  |  |
| cpt_product_description | The procedure or charge code description for the product, or the inventory product description. | string | True | 500 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| product_charge | Product unit charge | double | True |  |  |  |
| product_units | Number of units being sold | double | True |  |  |  |
| product_subtotal | Subtotal of transaction | double | True |  |  |  |
| product_discount_amount | Charge amount discounted in % or $ amount | double | True |  |  |  |
| product_discount_reason | Reason for discount | string | True | 22 | CUSTOM_DISCOUNT PACKAGES PROFESSIONAL_COURTESY PROMOTIONAL PACKAGES OTHER |  |
| custom_discount_reasons | Comma separated values for custom discount reasons. | string | True | 500 |  |  |
| product_local_tax_rate | Facility local tax rate | double | True |  |  |  |
| product_state_tax_rate | Facility state tax rate | double | True |  |  |  |
| product_total | Total charge after discounts and taxes are applied. | double | True |  |  |  |
| total_adjustments_itd | Total adjustments applied (inception to date). | double | True |  |  |  |
| financial_category | The Financial category related to the patient | string | True | 100 |  |  |
| time_zone | User time zone | string | True | 30 |  |  |
| transaction_date | Date of transaction | timestamp | True |  |  |  |
| service_date | Date of service | timestamp | True |  | This field can be change by the staff. |  |
| product_posted_date | Posted Date | timestamp | True |  | This field can be change by the staff. |  |
| transaction_date_ld | Date of transaction | timestamp | True |  |  |  |
| service_date_ld | Date of service | timestamp | True |  |  |  |
| product_posted_date_ld | Posted Date | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## unposted_charges

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| unposted_charges_id | unposted_charges table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| provider_id | staff table id | string | False | 20 | Billing provider id |  |
| primary_provider_id | staff table id | string | False | 20 | Primary provider listed on bill |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| financial_category_id | financial_category table id | string | True | 20 |  |  |
| primary_payer_id | payer table id | string | True | 55 | Payer listed on bill |  |
| financial_category | financial category name | string | True | 255 |  |  |
| primary_payer_name | Primary insurance company name for payment | string | True | 250 |  |  |
| remaining_charge_balance | Remaining charge balance per bill item | double | True |  |  |  |
| bill_type | Bill type | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| status | Current bill status | string | True | 40 | PRELIMINARY IN_PROGRESS REQUIRES_REVISION READY_FOR_REVIEW IN_REVIEW INACTIVE_OTHER RESOLVED_PAID RESOLVED_OTHER IN_DISPUTE PAYMENT_PENDING READY_FOR_POSTING |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or the inventory product code. | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code description for the bill charge or the inventory product description. | string | True | 500 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| service_date_to_ld | Date which service ended. | timestamp | True |  |  |  |
| service_date_from_ld | Date which service started. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## unbilled_posted_charges

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| unbilled_posted_charges_id | unbilled_posted_charges table id | string | False | 40 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 |  |  |
| facility_id | facility table id | string | False | 20 | Service location |  |
| provider_id | staff table id | string | False | 20 | Billing provider id |  |
| primary_provider_id | staff table id | string | True | 20 | Primary provider listed on bill |  |
| payer_id | payer table id | string | True | 20 | Payer listed on bill |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| patient_business_unit_id | patient_business_unit_setting table id | string | True | 30 |  |  |
| remaining_charge_balance | Remaining charge balance per bill item | double | True |  |  |  |
| coverage_type | Coverage type | string | True | 40 | Primary Secondary Tertiary Self-Pay |  |
| responsible_party | responsible party | string | True | 40 |  |  |
| status | Current bill status | string | True | 40 | PRELIMINARY IN_PROGRESS REQUIRES_REVISION READY_FOR_REVIEW IN_REVIEW INACTIVE_OTHER RESOLVED_PAID RESOLVED_OTHER IN_DISPUTE PAYMENT_PENDING READY_FOR_POSTING |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or the inventory product code. | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code description for the bill charge or the inventory product description. | string | True | 500 |  |  |
| encounter_count | Stores the associated bill_id. If not null, indicates an encounter has occurred and the sum of units posted or reversed within the bill is greater than zero. | string | True | 20 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| service_date_to_ld | Date which service ended. | timestamp | True |  |  |  |
| service_date_from_ld | Date which service started. | timestamp | True |  |  |  |
| post_date_ld | Date which charge posted. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payments_posted

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payments_posted_id | payments_posted table id | string | False | 60 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 | Billing provider id |  |
| primary_provider_id | staff table id | string | True | 20 | Primary provider listed on bill |  |
| payer_id | payer table id | string | True | 20 | Payer listed on bill |  |
| facility_id | facility table id | string | True | 20 | Service location |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| bill_id | bill table id | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 | Individual services on bill associated to payment |  |
| bill_insurance_id | bill_insurance table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| batch_id | batch table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| custom_payment_method_id | custom_payment_method table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| package_item_sale_id | package_item_sale table id | string | True | 20 |  |  |
| bill_assignee_id | bill_assignee table id. Id of the staff member assigned to follow up on payments. | string | True | 20 |  |  |
| firm_id | firm table id. | string | True | 20 |  |  |
| appointment_provider_id | staff table id for appointment provider. | string | True | 20 | Appointment Provider |  |
| original_bill_id | Bill table id. Indicates if a bill was recreated from a previous bill | string | True | 20 |  |  |
| sold_by_id | staff table id | string | True | 20 | The staff member selected in the Sold By field. The provider and the Sold by could be the same person depending on selection. |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| billing_quote_id | billing_quote table id | string | True | 20 |  |  |
| billing_quote_created_by_id | staff table id | string | True | 20 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| transaction_initiated_by_id | staff table id. | string | True | 20 | The person who ran the transaction, specifically patient payments, voids, or refund. This may also refer to the user who accepted a pending patient payment via external source. |  |
| payer_address_id | payer_address table id | string | True | 20 |  |  |
| provider_level_adjustment_id | provider_level_adjustment table id. | string | True | 40 |  |  |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 100 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| payer_check_key | Payer check key, used to link different payer payments to payment tables. | string | True | 20 |  |  |
| batch_name | Batch associated to the payment/refund | string | True | 100 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| coverage_type | Coverage type | string | True | 20 | Primary Secondary Tertiary Self-Pay |  |
| link_state | Stores the current state of the insurance in relation to the bill | string | True | 20 | LINKED UNLINKED REMOVED LEGACY_REMOVED |  |
| ledger_payment_amount | Total payment for service. | double | True |  |  |  |
| payment_method | Method of payment such as cash, check, e-check, credit card, gift card, etc. | string | True | 200 |  |  |
| payment_source | Source of payment | string | True | 200 |  |  |
| payment_link | Payment url for EMA | string | True | 100 |  |  |
| payment_code | Payment code associated with payment. | string | True | 20 | AVAILABLE COPAY PAYER_CHECK OMITTED_PAYER_CHECK PAYER_CHECK_CLAIM UNAVAILABLE |  |
| payment_code_description | payment_code meaning. | string | True | 20 | Deposits Copay Payer Check Payer Check Omitted Payer Check Claim General |  |
| payer_check_notes | payer check notes | string | True | 255 |  |  |
| ledger_reference | Ledger reference code. For Payers, this is the payment transaction number. For patients, this is the check number or a transaction id for other payment methods. | string | True | 100 |  |  |
| activity_type | Activity Type | string | True | 100 | PAYMENT PLA_OFFSET_CHARGE_PAYMENT PLA_POST_TO_SERVICE_LINE PLA_POST_TO_SVC_LINES VOID_PAYMENT VOID_PLA_OFFSET_CHARGE_PAYMENT VOID_PLA_POST_TO_SERVICE_LINE VOID_PLA_POST_TO_SVC_LINES |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or the inventory product description. | string | True | 500 |  |  |
| financial_category | The Financial category listed for the payer | string | True | 100 |  |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| payment_channel | The channel used for patient payments | string | True | 30 | STAFF TEXT_TO_PAY AUTOMATIC_PROCESSING KIOSK POCKET_PATIENT_ANDROID TERMINAL POCKET_PATIENT_IOS PATIENT_PORTAL QUICK_PAY PAYMENT_PLAN EXTERNAL_API ONLINE_CHECK_IN |  |
| bill_assignee_staff_name | Name of the staff member that is assigned to follow up on payments. | string | True | 200 |  |  |
| claim_insurance_key | A concatenation of bill item and billing insurance id which is linked to the claims that are sent out. This key is used to link the payments to the claims table. | string | True | 20 |  |  |
| is_legacy_payment | If True, payment was created before EMA tracked the relationship between payments received and payments posted. | boolean | True |  |  |  |
| transaction_identifier | Transaction Identifier. This value will be null for PLA transactions. | string | True | 40 |  |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| appointment_type | Appointment type. Types are confirmed by the practice at the firm admin level. | string | True | 25 |  |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| bill_type | Bill type. | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| responsible_insurance_policy_number | Insurance policy number. | string | True | 100 |  |  |
| policy_type | Insurance policy type. May have a null value. | string | True | 100 | EPO GHP HMO IPA MEDICARE_ADVANTAGE PPO POS COMMERCIAL_OTHER ACA_EXCHANGE CHAMPVA CHIP FECA MEDICARE MEDICAID TRICARE GOVERNMENT_OTHER VISION WORKERS_COMP AUTO_PIP B C Champus Choice Plus Exclusive Provider Organization (EPO) M O |  |
| policy_group_number | Insurance policy group number. | string | True | 100 |  |  |
| patient_relationship_to_policy_holder | Patient relationship to insurance policy holder. May have a null value. | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| policy_patient_name | Name of the policy holder listed for insurance. | string | True | 250 |  |  |
| policy_holder_gender | Policy holder Gender. May have a null value. | string | True | 20 | MALE, FEMALE, etc. |  |
| policy_holder_date_of_birth | Policy Holder Date Of Birth | timestamp | True |  |  |  |
| payer_plan_name | Payer's plan name. | string | True | 100 |  |  |
| product_category | Product category name | string | True | 100 |  |  |
| product_sku | Product sku | string | True | 100 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| service_location_pos_code | Place of service code listed on the bill. | string | True | 5 |  |  |
| notes | Notes. | string | True | 500 |  |  |
| quick_code | Reflects the quick code combination configured for the CPT/Modifier combination on the bill. These codes are configured by the practice. | string | True | 50 |  |  |
| bill_item_allowed | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| wrvu | CMS wRVU (work relative value units) for the associated Bill Item. | double | True |  |  |  |
| billing_quote_title | Title of billing quote | string | True | 100 |  |  |
| billing_quote_id_number | Client-facing billing quote id | string | True | 20 |  |  |
| firm_is_using_rcm | Whether using rcm is enabled | boolean | True |  |  |  |
| source_of_payment_typology | Source of Payment Typology | string | True | 100 |  |  |
| signature_on_file | If true, a practice can receive payment from an insurer on behalf of a patient. | boolean | True |  | True: Yes, False: No |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| package_sale_date_created_ld | Date on which the package was sold. | timestamp | True |  |  |  |
| service_date_from | Date which service started. Note: This column will be deprecated on our next release, please use service_date_from_ld column. | timestamp | True |  |  | True |
| service_date_to | Date which service ended. Note: This column will be deprecated on our next release, please use service_date_from_ld column. | timestamp | True |  |  |  |
| pla_reason | Provider level adjustment reason | string | True | 100 |  |  |
| authorization_number | Authorization number linked to insurance policy. | string | True | 50 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| ledger_activity_date | Activity date of the financial transaction. | timestamp | True |  |  |  |
| post_date_ld | Post date of payment for service line | date | True |  |  |  |
| adjudication_date_ld | The date when a payer approved payment for a claim. This field is automatically populated for ERAs but must be manually entered for EOBs. | timestamp | True |  |  |  |
| service_date_from_ld | Date which service started | timestamp | True |  |  |  |
| service_date_to_ld | Date which service ended | timestamp | True |  |  |  |
| ledger_activity_date_ld | Activity date of the financial transaction | timestamp | True |  |  |  |
| deposit_date_ld | Deposit date of payment for service line | timestamp | True |  |  |  |
| follow_up_date | Date at which Financial Assignee will follow up on the Payer Payment. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## era_received

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| era_received_id | era_received table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| payer_id | payer table id | string | True | 20 | System payer name selected by staff user and listed on the ERA |  |
| facility_id | facility table id | string | True | 20 |  |  |
| era_status | Payment status | string | True | 20 | ARCHIVED FAILED_PROCESSING FAILED NEW POSTED PROCESSING QUEUED |  |
| era_transaction_number | Payment reference number. In PM this number may also be referred to as the check/trace number or the Transaction number displayed on the ERA. | string | True | 50 |  |  |
| era_payment_method_code | Payer payment method code from the clearinghouse | string | True | 10 | BOP: Financial Institution Option / Balance of Payment NON: Non-payment FWT: Federal Reserve Fund / Wire Transfer CHK: Check ACH: Automated Clearinghouse |  |
| payer_name | Payer associated with ERA | string | True | 100 |  |  |
| era_payer_identifier | Payer identification number associated with ERA. This identifier is sent by the payer in the ERA. | string | True | 50 |  |  |
| era_total_amount | ERA total payment amount | double | True |  |  |  |
| era_received_date | Date which ERA was received | timestamp | True |  |  |  |
| era_deposit_date | Deposit date of ERA | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## transfer_funds

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| transfer_funds_id | transfer_funds table id | string | False | 40 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| from_patient_id | patient table id | string | True | 20 | The originating patient record from which funds were transferred |  |
| to_patient_id | patient table id | string | True | 20 | The recieving patient records to which funds are tranferred |  |
| facility_id | facility id | string | False | 20 |  |  |
| from_business_unit_id | business_unit table id | string | True | 20 | The originating business unit from which funds were transferred |  |
| to_business_unit_id | business_unit table id | string | True | 20 | The recieving business unit to which funds are tranferred |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| initiated_by_staff_id | staff table id | string | True | 20 |  |  |
| transaction_identifier | Transaction Identifier. | string | True | 40 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| amount | Amount transferred between patients or business units | double | True |  |  |  |
| transfer_type | Type of transfer. | string | True | 50 | EXTERNAL_TRANSFER PATIENT_TRANSFER BUSINESS_UNIT_TRANSFER |  |
| notes | Notes added for the transaction performed. The transfer notes can only be added during payment transfer by the staff member peforming the transfer. | string | True | -1 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| transaction_initiated_date | Activity date of the financial transaction | timestamp | True |  |  |  |
| transaction_initiated_date_ld | Activity date of the financial transaction | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## provider_level_adjustment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| provider_level_adjustment_id | provider_level_adjustment table id | string | False | 40 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 | Service Location |  |
| payer_id | payer table id | string | True | 20 | Payer that is selected for the payer payment |  |
| staff_id | staff table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| pla_action | PLA action. This reflects the action or behavior of the PLA as configured for the payer/code in the Firm admin. | string | True | 50 |  |  |
| trans_num | Transaction number | string | True | 50 |  |  |
| provider_identifier | Provider identifier. By default this is the provider NPI number. If the provider NPI number is not available, then this will be the provider database number. | string | True | 50 |  |  |
| reference_identifier | Reference identifier. Staff can select a specific claim or type in an id through free text option. | string | True | 50 |  |  |
| pla_reason | Provider level adjustment reason | string | True | 100 |  |  |
| notes | PLA notes. Free text field. | string | True | -1 |  |  |
| amount | PLA Amount | double | True |  | USD |  |
| coverage_type | Coverage type | string | True | 20 | Primary Secondary Tertiary Self-Pay |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| posted_date_ld | Posted date | date | True |  |  |  |
| transaction_date | Transaction date (system generated) | timestamp | True |  |  |  |
| fiscal_period | Fiscal date indicated for PLA | timestamp | True |  |  |  |
| deposit_date_ld | Deposit date of payer check | timestamp | True |  |  |  |
| transaction_date_ld | Transaction date (system generated) | timestamp | True |  |  |  |
| fiscal_period_ld | Fiscal date indicated for PLA | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_statement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_statement_id | patient_statement table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| statement_date | Date on which the statement was generated | timestamp | True |  |  |  |
| statement_number | Statement identifier | string | True | 20 |  |  |
| status | Status of the Statement. | string | True | 20 | DELETED FAILED ON_DEMAND QUEUED QUEUED_HELD QUEUED_SCRUB_FAILED SUCCESSFUL QUEUED_AUTO_HELD |  |
| note | Information on delivery of the statement. | string | True | 50 | AUTO_PAY_STATEMENT GENERATED_FOR_OFFICE_USER GIVEN_TO_PATIENT MAILED_TO_PATIENT AUTO_PAY_STATEMENT |  |
| total_insurance_due | Total insurance balance for service lines, noted on bill (not displayed on statement). | double | True |  |  |  |
| total_patient_due | Total patient balance for service lines | double | True |  |  |  |
| version | Version number of the statement | int | True |  |  |  |
| oldest_aging_balance | Text description of how long the balance has been left unpaid. | string | True | 20 |  |  |
| has_aging_balance_120_plus | Is the balance older than 120 days? | boolean | True |  |  |  |
| has_aging_balance_30_60 | Is the balance between 31 and 60 days old? | boolean | True |  |  |  |
| has_aging_balance_60_90 | Is the balance between 61 and 90 days old? | boolean | True |  |  |  |
| has_aging_balance_90_120 | Is the balance between 91 and 120 days old? | boolean | True |  |  |  |
| has_aging_balance_current | Is the balance between 0 and 30 days old (regardless of age)? | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## patient_statement_charge

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_statement_charge_id | patient_statement_charge table id | string | False | 20 |  |  |
| patient_statement_id | patient_statement table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 20 |  |  |
| statement_date | Date on which the statement was generated | timestamp | True |  |  |  |
| service_date | Date on which the service was provided | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## patient_payments_unposted

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_payments_unposted_id | patient_payments_unposted table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| facility_id | facility table id | string | False | 20 | Service location |  |
| provider_id | staff table id | string | True | 20 | Billing provider |  |
| created_by_staff_id | staff table id | string | True | 20 | Staff who transacted the payment |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| custom_payment_method_id | custom_payment_method table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| transaction_number | Payment transaction number (system generated) | string | True | 75 |  |  |
| payment_code | Payment code | string | True | 11 | UNAVAILABLE:General, COPAY:CoPay, AVAILABLE:Deposits |  |
| payment_method | Payment method. Can be configured by the practice in Firm admin. | string | True | 50 |  |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| payment_amount | Total payment amount | double | True |  |  |  |
| unallocated_amount | Amount of payment not posted to charge item | double | True |  |  |  |
| patient_balance | Total outstanding balance belonging to the patient | double | True |  |  |  |
| insurance_balance | Total outstanding balance belonging to the insurance | double | True |  |  |  |
| financial_category | Financial category listed for the patient | string | True | 100 |  |  |
| code_category | Code category name. Only present for deposit payment type, null otherwise. | string | True | 75 |  |  |
| payment_link | URL that links back to the payment transaction modal | string | True | 100 |  |  |
| appointment_type | If applicable, type of appointment linked to payment transaction | string | True | 25 |  |  |
| transaction_note | Notes regarding patient's method of payment | string | True | 3000 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| transaction_date | Transaction date of payment. | timestamp | True |  |  |  |
| transaction_date_ld | Transaction date of payment. | timestamp | True |  |  |  |
| deposit_date_ld | Deposit date of payment | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_adjustments

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_adjustments_id | payer_adjustments table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 | Service location |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| provider_id | staff table id | string | False | 20 | Billing provider |  |
| primary_provider_id | staff table id | string | False | 20 | Primary provider |  |
| payer_id | payer table id | string | True | 20 | Payer associated to payment and payment adjustment code |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 |  |  |
| bill_insurance_id | bill_insurance table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| appointment_provider_id | staff table id for appointment provider. | string | True | 20 | Appointment Provider |  |
| original_bill_id | Bill table id. Indicates if a bill was recreated from a previous bill | string | True | 20 |  |  |
| sold_by_id | staff table id | string | True | 20 | The staff member selected in the Sold By field. The provider and the Sold by could be the same person depending on selection. |  |
| payer_address_id | payer_address table id | string | True | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| billing_quote_id | billing_quote table id | string | True | 20 |  |  |
| billing_quote_created_by_id | staff table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| package_item_sale_id | package_item_sale table id | string | True | 20 |  |  |
| era_received_id | era_received table id | string | True | 20 |  |  |
| transaction_identifier | Transaction Identifier. Note: This column will be deprecated in release 1.24 and removed in 1.25. | string | True | 40 |  | True |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 100 |  |  |
| bill_item_adjustment_amount | Bill Item Adjustment. This is the amount of the adjustment. It can be positive or negative. A positive value reduces the charge balance, a negative value increases the charge balance. | double | True |  |  |  |
| bill_item_adjustment_carc | CARC number (payer only) | string | True | 10 |  |  |
| rarc_codes | List of RARC code associated with a bill item adjustment | string | True | 100 |  |  |
| bill_item_adjustment_group_code | Group code that describes what the CARC signifies (payer only). | string | True | 30 |  |  |
| bill_item_adjustment_qualifier | Payer or patient adjustment | string | True | 20 |  |  |
| bill_item_adjustment_status | Payer adjustment status (payer only). | string | True | 40 |  |  |
| denial_category | Denial Category. | string | True | 40 |  |  |
| is_custom_denial_category | Flag for custom denial Category. | boolean | True |  |  |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code for the bill charge | string | True | 500 |  |  |
| coverage_type | Coverage type | string | True | 10 | Primary Secondary Tertiary Self-Pay |  |
| link_state | Stores the current state of the insurance in relation to the bill | string | True | 20 | LINKED UNLINKED REMOVED LEGACY_REMOVED |  |
| bill_item_adjustment_reason_code | Reason code. Payer reason code or code manually entered by the staff | string | True | 25 |  |  |
| bill_item_adjustment_reason_code_description | Description of Reason code. | string | True | 1000 |  |  |
| units | Bill item units | double | True |  |  |  |
| charge_amount_original | Original amount of the charge associated with the adjustment. | double | True |  |  |  |
| bill_type | Bill type | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| financial_category | The Financial category listed for the payer | string | True | 100 |  |  |
| policy_type | Payer policy type. May have a null value. | string | True | 100 | EPO GHP HMO IPA MEDICARE_ADVANTAGE PPO POS COMMERCIAL_OTHER ACA_EXCHANGE CHAMPVA CHIP FECA MEDICARE MEDICAID TRICARE GOVERNMENT_OTHER VISION WORKERS_COMP AUTO_PIP B C Champus Choice Plus Exclusive Provider Organization (EPO) M O |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| voided_adjustment | Indicates if an adjustment has been voided | boolean | True |  |  |  |
| deposit_date | Date payment associated with an adjustment was deposited | date | True |  |  |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| activity_type | Activity Type. | string | True | 1000 | ADJUSTMENT VOID_ADJUSTMENT |  |
| appointment_type | Appointment type. Types are confirmed by the practice at the firm admin level. | string | True | 25 |  |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| responsible_insurance_policy_number | Insurance policy number. | string | True | 100 |  |  |
| policy_group_number | Insurance policy group number. | string | True | 100 |  |  |
| patient_relationship_to_policy_holder | Patient relationship to insurance policy holder. May have a null value. | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| policy_patient_name | Name of the policy holder listed for insurance. | string | True | 250 |  |  |
| policy_holder_gender | Policy holder Gender. May have a null value. | string | True | 20 | MALE, FEMALE, etc. |  |
| policy_holder_date_of_birth | Policy Holder Date Of Birth | timestamp | True |  |  |  |
| payer_plan_name | Payer's plan name. | string | True | 100 |  |  |
| product_category | Product category name | string | True | 100 |  |  |
| product_sku | Product sku | string | True | 100 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| service_location_pos_code | Place of service code listed on the bill. | string | True | 5 |  |  |
| notes | Notes. | string | True | 300 |  |  |
| quick_code | Reflects the quick code combination configured for the CPT/Modifier combination on the bill. These codes are configured by the practice. | string | True | 50 |  |  |
| bill_item_allowed | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| wrvu | CMS wRVU (work relative value units) for the associated Bill Item. | double | True |  |  |  |
| billing_quote_title | Title of billing quote | string | True | 100 |  |  |
| billing_quote_id_number | Client-facing billing quote id | string | True | 20 |  |  |
| firm_is_using_rcm | Whether using rcm is enabled | boolean | True |  |  |  |
| source_of_payment_typology | Source of Payment Typology | string | True | 100 |  |  |
| signature_on_file | If true, a practice can receive payment from an insurer on behalf of a patient. | boolean | True |  | True: Yes, False: No |  |
| package_name | Package name. | string | True | 50 |  |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| package_sale_date_created_ld | Date on which the package was sold. | timestamp | True |  |  |  |
| bill_item_charge_amount | Total charge for the bill item. | double | True |  |  |  |
| bill_item_adjustment_equal_to_charge | Calulcated field. 'Yes' value is set when the adjustement amount is equal to the bill item charge amount. | string | True | 3 | Yes No |  |
| adjustment_reason | Adjustment reason description. | string | True | 1000 |  |  |
| claim_insurance_key | A concatenation of of bill item and billing insurance id which is linked to the claims which are sent out. | string | True | 40 |  |  |
| bill_item_date_created | Date bill item was created (system generated) | timestamp | True |  |  |  |
| bill_item_date_created_ld | Date bill item was created (system generated) | timestamp | True |  |  |  |
| rcm_transaction_responsible | Transaction responsibility flag for RCM | string | True | 25 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| bill_item_adjustment_accounting_date | Date that the adjustment was added to the bill item (system generated) | timestamp | True |  |  |  |
| bill_item_adjustment_posted_date_ld | Posted date | timestamp | True |  |  |  |
| bill_item_adjustment_transaction_date | Transaction date (system generated) | timestamp | True |  |  |  |
| service_date_from | Date which service started | timestamp | True |  |  |  |
| service_date_to | Date which service ended | timestamp | True |  |  |  |
| bill_item_adjustment_accounting_date_ld | Date that the adjustment was added to the bill item (system generated) | timestamp | True |  |  |  |
| bill_item_adjustment_transaction_date_ld | Transaction date (system generated) | timestamp | True |  |  |  |
| service_date_from_ld | Date which service started | timestamp | True |  |  |  |
| service_date_to_ld | Date which service ended | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_adjustments_detail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_adjustments_detail_id | payer_adjustments_detail table id | string | False | 60 |  |  |
| claim_id | claim table id | string | False | 20 |  |  |
| bill_item_id | bill_item table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| claim_bill_item_id | claim_bill_item table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| carc | Claim Adjustment Reason Code (CARC). Convey information about remittance processing | string | True | 10 |  |  |
| carc_description | The description associated with the given carc code. | string | True | 1000 |  |  |
| rarc_code | Remittance Advice Remark Codes (RARCs). Provide additional explanation for an adjustment already described by a Claim Adjustment Reason Code | string | True | 60 |  |  |
| rarc_code_description | The description associated with the given rarc code. | string | True | 1000 |  |  |
| bill_item_adjustment_reason_code | Group code that describes what the CARC signifies (payer only). | string | True | 30 |  |  |
| default_denial_category | Denial Category. | string | True | 40 | BILLING_OR_CLAIM_ERROR ADDITIONAL_INFORMATION CREDENTIALING_OR_ENROLLMENT DUPLICATE ADJUDICATION OTHER COORDINATION_OF_BENEFITS OTHER_COVERAGE BENEFIT_MAX AUTHORIZATION MEDICAL_NECESSITY CODING TIMELY_FILING NON_COVERED ELIGIBILITY |  |
| custom_denial_category |  | string | True | 40 |  |  |
| custom_denial_reason_category | Custom claim adjustment denial reason category. | string | True | 30 |  |  |
| custom_adjustment_code_description | Custom claim adjustment denial reason category description. | string | True | 1000 |  |  |
| denied_item | Flag indicating it the bill_item has been associated with a denial. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_adjustments_rarc

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_adjustments_rarc_id | payer_adjustments_rarc table id | string | False | 30 |  |  |
| payer_adjustments_id | payer_adjustments table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| rarc_code | RARC code | string | True | 60 |  |  |
| description | RARC code description | string | True | 800 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payer_payments_unposted

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payer_payments_unposted_id | payer_payments_unposted table id | string | False | 60 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| payer_id | payer table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| payer_check_key | Payer check key, used to link different payer payments to payment tables. | string | True | 20 |  |  |
| payer_check_transaction_number | Payment reference number. In PM this number may also be referred to as the check/trace number or the Transaction number | string | True | 50 |  |  |
| payer_check_format | Format of payer payment. This indicates whether payment was sent electronically from clearinghouse (ERA) or entered manually by practice (EOB). | string | True | 20 | ERA EOB |  |
| payer_check_amount | Amount of payer payment | double | True |  |  |  |
| payer_check_unposted_amount | Amount of payer payment that has not been posted to services. | double | True |  |  |  |
| payer_check_notes | Payer check notes entered by the practice | string | True | 255 |  |  |
| financial_category | The Financial Category listed for the payer | string | True | 100 |  |  |
| payer_check_payment_method | Payment method | string | True | 20 | Payer Check Payer E-Check Payer EFT Payer Credit Card Payer Non-Payment Payer Other Patient Refund |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| payment_link | URL that links back to the payment transaction modal | string | True | 100 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| payer_check_entered_date | Date payer check was entered | timestamp | True |  |  |  |
| payer_check_entered_date_ld | Date payer check was entered | timestamp | True |  |  |  |
| payer_check_deposit_date_ld | Payer check deposit date | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## transaction_settlement

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| transaction_settlement_id | transaction_settlement table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| transaction_settlement_link_key | External UUID that identifies a Transaction (PAYFAC Session), shared between EMA and PAYFAC. | string | True | 50 |  |  |
| funding_status | Transaction Processor Funding Status. | string | True | 10 | AUTH_ONLY DECLINED FUNDED INCOMPLETE IN_QUEUE ON_HOLD REJECTED SUBMITTED |  |
| transaction_amount | Amount of the Payment submitted to Transaction Processor | double | True |  |  |  |
| fee_amount | Amount of Fees charged by Transaction Processor | double | True |  |  |  |
| funded_amount | Amount funded, net of Fees, received from Transaction Processor | double | True |  |  |  |
| funded_date | Date at which Funded Amount was funded by Transaction Processor | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## transaction_settlement_refund

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| transaction_settlement_refund_id | transaction_settlement_refund table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| transaction_settlement_id | transaction_settlement table id | string | True | 50 |  |  |
| transaction_settlement_link_key | External UUID that identifies a Transaction (PAYFAC Session), shared between EMA and PAYFAC. | string | True | 50 |  |  |
| funding_status | Transaction Processor Funding Status. | string | True | 10 | AUTH_ONLY DECLINED FUNDED INCOMPLETE IN_QUEUE ON_HOLD REJECTED SUBMITTED |  |
| transaction_amount | Amount of the Payment (or Refund) submitted to Transaction Processor | double | True |  |  |  |
| fee_amount | Amount of Fees charged by Transaction Processor | double | True |  |  |  |
| funded_amount | Amount funded (or refunded), net of Fees, received from Transaction Processor | double | True |  |  |  |
| funded_date | Date at which Funded Amount was funded by Transaction Processor | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## payments_received

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| payments_received_id | payments_received table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| payer_id | payer table id | string | True | 20 |  |  |
| facility_id | facility table id | string | False | 20 | Service location |  |
| provider_id | staff table id | string | True | 20 | Billing provider |  |
| created_by_staff_id | staff table id | string | True | 20 | Staff who transacted the payment |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| batch_id | batch table id | string | True | 20 |  |  |
| code_category_id | code_category table id. Only present for deposit payment type, null otherwise. | string | True | 20 |  |  |
| custom_payment_method_id | custom_payment_method table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| bill_assignee_id | bill_assignee table id. Id of the staff member assigned to follow up on payments. | string | True | 20 |  |  |
| transaction_settlement_link_key | External UUID that identifies a Transaction (PAYFAC Session), shared between EMA and PAYFAC. | string | True | 50 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| original_payment_link_key | Linking key that ties transaction to original payment. This column will have a null value unless the transaction is a refund. | string | True | 100 |  |  |
| payer_check_key | Payer check key, used to link different payer payments to payment tables. | string | True | 20 |  |  |
| reference_number | Payment reference number. In PM this number may also be referred to as the check/trace number or the Transaction number | string | True | 60 |  |  |
| code_category | Code category name. Only present for deposit payment type, null otherwise. | string | True | 75 |  |  |
| batch_name | Batch payment name. | string | True | 100 |  |  |
| package_name | Package name. | string | True | 50 |  |  |
| payment_code | Payment code | string | True | 11 | UNAVAILABLE:General, COPAY:CoPay, AVAILABLE:Deposits |  |
| payment_source | Source of payment | string | True | 40 | PAYER_REFUND ERA PATIENT_PAYMENT PATIENT_PAYMENT_VOID EOB LEGACY_PATIENT_EXTERNAL_TRANSFER LEGACY_PATIENT_EXTERNAL_TRANSFER_VOID LEGACY_PATIENT_PAYMENT LEGACY_PATIENT_PAYMENT_VOID PATIENT_REFUND PATIENT_EXTERNAL_TRANSFER_VOID PATIENT_EXTERNAL_TRANSFER PATIENT_EXTERNAL_TRANSFER_REFUND BUSINESS_UNIT_TRANSFER_RECEIVED BUSINESS_UNIT_TRANSFER_RECEIVE_REFUND BUSINESS_UNIT_TRANSFER_SENT |  |
| payment_channel | The channel used for patient payments | string | True | 30 | STAFF TEXT_TO_PAY AUTOMATIC_PROCESSING KIOSK POCKET_PATIENT_ANDROID TERMINAL POCKET_PATIENT_IOS PATIENT_PORTAL QUICK_PAY PAYMENT_PLAN EXTERNAL_API ONLINE_CHECK_IN |  |
| payment_processor | Method by which payment was processed | string | True | 50 | EXTERNAL_TRANSFER MODMED PATIENT_CREDIT INSTAMED PATIENT_TRANSFER MANUAL BUSINESS_UNIT_TRANSFER PAYFAC NONE PAYJUNCTION MMPAY |  |
| payment_amount | Total payment amount | double | True |  |  |  |
| unposted_amount | Amount of payment that has not been posted to a service | double | True |  |  |  |
| omitted_amount | Amount of payment that has been omitted | double | True |  |  |  |
| original_amount | Amount of payment that initialized the unallocated fund | double | True |  |  |  |
| payment_link | URL that links back to the payment transaction modal | string | True | 100 |  |  |
| payer_payment_status | Status of payer payment. If patient payment, this column will be null. | string | True | 25 | PARTIALLY_POSTED POSTED UNPOSTED |  |
| patient_payment_status | Status of patient payment. If payer payment, this column will be null. | string | True | 25 | UNPOSTED: None of the payment has been posted to a charge. PARTIALLY_POSTED: Some of the payment has been posted to a charge. POSTED: All of the payment has been posted to a charge. UNKONWN: The payment was made prior to 2019 and the associated funds bucket (unallocated fund) has not been depleted. Prior to 2019, all payments were assigned to the same funds bucket, and it was therefore not possible to determine which dollars came from which payment. |  |
| payment_method | Method of payment such as cash, check, e-check, credit card, gift card, etc. | string | True | 60 |  |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| credit_card_type | Type of credit card used for payments with payment method of credit card | string | True | 20 |  |  |
| credit_card_last_four_digits | Last four digits of the credit card used for payments with payment method of credit card | string | True | 20 |  |  |
| patient_auto_pay_status | Status of Patient's Auto Pay | string | True | 20 | ACTIVE CANCELLED DEACTIVATED DECLINED PENDING |  |
| bill_assignee_staff_name | Name of the staff member that is assigned to follow up on payments. | string | True | 200 |  |  |
| notes | Notes entered for payment transaction | string | True | -1 |  |  |
| financial_category | The Financial Category listed for the responsible party. | string | True | 100 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| transaction_date | Transaction date (system date) | timestamp | True |  |  |  |
| transaction_date_ld | Transaction date (system date) | timestamp | True |  |  |  |
| deposit_date_ld | Deposit date of payment | timestamp | True |  |  |  |
| adjudication_date_ld | The date when a payer approved payment for a claim. This field is automatically populated for ERAs but must be manually entered for EOBs. | timestamp | True |  |  |  |
| follow_up_date | Date at which Financial Assignee will follow up on the Payer Payment. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_adjustments

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_adjustments_id | patient_adjustments table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| provider_id | staff table id for current provider. | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| custom_patient_adjustment_code_id | custom_patient_adjustment_code table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| primary_provider_id | staff table id for primary provider. | string | True | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| appointment_provider_id | staff table id for appointment provider. | string | True | 20 | Appointment Provider |  |
| original_bill_id | Bill table id. Indicates if a bill was recreated from a previous bill | string | True | 20 |  |  |
| sold_by_id | staff table id | string | True | 20 | The staff member selected in the Sold By field. The provider and the Sold by could be the same person depending on selection. |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| billing_quote_id | billing_quote table id | string | True | 20 |  |  |
| billing_quote_created_by_id | staff table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| package_item_sale_id | package_item_sale table id | string | True | 20 |  |  |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 100 |  |  |
| transaction_identifier | Transaction Identifier. Note: This column will be deprecated in release 1.24 and removed in 1.25. | string | True | 40 |  | True |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or the inventory product description. | string | True | 500 |  |  |
| patient_adjustment_amount | Bill item or charge adjustment amount. This is the amount of the adjustment. It can be positive or negative. A positive value reduces the charge balance, a negative value increases the charge balance. | double | True |  |  |  |
| patient_adjustment_reason_code | Adjustment reason code | string | True | 50 |  |  |
| adjustment_code_type | Patient adjustment type. For types other than bad debt and collection are considered to be adjustments. May have a null value. | string | True | 10 | BAD_DEBT COLLECTION NONE |  |
| adjustment_code_name | Adjustment code | string | True | 25 |  |  |
| code_description | Adjustment description | string | True | 50 |  |  |
| bill_item_adjustment_qualifier | Payer or patient adjustment | string | True | 20 | PAYER PATIENT |  |
| charge_amount_original | Original amount of the charge associated with the adjustment. | double | True |  |  |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| activity_type | Activity Type. | string | True | 1000 | ADJUSTMENT VOID_ADJUSTMENT CHARGE_ADJUSTMENT VOID_CHARGE_ADJUSTMENT DISCOUNT |  |
| appointment_type | Appointment type. Types are confirmed by the practice at the firm admin level. | string | True | 25 |  |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| bill_type | Bill type. | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| product_category | Product category name | string | True | 100 |  |  |
| product_sku | Product sku | string | True | 100 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| service_location_pos_code | Place of service code listed on the bill. | string | True | 5 |  |  |
| notes | Notes. | string | True | 300 |  |  |
| financial_category | Financial category associated to payer or patient. | string | True | 100 |  |  |
| quick_code | Reflects the quick code combination configured for the CPT/Modifier combination on the bill. These codes are configured by the practice. | string | True | 50 |  |  |
| bill_item_allowed | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| wrvu | CMS wRVU (work relative value units) for the associated Bill Item. | double | True |  |  |  |
| billing_quote_title | Title of billing quote | string | True | 100 |  |  |
| billing_quote_id_number | Client-facing billing quote id | string | True | 20 |  |  |
| firm_is_using_rcm | Whether using rcm is enabled | boolean | True |  |  |  |
| package_name | Package name. | string | True | 50 |  |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| package_sale_date_created_ld | Date on which the package was sold. | timestamp | True |  |  |  |
| adjustment_reason | Adjustment reason description. | string | True | 1000 |  |  |
| bill_item_adjustment_reason_code | Reason code. Payer or patient reason code or code manually entered by the staff.. | string | True | 45 |  |  |
| bill_item_adjustment_carc | CARC. | string | True | 10 |  |  |
| bill_item_adjustment_status | Payer adjustment status. | string | True | 20 | ON_HOLD TRANSFER_RESPONSIBILITY WRITE_OFF IGNORE |  |
| coverage_type | Coverage type | string | True | 20 | Primary Secondary Tertiary Self-Pay |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| service_date_from | Date which service started. | timestamp | True |  |  |  |
| service_date_to | Date which service ended. | timestamp | True |  |  |  |
| bill_item_adjustment_account_date | Date that the adjustment was added to the bill item (system generated). | timestamp | True |  |  |  |
| bill_item_adjustment_transaction_date | Transaction date (system generated). | timestamp | True |  |  |  |
| posted_date_ld | Post date of service. | date | True |  |  |  |
| service_date_from_ld | Service data from. | timestamp | True |  |  |  |
| service_date_to_ld | Date which service ended. | timestamp | True |  |  |  |
| bill_item_adjustment_account_date_ld | Date that the adjustment was added to the bill item (system generated). | timestamp | True |  |  |  |
| bill_item_adjustment_transaction_date_ld | Transaction date (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_id | claim table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| bill_insurance_id | bill_insurance table id | string | False | 20 |  |  |
| claim_assignee_id | bill_assignee table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| claim_identifier | Claim identifier displayed on the claim. | string | True | 20 |  |  |
| claim_status | Claim status | string | True | 60 | APPEALED_CLAIM BATCHED_FOR_PRINTING CLAIM_NOT_ON_FILE CORRECTED_CLAIM_SENT DENIAL_ASSESSMENT_PENDING DENIED FLAGGED_FOR_DENIAL_REVIEW INACTIVE_DUPLICATE INACTIVE_VOIDED INSURANCE_REPROCESSING INVALID IN_DISPUTE MEDICAL_RECORDS_SENT ON_HOLD PAYMENT_PENDING PENDING_ADJUSTMENT_WRITE_OFF QUEUED READY_FOR_POSTING READY_FOR_SENDING REJECTED RESOLVED_OTHER RESOLVED_PAID CLAIM_NOT_ON_FILE REVIEW_NEEDED |  |
| claim_payer | Payer linked to claim | string | True | 200 |  |  |
| claim_type | Claim types. | string | True | 40 | NEW VOIDED REPLACEMENT CORRECTED CROSSOVER |  |
| claim_format_type | Formats types of claim submission. | string | True | 40 | ELECTRONIC_5010 PAPER |  |
| claim_assignee_type | Indicates if claim is assigned to a group or individual staff member. May have a null value. | string | True | 20 | BILL_ASSIGNEE_GROUP FIRM_GROUP STAFF |  |
| claim_assignee | Name of the Individual staff member assigned to the claim. If staff member does not exist then the claim assignee group name will be listed instead. | string | True | 400 |  |  |
| last_assignee | Name of the Individual staff member who was last assigned to the claim. | string | True | 200 |  |  |
| current_assignee | Name of the Individual staff member currently assigned to the claim. | string | True | 200 |  |  |
| average_days_assigned | Average number of days the claim has been assigned to a user (calculated field). | double | True |  |  |  |
| days_assigned_to_current_assignee | Number of days the claim has been assigned to current assignee (calculated field). | int | True |  |  |  |
| times_reassigned | Indicates how many times a claim has been reassigned. | int | True |  |  |  |
| employment_related | Accident or Injury type flag. | boolean | True |  |  |  |
| auto_accident_related | Accident or Injury type flag. | boolean | True |  |  |  |
| other_accident_related | Accident or Injury type flag. | boolean | True |  |  |  |
| claim_item_was_denied | If a bill item associated with the claim was ever denied. | boolean | True |  |  |  |
| auto_accident_related_state | Auto accident related state. | string | True | 2 |  |  |
| follow_up_action | Follow up action | string | True | 40 | ACCESSED_PAYER_PORTAL_NO_UPDATE ADJUSTMENT_REQUEST CLAIM_REPROCESSING CORRECTED_CLAIM_SUBMISSION_ELECTRONIC CORRECTED_CLAIM_SUBMISSION_PAPER INITIAL_APPEAL_ELECTRONIC INITIAL_APPEAL_PAPER INITIAL_SUBMISSION LEFT_VOICEMAIL_FOR_PAYER LONG_HOLD_TIME MEDICAL_RECORDS_SENT_ELECTRONIC MEDICAL_RECORDS_SENT_PAPER OTHER PAYMENT_DETAILS_SUBMITTED_VIA_PHONE PAYMENT_DETAILS_SUBMITTED_VIA_PORTAL PENDING_ADMIN_EVALUATION PENDING_ONLINE_ACCESS PENDING_REMIT_INFORMATION REASSIGNED RESUBMISSION_INITIAL_APPEAL RESUBMISSION_INITIAL_APPEAL_ELECTRONIC SECOND_LEVEL_APPEAL_ELECTRONIC SECOND_LEVEL_APPEAL_PAPER |  |
| follow_up_date | Most recent follow up date for claim | timestamp | True |  |  |  |
| follow_up_next_action | Follow up action | string | True | 40 | ATTACH_MEDICAL_RECORDS CHECK_APPEAL_STATUS CHECK_CLAIM_STATUS CONFIRM_CREDENTIALING_STATUS CONFIRM_PAYMENT_POSTING CONTACT_PATIENT CONTACT_PAYER GENERATE_APPEAL OTHER REQUEST_APPROVAL REQUEST_AUTHORIZATION REQUEST_SUPPORT RESEARCH_DENIAL_FURTHER REVIEW_AUTHORIZATION_STATUS REVIEW_DIAGNOSIS_CODE REVIEW_FOR_ADJUSTMENT REVIEW_FOR_APPEAL REVIEW_MODIFIER REVIEW_PROCEDURE_CODE UPDATE_INSURANCE UPDATE_PATIENT_DEMOGRAPHICS |  |
| include_zero_dollar_services | Flag indicating whether to include $0 services. | boolean | True |  |  |  |
| applied_adjustments_total | Total of the adjustments applied to the bill | decimal(10,2) | True |  |  |  |
| patient_responsible_total | Patient total | decimal(10,2) | True |  |  |  |
| payments_total | Payments total | decimal(10,2) | True |  |  |  |
| latest_claim_status_accepted | Indicates if the most recent claim status has been accepted | boolean | True |  |  |  |
| latest_claim_status_source | Claim status source | string | True | 20 |  |  |
| latest_facility_submission_form | Most recent form submitted for a claim | string | True | 15 |  |  |
| contains_only_em_codes | If CPT codes are only E/M codes | boolean | True |  |  |  |
| contains_an_em_code | If CPT codes contain E/M codes | boolean | True |  |  |  |
| claim_was_ever_denied | When true it indicates that the claim has been in a "DENIED" status at least once | boolean | True |  |  |  |
| claim_was_ever_invalid | When true it indicates that the claim has been in an "INVALID" status at least once | boolean | True |  |  |  |
| claim_was_ever_rejected | When true it indicates that the claim has been in a "REJECTED" status at least once | boolean | True |  |  |  |
| claim_was_ever_denied_invalid_rejected | When true it indicates that the claim has been in any of the following statuses at least once: "DENIED", "INVALID", "REJECTED". | boolean | True |  |  |  |
| latest_claim_status_effective_date | Effective date of the most recent claim status | timestamp | True |  |  |  |
| claim_submission_date | Date claim was submitted to responsible party | timestamp | True |  |  |  |
| status_update_date | Date of status update | timestamp | True |  |  |  |
| claim_latest_denial_date | Date of latest claim denial | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_bill_item

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_bill_item_id | claim_bill_item table id | string | False | 20 |  |  |
| claim_id | claim table id | string | False | 20 |  |  |
| bill_item_id | bill_item table id | string | False | 20 |  |  |
| bill_insurance_id | bill_insurance table id | string | False | 20 |  |  |
| bill_assignee_id | bill_assignee table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| is_em_code | If CPT code is an E/M code | boolean | True |  |  |  |
| delinquency | Indicates whether a bill falls into a delinquent status. For a bill to be marked as Delinquent, current bill status and claim is not "Resolved/Other", "Inactive", or "Resolved/Paid", the bill is assigned to a user or user group, and current date is 3 days past the selected follow-up date. If a bill does not meet this criteria, it will be marked as Not Delinquent. | string | True | 20 |  |  |
| delinquency_days | This is the number of days since follow up date from current date minus 3 days | int | True |  |  |  |
| adjustments_total | Adjustment total | double | True |  |  |  |
| payments_total | Payments total | double | True |  |  |  |
| bill_item_was_denied | If the bill item was ever denied for a claim. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_log_id | claim_log table id | string | False | 20 |  |  |
| claim_id | claim table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| claim_created_by_staff_id | staff table id | string | True | 20 |  |  |
| event_triggered_by_staff_id | staff table id | string | True | 20 |  |  |
| claim_identifier | Claim identifier displayed on the claim. | string | True | 20 |  |  |
| event_type | Type of event logged in claim | string | True | 40 | BILL_INSURANCE_LINK BILL_INSURANCE_UNLINK CLAIM_PRINTED CLAIM_SCRUB_RULE_FAILURE CLAIM_SCRUB_RULE_OVERRIDE CLAIM_STATUS_CHANGE CLAIM_STATUS_INQUIRY_BATCH CLAIM_STATUS_INQUIRY_BATCH_RESPONSE CLAIM_STATUS_REFERENCE CLAIM_SUBMISSION_REFERENCE CROSSOVER_CLAIM_CREATION DENIAL_ASSESSMENT_ATTEMPT_FAILED DENIAL_ASSESSMENT_DISMISSED DENIAL_ASSESSMENT_NOT_IMPLEMENTED DENIAL_ASSESSMENT_PASSED DENIAL_ASSESSMENT_REQUEST_ERROR DENIAL_ASSESSMENT_REASON_DISMISSED DENIAL_ASSESSMENT_RESPONSE_IGNORED DENIAL_ASSESSMENT_RESPONSE_TIMED_OUT ERA_ASSOCIATE ERA_DISASSOCIATE FLAGGED_FOR_DENIAL_REVIEW FOLLOW_UP_ACTION_CHANGE FOLLOW_UP_DATE_CHANGE FOLLOW_UP_NEXT_ACTION_CHANGE PM_NOTE_REFERENCE REALTIME_CLAIM_STATUS_CHECK REMOVE_CLAIM_SCRUB_RULE_OVERRIDE TIMELY_FILING_OVERDUE TIMELY_FILING_WARNING_SENT |  |
| claim_status_changed_to | Claim status changed to new status | string | True | 30 | APPEALED_CLAIM BATCHED_FOR_PRINTING CLAIM_NOT_ON_FILE CORRECTED_CLAIM_SENT DENIAL_ASSESSMENT_PENDING DENIED FLAGGED_FOR_DENIAL_REVIEW INACTIVE_DUPLICATE INACTIVE_VOIDED INSURANCE_REPROCESSING INVALID IN_DISPUTE MEDICAL_RECORDS_SENT ON_HOLD PAYMENT_PENDING PENDING_ADJUSTMENT_WRITE_OFF QUEUED READY_FOR_POSTING READY_FOR_SENDING REJECTED RESOLVED_OTHER RESOLVED_PAID CLAIM_NOT_ON_FILE REVIEW_NEEDED |  |
| additional_information | Additional information for the claim event | string | True | 1500 |  |  |
| follow_up_action | Follow up action | string | True | 50 | ACCESSED_PAYER_PORTAL_NO_UPDATE ADJUSTMENT_REQUEST CLAIM_REPROCESSING CORRECTED_CLAIM_SUBMISSION_ELECTRONIC CORRECTED_CLAIM_SUBMISSION_PAPER INITIAL_APPEAL_ELECTRONIC INITIAL_APPEAL_PAPER INITIAL_SUBMISSION LEFT_VOICEMAIL_FOR_PAYER LONG_HOLD_TIME MEDICAL_RECORDS_SENT_ELECTRONIC MEDICAL_RECORDS_SENT_PAPER OTHER PAYMENT_DETAILS_SUBMITTED_VIA_PHONE PAYMENT_DETAILS_SUBMITTED_VIA_PORTAL PENDING_ADMIN_EVALUATION PENDING_ONLINE_ACCESS PENDING_REMIT_INFORMATION REASSIGNED RESUBMISSION_INITIAL_APPEAL RESUBMISSION_INITIAL_APPEAL_ELECTRONIC SECOND_LEVEL_APPEAL_ELECTRONIC SECOND_LEVEL_APPEAL_PAPER |  |
| latest_claim_log | Identifies top row(s) of claim logs for the specific claim | boolean | True |  |  |  |
| follow_up_next_action | Follow up action | string | True | 40 | ATTACH_MEDICAL_RECORDS CHECK_APPEAL_STATUS CHECK_CLAIM_STATUS CONFIRM_CREDENTIALING_STATUS CONFIRM_PAYMENT_POSTING CONTACT_PATIENT CONTACT_PAYER GENERATE_APPEAL OTHER REQUEST_APPROVAL REQUEST_AUTHORIZATION REQUEST_SUPPORT RESEARCH_DENIAL_FURTHER REVIEW_AUTHORIZATION_STATUS REVIEW_DIAGNOSIS_CODE REVIEW_FOR_ADJUSTMENT REVIEW_FOR_APPEAL REVIEW_MODIFIER REVIEW_PROCEDURE_CODE UPDATE_INSURANCE UPDATE_PATIENT_DEMOGRAPHICS |  |
| date_created | Date the claim_log record was created (database generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_bill_item_denial_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_bill_item_denial_category_id | claim_bill_item_denial_category table id | string | False | 60 |  |  |
| claim_bill_item_id | claim_bill_item table id | string | False | 20 |  |  |
| claim_id | claim table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| default_denial_category | Default denial category. | string | True | 40 |  |  |
| custom_denial_category | Custom denial category set by firm admin. | string | True | 40 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_submission

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_submission_id | claim_submission table id | string | False | 20 |  |  |
| claim_id | claim table id | string | True | 20 |  |  |
| contracted_payer_address_id | payer_address table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| submission_type | Type of submission | string | True | 25 | CREATE_AND_HOLD PRINT_TO_FORM SUBMIT_TO_PRINT_QUEUE SUBMIT_TO_QUEUE WAITING_FOR_PAYMENT |  |
| claim_type | Type of claim | string | True | 20 | CROSSOVER NEW REPLACEMENT VOIDED |  |
| auto_accident_related_state | If auto-accident related, state (subdivision) associated with the claim. | string | True | 2 |  |  |
| related_claim_identifier | Identifier of Claim related to claim submission | string | True | 50 |  |  |
| facility_submission_form | Form used to submit claim. | string | True | 10 | CMS_1500 UB_04 |  |
| auto_accident_related | Flag indicating whether claim is related to an auto accident. | boolean | True |  |  |  |
| other_accident_related | Flag indicating whether claim is related to some other accident. | boolean | True |  |  |  |
| employment_related | Flag indicating whether claim is related to employement. | boolean | True |  |  |  |
| include_zero_dollar_services | Flag indicating whether to include $0 services. | boolean | True |  |  |  |
| submission_date | Date on which submission was sent. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## claim_submission_bill_item

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_submission_bill_item_id | claim_submission_bill_item table id | string | False | 20 |  |  |
| claim_submission_id | claim_submission table id | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## claim_submission_change

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_submission_change_id | claim_submission_change table id | string | False | 20 |  |  |
| claim_id | claim table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| old_claim_submission_id | claim_submission table id | string | True | 20 |  |  |
| new_claim_submission_id | claim_submission table id | string | True | 20 |  |  |
| claim_submission_changes | For a given grouping of claim, change_type, and change_subtype, the total number of changes for that grouping. Only appears on most recent record. | int | True |  |  |  |
| claim_submission_change_old_value | Value before change. | string | True | 1000 |  |  |
| claim_submission_change_new_value | Value after change. | string | True | 1000 |  |  |
| change_type | Change type | string | True | 50 | ACCEPT_ASSIGNMENT AUTO_ACCIDENT_RELATED BILLING_PROVIDER BILLING_PROVIDER_SECONDARY_ID CPT DIAGNOSIS_POINTER EMPLOYMENT_ACCIDENT_RELATED MODIFIER OTHER_ACCIDENT_RELATED PATIENT_ADDRESS PAYER_INFORMATION POLICY_HOLDER_ADDRESS PRIOR_AUTHORIZATION_NUMBER REFERRING_PROVIDER REFERRING_PROVIDER_SECONDARY_ID RESUBMISSION_CODE SERVICE_LOCATION |  |
| change_subtype | change subtype | string | True | 10 | added changed removed |  |
| claim_submission_change_submitting_user | Name of staff who submitted change. | string | True | 100 |  |  |
| claim_created_date | Date on which claim was created. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## bill

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_id | bill table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| business_unit_id | business_unit table id | string | True | 20 |  |  |
| financial_category_id | financial_category table id | string | True | 20 | Financial Category |  |
| firm_id | firm table id | string | False | 20 |  |  |
| visit_id | visit table id | string | True | 20 | Visit linked to bill. Field will be empty if a visit was not linked to the bill. |  |
| billing_facility_id | facility table id | string | True | 20 |  |  |
| service_facility_id | facility table id | string | True | 20 | Service location. |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| patient_case_id | patient_case table id | string | True | 20 |  |  |
| appointment_id | appointment table id | string | True | 20 | Appointment linked to bill. Field will be empty if an appointment was not linked to the bill. |  |
| primary_provider_id | staff table id | string | True | 20 |  |  |
| operating_provider_id | staff table id | string | True | 20 |  |  |
| ordering_provider_id | staff table id | string | True | 20 |  |  |
| other_operating_provider_id | staff table id | string | True | 20 |  |  |
| other_rendering_provider_id | staff table id | string | True | 20 |  |  |
| supervising_provider_id | staff table id | string | True | 20 |  |  |
| supervising_referral_contact_id | referral_contact table id. | string | True | 20 |  |  |
| ordering_referral_contact_id | referral_contact table id. | string | True | 20 |  |  |
| referral_contact_id | referral_contact table id. | string | True | 20 |  |  |
| referral_institution_id | referral institution table id. A referral institution can be added to a bill via the referring physician field. | string | True | 20 |  |  |
| referral_staff_id | staff table id. | string | True | 20 |  |  |
| fee_schedule_id | fee_schedule table id. This is the provider fee schedule listed on the bill. | string | True | 20 |  |  |
| primary_biller_id | staff table id | string | True | 20 | Primary biller. |  |
| last_modified_by_staff_id | staff table id | string | True | 20 |  |  |
| bill_created_by_staff_id | staff table id | string | True | 20 |  |  |
| bill_assignee_id | bill_assignee table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| split_from_bill_id | Bill table id. | string | True | 20 |  |  |
| appointment_provider_id | staff table id for appointment provider. | string | True | 20 | Appointment Provider |  |
| billing_quote_id | billing_quote table id | string | True | 20 |  |  |
| billing_quote_created_by_id | staff table id | string | True | 20 |  |  |
| original_bill_id | Bill table id. Indicates if a bill was recreated from a previous bill | string | True | 20 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| appointment_type | Appointment type. Types are confirmed by the practice at the firm admin level. | string | True | 25 |  |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| encounter_count | Stores the associated bill_id. If not null, indicates an encounter has occurred and the sum of units posted or reversed within the bill is greater than zero. | string | True | 20 |  |  |
| financial_category | The Financial Category listed for the payer | string | True | 100 |  |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| billing_quote_title | Title of billing quote | string | True | 100 |  |  |
| billing_quote_id_number | Client-facing billing quote id | string | True | 20 |  |  |
| is_referring_physician_data | Qlik flag if record is part of the referring physician report. | boolean | True |  |  |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| package_sale_date_created_ld | Date on which the package was sold. | timestamp | True |  |  |  |
| firm_is_using_rcm | Whether using rcm is enabled | boolean | True |  |  |  |
| referral_contact_name | referral contact full name. | string | True | 200 |  |  |
| referral_institution_name | referral institution name. | string | True | 100 |  |  |
| referral_staff_name | staff full name. | string | True | 200 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| bill_identifier | Bill identifier. This is the number displayed on the bill. | string | True | 20 |  |  |
| split_from_bill_identifier | Bill identifier of the bill that the current bill was split from | string | True | 20 |  |  |
| clia_number | CLIA number assigned to facility. | string | True | 50 |  |  |
| bill_type | Bill type | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| bill_assignee_type | Indicates if bill is assigned to a group or individual staff member. May have a null value. | string | True | 20 | BILL_ASSIGNEE_GROUP FIRM_GROUP STAFF |  |
| bill_status | Bill status. | string | True | 20 | PRELIMINARY IN_PROGRESS REQUIRES_REVISION READY_FOR_REVIEW IN_REVIEW INACTIVE_OTHER RESOLVED_PAID RESOLVED_OTHER IN_DISPUTE PAYMENT_PENDING READY_FOR_POSTING |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| discharge_status | Patient discharge status | string | True | 50 | HOME_OR_SELF_CARE SHORT_TERM_GENERAL_HOSPITAL SKILLED_NURSING_FACILITY INTERMEDIATE_CARE_FACILITY DESIGNAGTED_CARE_CENTER_OR_CHILDRENS_HOSPITAL HOME_UNDER_CARE_OF_HOME_HEALTH_CARE_ORG LEFT_AGAINST_MEDICAL_ADVICE EXPIRED COURT_OR_LAW_ENFORCEMENT HOSPICE_HOME HOSPICE_MEDICAL_FACILITY INPATIENT_REHABILITATION_FACILITY MEDICARE_CERTIFIED_LONG_TERM_CARE_HOSPITAL MEDICAID_NURSING_FACILITY PSYCHIATRIC_HOSPITAL CRITICAL_ACCESS_HOSPITAL DESIGNATED_DISASTER_ALTERNATE_CARE_SITE OTHER FEDERAL_HEALTH_CARE_FACILITY |  |
| bill_assignee | Name of the Individual staff member assigned to the bill. If staff member does not exist then the bill assignee group name will be listed instead. | string | True | 400 |  |  |
| bill_charge_type | Indicates whether bill is for facility or professional services. | string | True | 20 | FACILITY PROFESSIONAL |  |
| bill_visit_specialty | Specialty selected at the visit for the bill. May have a null value. | string | True | 20 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY RHEUMATOLOGY UROLOGY |  |
| last_assignee | Name of the Individual staff member who was last assigned to the bill. | string | True | 200 |  |  |
| current_assignee | Name of the Individual staff member currently assigned to the bill. | string | True | 200 |  |  |
| average_days_assigned | Average number of days bill has been assigned to a user (calculated field) | double | True |  |  |  |
| days_assigned_to_current_assignee | Number of days bill has been assigned to current assignee (calculated field) | int | True |  |  |  |
| times_reassigned | Times reassigned | int | True |  |  |  |
| total_charges | Service rendered total charges. Unit charge x number of units. | double | True |  |  |  |
| total_payments | Total for payments made on the bill. | double | True |  |  |  |
| applied_adjustments_total | Adjustments total applied on the bill. | double | True |  |  |  |
| total_posted_charges | Total posted charges. Field will be empty until the bill has been posted | double | True |  |  |  |
| external_lab_amount | External lab amount | double | True |  |  |  |
| balance | balance for the bill | double | True |  |  |  |
| billing_location_other_identifier | Billing identifier for the billing location. Other ID (32b) | string | True | 17 |  |  |
| billing_location_other_identifier_qualifier | Billing qualifier for billing location other identifier. | string | True | 20 |  |  |
| date_of_current_illness_qualifier | Billing qualifier for date of current illness. | string | True | 20 |  |  |
| other_claim_identifier | Billing identifier for claim other. | string | True | 28 |  |  |
| other_treatment_date_qualifier | Billing qualifier for treatment date. | string | True | 20 |  |  |
| referring_provider_other_identifier | Billing identifier for referring provider other. | string | True | 17 |  |  |
| referring_provider_other_identifier_qualifier | Billing qualifier for referring provider other identifier. | string | True | 20 |  |  |
| rendering_provider_other_identifier | Billing identifier for rendering provider other. | string | True | 11 |  |  |
| rendering_provider_other_identifier_qualifier | Billing qualifier for rendering provider other identifier. | string | True | 20 |  |  |
| service_location_other_identifier | Billing identifier for service location other. | string | True | 14 |  |  |
| service_location_other_identifier_qualifier | Billing qualifier for service location other identifier. | string | True | 20 |  |  |
| claim_note | Bill claim note. | string | True | 55 |  |  |
| service_location_pos_code | Code position for service locaiton. | string | True | 5 |  |  |
| attachment_transmission_code | Attachment transmission code | string | True | 2 |  |  |
| reportable_reason | Reportable reasons for patient visit. | string | True | 25 | MEDICAL_NON_EMERGENCY MEDICAL_EMERGENCY AUTOMOBILE_ACCIDENT COSMETIC_SERVICES VISION WORKERS_COMP OTHER |  |
| appointment_notes | Appointment notes. | string | True | 3000 |  |  |
| bill_as_new_patient | New patient bill flag. | boolean | True |  |  |  |
| employment_related | Accident or Injury type flag. | boolean | True |  |  |  |
| auto_accident_related | Accident or Injury type flag. | boolean | True |  |  |  |
| other_accident_related | Accident or Injury type flag. | boolean | True |  |  |  |
| auto_accident_related_state | Auto accident related state. | string | True | 2 |  |  |
| external_lab | External lab flag. | boolean | False |  |  |  |
| is_last_visit | Visit is most recent visit for patient. | boolean | True |  |  |  |
| bill_was_split | Indicates if the bill originated from a bill that was split. | boolean | True |  |  |  |
| service_date | Date which service was performed. | timestamp | True |  |  |  |
| follow_up_date | Date specified by practice for billers to follow up for status on claim resolution. Also termed Next Touch Date. This column will be deprecated in release 1.25 and removed in release 1.26. | timestamp | True |  |  | True |
| bill_creation_date | Date which bill was created, either by visit finalization or manual creation by staff. | timestamp | True |  |  |  |
| bill_follow_up_date | Date selected for follow-up. This date is set by the practice staff. This column will be deprecated in release 1.25 and removed in release 1.26. | timestamp | True |  |  | True |
| date_of_current_illness | Date of current illness. | timestamp | True |  |  |  |
| other_treatment_date | Date of other condition or treatment. | timestamp | True |  |  |  |
| last_modified_date | Date which the bill was last modified. | timestamp | True |  |  |  |
| hospitalization_from_date | Hospitalization from date. | timestamp | True |  |  |  |
| hospitalization_to_date | Hospitalization to date. | timestamp | True |  |  |  |
| service_date_ld | Date which service was performed. This column will be deprecated in release 1.25 and removed in release 1.26. | timestamp | True |  |  | True |
| follow_up_date_ld | Date for follow up visit. This column will be deprecated in release 1.25 and removed in release 1.26. | timestamp | True |  |  | True |
| bill_creation_date_ld | Date which bill was created, either by visit finalization or manual creation by staff. | timestamp | True |  |  |  |
| bill_follow_up_date_ld | Date selected for follow-up. This date is set by the practice staff. | timestamp | True |  |  |  |
| date_of_current_illness_ld | Date of current illness. | timestamp | True |  |  |  |
| other_treatment_date_ld | Date of other condition or treatment. | timestamp | True |  |  |  |
| last_modified_date_ld | Date which the bill was last modified. | timestamp | True |  |  |  |
| hospitalization_from_date_ld | Hospitalization from date. | timestamp | True |  |  |  |
| hospitalization_to_date_ld | Hospitalization to date. | timestamp | True |  |  |  |
| finalized_date | Visit Finalization Date. | timestamp | True |  |  |  |
| finalized_date_ld | Localized Visit Finalization Date. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_item

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_item_id | bill_item table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| bill_id | bill table id | string | False | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| wrvu | CMS wRVU (work relative value units) for the associated Bill Item. | double | True |  |  |  |
| quick_code | Reflects the quick code combination configured for the CPT/Modifier combination on the bill. These codes are configured by the practice. | string | True | 50 |  |  |
| identifier | Identifier(s) linked to bill item | string | True | 16 | Identifier for bill item. |  |
| code | Bill item code displayed on the bill. | string | True | 20 |  |  |
| code_description | Bill item code descriptio displayed on the bill. | string | True | 200 |  |  |
| bill_item_allowed | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| position | Position of bill item on the bill | int | True |  |  |  |
| type | Bill item type. May have a null value. | string | True | 20 | CPT INJECTABLE CUSTOM DME ANESTHESIA UNKNOWN INVENTORY |  |
| units | Bill item units | double | True |  |  |  |
| unit_allowable | Bill item unit allowable units | double | True |  |  |  |
| bill_item_fee_schedule_allowable | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| modifiers | Modifier(s) linked to bill item | string | True | 60 | Comma-separated string sorted by modifier position |  |
| first_modifier | First modifier linked to bill item | string | True | 20 |  |  |
| second_modifier | Second modifier linked to bill item | string | True | 20 |  |  |
| third_modifier | Third modifier linked to bill item | string | True | 20 |  |  |
| fourth_modifier | Fourth modifier linked to bill item | string | True | 20 |  |  |
| num_modifiers | Number of modifiers linked to bill item | int | True |  |  |  |
| more_than_four_modifiers | Specifies if there are more than 4 modifiers that are linked to the bill item | boolean | True |  |  |  |
| reversal_state | Indicate whether a bill_item is in a reverse status or not | string | True | 20 | LEGACY LEGACY_REVERSED ACTIVE REVERSED |  |
| supplemental_code | Supplemental code liked to bill item. | string | True | 50 |  |  |
| supplemental_description | Supplemental code description liked to bill item. | string | True | 80 |  |  |
| revenue_code | Revenue code associated to the CPT code. | string | True | 4 |  |  |
| supplemental_qualifier | Supplemental qualifier linked to bill item as listed on 1500 form. | string | True | 20 |  |  |
| supplemental_quantity | Supplemental quantity. | double | True |  |  |  |
| supplemental_quantity_qualifier | Supplemental quantity qualifier linked to bill item. | string | True | 20 |  |  |
| supplemental_qualifier_code | Code for the supplemental qualifier associated with the bill item | string | True | 20 |  |  |
| supplemental_qualifier_description | Description for the supplemental qualifier associated with the bill item | string | True | 20 |  |  |
| unit_of_measure_code | Unit of measure for the supplemental qualifier associated with the bill item | string | True | 20 |  |  |
| unit_of_measure_description | Description of the unit of measure for the supplemental qualifier associated with the bill item | string | True | 20 |  |  |
| patient_responsible_from_copay | Patient copay. | double | True |  |  |  |
| patient_responsible_from_coinsurance | Patient coinsurance. | double | True |  |  |  |
| patient_responsible_from_deductible | Patient deductible. | double | True |  |  |  |
| patient_responsible_from_other | Other. | double | True |  |  |  |
| charge | Total charge on bill item. | double | True |  |  |  |
| unit_charge | Unit charge on bill item. | double | True |  |  |  |
| total_payments | Total payments made on bill item. | double | True |  |  |  |
| applied_adjustments_total | Total adjustments applied to bill item. | double | True |  |  |  |
| balance | Bill item balance. | double | True |  |  |  |
| note | Bill item note. | string | True | 55 |  |  |
| status | Bill item post status. | string | True | 40 |  |  |
| visible | Bill item visible flag. Bill items that have been removed from a bill will have visible flag set to False. | boolean | True |  |  |  |
| service_date_from | Bill item service date from. | timestamp | True |  |  |  |
| service_date_to | Bill item service date to. | timestamp | True |  |  |  |
| service_date_from_ld | Bill item service date from. | timestamp | True |  |  |  |
| service_date_to_ld | Bill item service date to. | timestamp | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pm_note

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pm_note_id | pm_note table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 | Bill note author |  |
| bill_id | bill table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| patient_statement_id | patient_statement table id | string | True | 20 |  |  |
| primary_biller_id | staff table id | string | True | 20 |  |  |
| service_location_id | facility table id | string | True | 20 |  |  |
| bill_note_author | Bill note author name | string | True | 200 |  |  |
| bill_note_author_role | Role | string | True | 50 | DOCTOR, PHYSICIAN_ASSISTANT, MEDICAL_ASSISTANT etc. |  |
| note_text | Free text bill notes | string | True | -1 |  |  |
| type | Type of financial note entered | string | True | 50 | BILL GENERAL PATIENT_STATEMENT TRANSACTION PAYER_PAYMENT PAYMENT_PLAN |  |
| bill_note_bill_identifier | Bill identifier | string | True | 20 |  |  |
| latest_bill_note | Flag indicating this is the latest note for a bill. | boolean | True |  |  |  |
| bill_recreated | Flag indicating if the bill has been recreated. | boolean | True |  |  |  |
| primary_biller_name | Primary biller name | string | True | 200 |  |  |
| service_location | Service location. | string | True | 200 |  |  |
| time_zone | User time zone | string | True | 30 |  |  |
| note_created_date | Date and time when bill note was entered | timestamp | True |  |  |  |
| note_created_date_ld | Date and time when bill note was entered | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_item_modifier

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_item_modifier_id | bill_item_modifier table id | string | False | 20 |  |  |
| bill_item_id | bill_item table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| modifier | Modifier linked to bill item | string | True | 60 |  |  |
| position | Modifier position | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_item_diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_item_diagnosis_id | bill_item_diagnosis table id | string | False | 20 |  |  |
| bill_item_id | bill_item table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| diagnosis_code | ICD 9 or ICD 10 diagnosis code linked to bill item | string | True | 40 |  |  |
| position | Position of ICD 9 or ICD 10 diagnosis code linked to bill item. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_insurance

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_insurance_id | bill_insurance table id | string | False | 20 |  |  |
| bill_id | bill table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| insurance_policy_authorization_id | insurance_policy_authorization table id | string | True | 20 |  |  |
| unlinked_by_staff_id | staff table id | string | True | 20 |  |  |
| inactivated_by_staff_id | staff table id | string | True | 20 |  |  |
| fee_schedule_id | fee_schedule table id. This is the payer fee schedule selected for the bill. | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| authorization_number | Bill insurance authorization number. | string | True | 50 |  |  |
| position | Insurance policy position on the bill. | int | True |  |  |  |
| status | Bill insurance status. | string | True | 50 | PRELIMINARY UNAVAILABLE |  |
| payer_id_type | Type of payer ID. | string | True | 20 | DME INSTITUTIONAL OTHER PROFESSIONAL |  |
| link_state | Stores the current state of the insurance in relation to the bill. | string | True | 20 | LINKED UNLINKED REMOVED LEGACY_REMOVED |  |
| date_inactivated | Date at which Bill Insurance was inactivated. | timestamp | True |  |  |  |
| date_unlinked | Date at which Bill Insurance was unlinked. | timestamp | True |  |  |  |
| signature_on_file | Flag for signature on file. | boolean | True |  |  |  |
| accepts_assignment | Flag for whether the Bill Insurance accepts assignment. | boolean | True |  |  |  |
| visible | Flag for whether the record is visible. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_insurance_timely_filing

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_insurance_timely_filing_id | bill_insurance_timely_filing table id | string | False | 20 |  |  |
| bill_insurance_id | bill_insurance table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| archived | Billing insurance archived flag. | boolean | True |  |  |  |
| timely_filing_date | Timely Filing date. | timestamp | True |  |  |  |
| timely_filing_warning_date | Timely Filing warning date. | timestamp | True |  |  |  |
| timely_filing_date_ld | Timely Filing date. | timestamp | True |  |  |  |
| timely_filing_warning_date_ld | Timely Filing warning date. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## bill_assignee

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| bill_assignee_id | bill_assignee table id | string | False | 20 |  | True |
| firm_id | firm table id | string | True | 20 |  | True |
| staff_id | staff table id | string | True | 20 |  | True |
| type | Bill assignee type. | string | True | 50 | BILL_ASSIGNEE_GROUP FIRM_GROUP STAFF | True |
| group_name | Bill assignee group name. | string | True | 30 |  | True |
| display_group_name | Formatted bill assignee group name. | string | True | 30 |  | True |
| archived | Bill assignee arhived flag. | boolean | True |  |  | True |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  | True |

## financial_assignee

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| financial_assignee_id | financial_assignee table id | string | False | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| type | Financial assignee type. | string | True | 50 | BILL_ASSIGNEE_GROUP FINANCIAL_ASSIGNEE_GROUP FIRM_GROUP STAFF |  |
| group_name | Financial assignee group name. | string | True | 30 |  |  |
| display_group_name | Formatted financial assignee group name. | string | True | 30 |  |  |
| archived | Financial assignee archived flag. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## production_summary

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| production_summary_id | production_summary table id | string | False | 40 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| payer_id | payer table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| provider_id | staff table id for current provider. | string | True | 20 | Billing Provider. |  |
| primary_provider_id | staff table id for primary provider. | string | True | 20 | Primary Provider. |  |
| appointment_provider_id | staff table id for appointment provider. | string | True | 20 | Appointment Provider |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| original_bill_id | Bill table id. Indicates if a bill was recreated from a previous bill | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 |  |  |
| bill_insurance_id | bill_insurance table id | string | True | 20 |  |  |
| sold_by_id | staff table id | string | True | 20 | The staff member selected in the Sold By field. The provider and the Sold by could be the same person depending on selection. |  |
| transaction_initiated_by_id | staff table id. | string | True | 20 | The person who ran the transaction, specifically patient payments, voids, or refund. This may also refer to the user who accepted a pending patient payment via external source. |  |
| payer_address_id | payer_address table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| batch_id | batch table id | string | True | 20 |  |  |
| provider_level_adjustment_id | provider_level_adjustment table id. | string | True | 40 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| billing_quote_id | billing_quote table id | string | True | 20 |  |  |
| billing_quote_created_by_id | staff table id | string | True | 20 |  |  |
| custom_payment_method_id | custom_payment_method table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 | Staff table id |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| package_item_sale_id | package_item_sale table id | string | True | 20 |  |  |
| bill_assignee_id | bill_assignee table id. Id of the staff member assigned to follow up on payments. | string | True | 20 |  |  |
| charges_id | charges table id | string | True | 50 |  |  |
| patient_adjustments_id | patient_adjustments table id | string | True | 50 |  |  |
| payer_adjustments_id | payer_adjustments table id | string | True | 50 |  |  |
| payments_posted_id | payments_posted table id | string | True | 50 |  |  |
| transaction_identifier | Transaction Identifier. This value will be null for PLA transactions. | string | True | 40 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| payer_check_key | Payer check key, used to link different payer payments to payment tables. | string | True | 20 |  |  |
| charge_link_key | Linking key between charges, payments_posted, patient_adjustments, payer_adjustments, product_sales and production_summary tables. | string | True | 100 |  |  |
| ledger_charge_amount | Charge amount per ledger item. | double | True |  |  |  |
| ledger_payment_amount | Payment amount per ledger item. | double | True |  |  |  |
| ledger_adjustment_amount | Adjustment amount per ledger item. | double | True |  |  |  |
| subtotal | Product subtotal. | double | True |  |  |  |
| discount_amount | Product discount amount. | double | True |  |  |  |
| discount_reason | Discount reason from standard_list or pipe separated custom discount reason(s) | string | True | 500 |  |  |
| tax_rate_local | Product local tax rate. | double | True |  |  |  |
| tax_rate_state | Product state tax rate. | double | True |  |  |  |
| tax_amount_local | Product local tax amount. | double | True |  |  |  |
| tax_amount_state | Product state tax amount. | double | True |  |  |  |
| tax_amount | Product total tax amount, state and local combined. | double | True |  |  |  |
| responsible | Responsible party value | string | True | 20 | INSURANCE PATIENT |  |
| ledger_reference | Ledger reference code. | string | True | 100 |  |  |
| payment_method | Method of payment such as cash, check, e-check, credit card, gift card, etc. | string | True | 200 |  |  |
| payment_source | Source of payment | string | True | 40 | PAYER_REFUND ERA PATIENT_PAYMENT PATIENT_PAYMENT_VOID EOB LEGACY_PATIENT_EXTERNAL_TRANSFER LEGACY_PATIENT_EXTERNAL_TRANSFER_VOID LEGACY_PATIENT_PAYMENT LEGACY_PATIENT_PAYMENT_VOID PATIENT_REFUND PATIENT_EXTERNAL_TRANSFER_VOID PATIENT_EXTERNAL_TRANSFER PATIENT_EXTERNAL_TRANSFER_REFUND BUSINESS_UNIT_TRANSFER_RECEIVED BUSINESS_UNIT_TRANSFER_RECEIVE_REFUND BUSINESS_UNIT_TRANSFER_SENT |  |
| payment_code | Payment code associated with payment. | string | True | 20 | AVAILABLE COPAY PAYER_CHECK OMITTED_PAYER_CHECK PAYER_CHECK_CLAIM UNAVAILABLE |  |
| payment_code_description | payment_code meaning. | string | True | 20 | Deposits Copay Payer Check Payer Check Omitted Payer Check Claim General |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| encounter_count | Stores the associated bill_id. If not null, indicates an encounter has occurred and the sum of units posted or reversed within the bill is greater than zero. | string | True | 20 |  |  |
| activity_type | Activity Type. | string | True | 1000 | ADJUSTMENT CHARGE CHARGE_ADJUSTMENT PAYMENT PLA_OFFSET_CHARGE PLA_OFFSET_CHARGE_PAYMENT PLA_POST_TO_SERVICE_LINE PLA_POST_TO_SVC_LINES VOID_ADJUSTMENT VOID_CHARGE VOID_CHARGE_ADJUSTMENT VOID_PAYMENT VOID_PLA_OFFSET_CHARGE VOID_PLA_OFFSET_CHARGE_PAYMENT VOID_PLA_POST_TO_SERVICE_LINE VOID_PLA_POST_TO_SVC_LINES |  |
| appointment_type | If applicable, type of appointment linked to payment transaction | string | True | 25 |  |  |
| ledger_units | Number of units associated to the charge. | double | True |  |  |  |
| bill_item_adjustment_reason_code | Reason code. Payer or patient reason code or code manually entered by the staff.. | string | True | 45 |  |  |
| adjustment_reason | Adjustment reason description. | string | True | 1000 |  |  |
| bill_item_adjustment_carc | CARC. | string | True | 10 |  |  |
| bill_item_adjustment_status | Payer adjustment status. | string | True | 20 | ON_HOLD TRANSFER_RESPONSIBILITY WRITE_OFF IGNORE |  |
| coverage_type | Coverage type. | string | True | 20 | Primary Secondary Tertiary Self-Pay |  |
| link_state | Stores the current state of the insurance in relation to the bill | string | True | 20 | LINKED UNLINKED REMOVED LEGACY_REMOVED |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| bill_type | Bill type. | string | True | 20 | PATIENT CLAIM VISION AUTO_PIP WORKERS_COMP |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| responsible_insurance_policy_number | Insurance policy number. | string | True | 100 |  |  |
| policy_type | Insurance policy type. May have a null value. | string | True | 100 | EPO GHP HMO IPA MEDICARE_ADVANTAGE PPO POS COMMERCIAL_OTHER ACA_EXCHANGE CHAMPVA CHIP FECA MEDICARE MEDICAID TRICARE GOVERNMENT_OTHER VISION WORKERS_COMP AUTO_PIP B C Champus Choice Plus Exclusive Provider Organization (EPO) M O |  |
| policy_group_number | Insurance policy group number. | string | True | 100 |  |  |
| patient_relationship_to_policy_holder | Patient relationship to insurance policy holder. May have a null value. | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| policy_patient_name | Name of the policy holder listed for insurance. | string | True | 250 |  |  |
| policy_holder_gender | Policy holder Gender. May have a null value. | string | True | 20 | MALE, FEMALE, etc. |  |
| policy_holder_date_of_birth | Policy Holder Date Of Birth | timestamp | True |  |  |  |
| payer_plan_name | Payer's plan name. | string | True | 100 |  |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or the inventory product description. | string | True | 500 |  |  |
| cpt_frequency_unit | The number of times a service has been rendered. This value will be negative for voids. | int | True |  |  |  |
| product_category | Product category name | string | True | 100 |  |  |
| product_sku | Product sku | string | True | 100 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| batch_name | Batch name. | string | True | 100 |  |  |
| service_location_pos_code | Place of service code listed on the bill. | string | True | 5 |  |  |
| claim_employer_name | If applicable, this reflects the employer's name listed for the insurance policy. | string | True | 100 |  |  |
| financial_category | Financial category associated to payer or patient. | string | True | 100 |  |  |
| quick_code | Reflects the quick code combination configured for the CPT/Modifier combination on the bill. These codes are configured by the practice. | string | True | 50 |  |  |
| authorization_number | Authorization number linked to insurance policy. | string | True | 50 |  |  |
| pla_reason | Provider level adjustment reason | string | True | 100 |  |  |
| bill_item_allowed | Payer Payment Allowable Amount for the associated Bill Item. | double | True |  |  |  |
| wrvu | CMS wRVU (work relative value units) for the associated Bill Item. | double | True |  |  |  |
| billing_quote_title | Title of billing quote | string | True | 100 |  |  |
| billing_quote_id_number | Client-facing billing quote id | string | True | 20 |  |  |
| source_of_payment_typology | Source of Payment Typology | string | True | 100 |  |  |
| payment_link | URL that links back to the payment transaction modal | string | True | 100 |  |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| payment_channel | The channel used for patient payments | string | True | 30 | STAFF TEXT_TO_PAY AUTOMATIC_PROCESSING KIOSK POCKET_PATIENT_ANDROID TERMINAL POCKET_PATIENT_IOS PATIENT_PORTAL QUICK_PAY PAYMENT_PLAN EXTERNAL_API ONLINE_CHECK_IN |  |
| payer_check_notes | Notes from the payer check. | string | True | 255 |  |  |
| signature_on_file | If true, a practice can receive payment from an insurer on behalf of a patient. | boolean | True |  | True: Yes, False: No |  |
| package_name | Package name. | string | True | 50 |  |  |
| bill_assignee_staff_name | Name of the staff member that is assigned to follow up on payments. | string | True | 200 |  |  |
| claim_insurance_key | A concatenation of bill item and billing insurance id which is linked to the claims which are sent out. | string | True | 20 |  |  |
| notes | Notes. | string | True | 500 |  |  |
| firm_is_using_rcm | Whether using rcm is enabled | boolean | True |  |  |  |
| service_date_from | Date which service started. Note: This column will be deprecated on our next release, please use service_date_from_ld column. | timestamp | True |  |  | True |
| rcm_transaction_responsible | Transaction responsibility flag for RCM | string | True | 25 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| adjudication_date_ld | The date when a payer approved payment for a claim. This field is automatically populated for ERAs but must be manually entered for EOBs. | timestamp | True |  |  |  |
| ledger_posted_date_ld | Posted Date of the financial transaction. | date | True |  |  |  |
| ledger_activity_date | Activity date of the financial transaction. | timestamp | True |  |  |  |
| service_date_from_ld | Date which service started | timestamp | True |  |  |  |
| service_date_to_ld | Date which service ended. | timestamp | True |  |  |  |
| ledger_activity_date_ld | Activity date of the financial transaction. | timestamp | True |  |  |  |
| deposit_date_ld | Deposit date of payment. | timestamp | True |  |  |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| package_sale_date_created_ld | Date on which the package was sold. | timestamp | True |  |  |  |
| follow_up_date | Date at which Financial Assignee will follow up on the Payer Payment. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## accounts_receivable

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| accounts_receivable_id | accounts_receivable table id | string | False | 70 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| primary_provider_id | staff table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| practice_location_id | facility table id | string | True | 20 | Practice Location (POS 11) |  |
| payer_id | payer table id | string | True | 20 |  |  |
| bill_id | bill table id | string | True | 20 |  |  |
| original_bill_id | Bill table id. If bill was recreated. This will be the original bill that the new bill was generated from. | string | True | 20 |  |  |
| bill_item_id | bill_item table id | string | True | 20 |  |  |
| patient_business_unit_id | patient_business_unit_setting table id | string | True | 30 |  |  |
| last_billing_note_id | pm_note table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| fee_schedule_primary_payer_id | Fee schedule of the primary insurance. This is the payer fee schedule of the primary insurance from the bill insurance. | string | True | 20 |  |  |
| referral_contact_id | referral_contact table id. | string | True | 25 |  |  |
| referral_institution_id | referral_institution table id. | string | True | 20 |  |  |
| referral_staff_id | staff table id. | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| referral_contact_name | referral contact full name. | string | True | 200 |  |  |
| referral_institution_name | referral institution name. | string | True | 100 |  |  |
| referral_staff_name | staff full name. | string | True | 200 |  |  |
| guarantor_name | Guarantor's full name | string | True | 220 |  |  |
| guarantor_mobile_number | Guarantor's mobile phone number | string | True | 25 |  |  |
| patient_relationship_to_guarantor | Patient's Relationship to Guarantor | string | True | 50 | SELF SPOUSE CHILD OTHER EMPLOYER |  |
| guarantor_date_of_birth | Guarantor's date of birth | timestamp | True |  |  |  |
| guarantor_address_line_1 | Guarantor's address street | string | True | 255 |  |  |
| guarantor_address_line_2 | Guarantor's address street line 2 | string | True | 255 |  |  |
| guarantor_city | Guarantor's address city | string | True | 255 |  |  |
| guarantor_state | Guarantor's address state | string | True | 50 |  |  |
| guarantor_zipcode | Guarantor's address Zipcode | string | True | 50 |  |  |
| allowable_balance | Calculated based on unit allowed per line item. If patient responsible then this is the patient balance. | double | True |  |  |  |
| balance | Total balance for the responsible party. | double | True |  |  |  |
| responsible | Responsible party. | string | True | 20 | PATIENT INSURANCE |  |
| authorization_number | Authorization number linked to insurance policy | string | True | 50 |  |  |
| responsible_insurance_policy_number | Responsible payer policy number. This will be null for patient responsible balances. | string | True | 25 |  |  |
| policy_group_number | Responsible payer policy group number. | string | True | 100 |  |  |
| patient_phone_number | Patient phone number | string | True | 25 |  |  |
| coverage_type | Type of coverage | string | True | 20 | Primary Secondary Tertiary Self-Pay |  |
| link_state | Stores the current state of the insurance in relation to the bill | string | True | 20 | LINKED UNLINKED REMOVED LEGACY_REMOVED |  |
| signature_on_file | If true, a practice can receive payment from an insurer on behalf of a patient. | boolean | True |  | True: Yes, False: No |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or inventory product description. | string | True | 500 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| bill_type | Bill type. For non-bill charges this field will be empty. | string | True | 20 | AUTO_PIP CLAIM PATIENT VISION WORKERS_COMP |  |
| bill_recreated | Indicates if a bill was recreated from a previous bill | boolean | True |  |  |  |
| bill_balance | Balance on bill | double | True |  |  |  |
| bill_balance_type | Indicates the type of balance remaining on a bill | string | True | 20 | Debit Credit |  |
| charge_status | Charge Status. | string | True | 20 | CHARGED CANCELED |  |
| financial_category | The Financial Category listed for the responsible party. | string | True | 100 |  |  |
| fee_schedule_primary_payer_name | Fee schedule name. This is the payer fee schedule from the primary bill insurance. | string | True | 50 |  |  |
| fee_schedule_type | Fee Schedule type. | string | True | 10 | PAYER PROVIDER |  |
| fee_schedule_primary_payer_effective_date | Effective date. The payer fee schedule effective date. | date | True |  |  |  |
| patient_statement_status | Patient statement status. | string | True | 20 | Sending On Hold |  |
| auto_pay_bill_status | Captures the status of a patient's AutoPay feature for billing | string | True | 300 | NOTIFIED SCRUB_FAILED QUEUED DECLINED ON_HOLD CANCELLED COMPLETED PENDING |  |
| cpt | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge. | string | True | 100 |  |  |
| modifiers | Modifiers associated with bill item. | string | True | 100 |  |  |
| billed_status | Flag that indicates whether claim has been submitted to responsible party. If claim has not been submitted, then status will be set to No. This flag can be used to identify balances that have not been submitted. | string | True | 10 | No Yes |  |
| time_zone | Facility time zone. | string | True | 30 |  |  |
| charge_sent_statement_count | The number of times a balance has been sent for the statement related to the charge. Note: Aggregating this column will result in duplicates. | int | True |  |  |  |
| last_payment_amount | The patient's last payment amount. | double | True |  |  |  |
| billed_days_date | The number of days since first submission claim to present. | timestamp | True |  |  |  |
| service_date_from | Service date. Note: This column is already localized to the client location. There is no time component. | date | True |  |  |  |
| service_date_to | Date which service ended. Note: This column is already localized to the client location. There is no time component. | date | True |  |  |  |
| posted_date | Posted date of charge. | timestamp | True |  |  |  |
| last_payment_date | Date of last payment. | timestamp | True |  |  |  |
| timely_filing_date | Date configured for timely filing per payer. | timestamp | True |  |  |  |
| charge_last_statement_date | Last charge statement date. | timestamp | True |  |  |  |
| billed_days_date_ld | The number of days since first submission claim to present. | timestamp | True |  |  |  |
| service_date_from_ld | Service date. Note: This column is already localized to the client location. There is no time component. | date | True |  |  |  |
| service_date_to_ld | Date which service ended. Note: This column is already localized to the client location. There is no time component. | date | True |  |  |  |
| posted_date_ld | Posted date of charge. | timestamp | True |  |  |  |
| last_payment_date_ld | Date of last payment | timestamp | True |  |  |  |
| timely_filing_date_ld | Date configured for timely filing per payer | timestamp | True |  |  |  |
| charge_last_statement_date_ld | Last charge statement date. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## code_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| code_category_id | code_category table id. | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| code_category | Code category name. | string | True | 80 |  |  |
| status | Whether category enabling status is active | string | True | 10 | ACTIVE INACTIVE |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## code_category_item

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| code_category_item_id | code_category_item table id. | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| code_category_id | code_category table id | string | True | 20 |  |  |
| revenue_code | Revenue code | string | True | 5 |  |  |
| code | Category code assigned | string | True | 100 |  |  |
| quick_key | Quick Key used for CPT and HCPCS Codes | string | True | 9 |  |  |
| quick_code | Code and modifier combination utilized for creation of distinct quick code by the user | string | True | 80 |  |  |
| modifiers | Modifiers linked to a code category | string | True | 12 | Comma-separated string sorted by modifier position |  |
| modifier_1 | First Modifier item linked to a code category | string | True | 2 |  |  |
| modifier_2 | Second Modifier item linked to a code category | string | True | 2 |  |  |
| modifier_3 | Third Modifier item linked to a code category | string | True | 2 |  |  |
| modifier_4 | Fourth Modifier item linked to a code category | string | True | 2 |  |  |
| composite_key | Concatenation of firm_id, type, code, modifier_1, modifier_2, modifier_3, modifier_4 and quick_key in the format: F~firm_id~abbreviated_type~C~code~M1~modifier_1~M2~modifier_2~M3~modifier_3~M4~modifier_4~QK~quick_key. | string | True | 80 | F - firm abbreviated type includes abbreviation for values associated with type. CPT_OR_HCPCS - COH, CUSTOM_CODE - CC, PRODUCT_CODE - PC, PRODUCT_AND_NON_BILL_CHARGES_CODE - PANBCC C - code M - modifier_n where n is either 1, 2, 3 or 4 QK - quick_key |  |
| type | Type of code associated with code category item. | string | True | 40 | CPT_OR_HCPCS CUSTOM_CODE PRODUCT_CODE PRODUCT_AND_NON_BILL_CHARGES_CODE |  |
| ama_description | AMA description for code | string | True | 200 |  |  |
| description | Custom description for code | string | True | 200 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## code_category_patient_payment_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| code_category_patient_payment_log_id | code_category_patient_payment_log table id. | string | False | 20 |  |  |
| patient_id | patient table id. | string | False | 20 |  |  |
| current_code_category_id | code_category table id for current value. | string | True | 20 |  |  |
| previous_code_category_id | Previous code_category table id. | string | True | 20 |  |  |
| transfer_sender_patient_id | patient table id for patient transfer payment types. | string | True | 20 |  |  |
| business_unit_id | business_unit table id. | string | True | 20 |  |  |
| provider_id | staff table id for current provider. | string | True | 20 |  |  |
| reference_number | Reference number for payment transaction (system generated). | string | True | 75 |  |  |
| original_reference_number | Original transaction reference number from which the amount has been transferred (system generated). | string | True | 75 |  |  |
| payment_amount | Amount which is added or transferred among different code categories under deposit. | double | True |  |  |  |
| total_transaction_amount | Total transaction amount collected under the payment. | double | True |  |  |  |
| deposits_amount | Original amount under deposits. | double | True |  |  |  |
| previous_category_before_amount | Previous category before amount. | double | True |  |  |  |
| previous_category_after_amount | Previous category after amount. | double | True |  |  |  |
| current_category_before_amount | Current category before amount. | double | True |  |  |  |
| current_category_after_amount | current category after amount. | double | True |  |  |  |
| history_type | Payment history type. | string | True | 50 | ADD EDIT REMOVE REASSIGN REFUND PATIENT_TRANSFER BUSINESS_UNIT_TRANSFER VOID_PATIENT_TRANSFER |  |
| transaction_type | transaction types. | string | True | 50 | PATIENT_PAYMENT PATIENT_PAYMENT_VOID PATIENT_PAYMENT_VOID_ERROR PATIENT_PAYMENT_DECLINED PATIENT_PAYMENT_ERROR PATIENT_PAYMENT_REFUND PATIENT_PAYMENT_REFUND_ERROR PATIENT_PAYMENT_REFUND_DECLINED PATIENT_PAYMENT_REFUND_VOID P2P_TRANSFER_RECEIVED P2P_TRANSFER_RECEIVED_REFUND P2P_TRANSFER_RECEIVED_VOID PATIENT_EXTERNAL_TRANSFER PATIENT_EXTERNAL_TRANSFER_REFUND PATIENT_EXTERNAL_TRANSFER_VOID PATIENT_ALLOCATION PATIENT_ALLOCATION_VOID BUSINESS_UNIT_TRANSFER_SENT BUSINESS_UNIT_TRANSFER_RECEIVED BUSINESS_UNIT_TRANSFER_RECEIVED_REFUND PENDING |  |
| original_transaction_type | transaction types. | string | True | 50 | PATIENT_PAYMENT PATIENT_PAYMENT_VOID PATIENT_PAYMENT_VOID_ERROR PATIENT_PAYMENT_DECLINED PATIENT_PAYMENT_ERROR PATIENT_PAYMENT_REFUND PATIENT_PAYMENT_REFUND_ERROR PATIENT_PAYMENT_REFUND_DECLINED PATIENT_PAYMENT_REFUND_VOID P2P_TRANSFER_RECEIVED P2P_TRANSFER_RECEIVED_REFUND P2P_TRANSFER_RECEIVED_VOID PATIENT_EXTERNAL_TRANSFER PATIENT_EXTERNAL_TRANSFER_REFUND PATIENT_EXTERNAL_TRANSFER_VOID PATIENT_ALLOCATION PATIENT_ALLOCATION_VOID BUSINESS_UNIT_TRANSFER_SENT BUSINESS_UNIT_TRANSFER_RECEIVED BUSINESS_UNIT_TRANSFER_RECEIVED_REFUND PENDING |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## batch

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| batch_id | batch table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| staff_id | Staff table id assigned to the batch. | string | False | 20 |  |  |
| created_by_staff_id | Staff table id which created the batch. | string | False | 20 |  |  |
| batch_name | Batch name. | string | True | 100 |  |  |
| total_payments | Total payments associated with the batch. | double | True |  |  |  |
| total_charges | Total charges associated with the batch. | double | True |  |  |  |
| total_refunds | Total refunds associated with the batch. | double | True |  |  |  |
| locked | Batch status lock flag. | boolean | True |  |  |  |
| charges_enabled | Charges enabled flag. | boolean | True |  |  |  |
| payments_and_refunds_enabled | Payments and refunds enabled flag. | boolean | True |  |  |  |
| note | Batch note. | string | True | 300 |  |  |
| visible | Batch archival flag. | boolean | True |  |  |  |
| deposit_date_ld | Date to be utilized as the deposit date for Payments Received; Refunds and the posting date for Charges. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## batch_payment_refund_amount

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| batch_payment_refund_amount_id | batch_payment_refund_amount table id | string | False | 20 |  |  |
| batch_id | batch table id. | string | True | 20 |  |  |
| payment_type | Payment type. | string | True | 60 |  |  |
| total | Lockbox amount to be compared to the sum of payments linked to a batch for a specified payment type. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## billing_quote

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| billing_quote_id | billing_quote table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| created_by_id | Staff table id | string | False | 20 |  |  |
| payer_fee_schedule_id | fee_schedule table id for Payer | string | True | 20 |  |  |
| provider_fee_schedule_id | fee_schedule table id for Provider | string | True | 20 |  |  |
| quote_identifier | Quote identifier. This is the number displayed on the quote. | string | True | 20 |  |  |
| quote_title | Title of quote | string | True | 100 |  |  |
| responsible | Responsible party. | string | True | 20 | PATIENT INSURANCE |  |
| status | Status of quote | string | True | 40 |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## billing_quote_verbiage

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| billing_quote_verbiage_id | billing_quote_verbiage table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| quote_name | Title of quote verbiage | string | True | 30 |  |  |
| verbiage | Full quote text | string | True | 5000 |  |  |
| status | Active status of quote verbiage | boolean | True |  |  |  |
| always_included | Allow user to remove verbiage from quote | boolean | True |  |  |  |
| is_removable | User is able to add additional quotes not already selected under Include Quote Verbiage or currently selected in Additional Quote Verbiage | boolean | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## billing_quote_verbiage_link

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| billing_quote_verbiage_link_id | billing_quote_verbiage_link table id | string | False | 20 |  |  |
| billing_quote_id | billing_quote table id | string | False | 20 |  |  |
| billing_quote_verbiage_id | billing_quote_verbiage table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## billing_quote_charge

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| billing_quote_charge_id | billing_quote_charge table id | string | False | 20 |  |  |
| billing_quote_id | billing_quote table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| custom_code_id | custom_code table id | string | True | 20 |  |  |
| code_category_item_id | code_category table id | string | True | 20 |  |  |
| product_id | Product table id | string | True | 20 |  |  |
| billing_quote_charge_discount_id | billing_quote_charge_discount table id. | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| charge_type | Type of code associated with charge | string | True | 30 | CPT CUSTOM_CHARGE PRODUCT ADDITIONAL_FEE INVENTORY CUSTOM_CODE |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or inventory product description. | string | True | 500 |  |  |
| unit_charge | Charge per unit for services rendered | double | True |  |  |  |
| units | Units | double | True |  |  |  |
| position | Position in the bill (order of code in list of codes). | int | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| date_modified | Date modified (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## billing_quote_charge_discount

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| billing_quote_charge_discount_id | billing_quote_charge_discount table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| discount_type | Type of discount associated with charge | string | True | 15 | AMOUNT PERCENT |  |
| amount | Discount amount. | double | True |  |  |  |
| discount_name | Discount Name | string | True | 100 |  |  |
| status | Active status of discount type | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## custom_patient_adjustment_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_patient_adjustment_code_id | custom_patient_adjustment_code table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| adjustment_code | Adjustment code. | string | True | 25 |  |  |
| description | Adjustment code description. | string | True | 50 |  |  |
| code_type | Adjustment code type. | string | True | 10 |  |  |
| status | Adjustment code status. | string | True | 15 | ALWAYS_ACTIVE ACTIVE INACTIVE |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## custom_payment_method

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_payment_method_id | custom_payment_method table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| name | Custom payment name. | string | True | 30 |  |  |
| description | Payment code description. | string | True | 50 |  |  |
| status | Payment code status. | string | True | 15 | ALWAYS_ACTIVE ACTIVE INACTIVE |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## custom_non_bill_code

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_non_bill_code_id | custom_non_bill_code table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| code_name | Product or charge code name. | string | True | 255 |  |  |
| description | Description for the custom product or charge. | string | True | 70 |  |  |
| amount | Amount associated with the custom product or charge code. | double | True |  |  |  |
| taxable | If the charge or product is taxable. | boolean | True |  |  |  |
| status | Code Status. | boolean | True |  |  |  |
| type | Type of custom code. | string | True | 10 | PRODUCTS CHARGES |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## custom_non_bill_code_facility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_non_bill_code_facility_id | custom_non_bill_code_facility table id | string | False | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_missing_charges

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_missing_charges_id | appointment_missing_charges table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| facility_id | facility table id | string | False | 20 | Service location |  |
| payer_id | payer table id | string | True | 20 | Payer that is selected for the payer payment |  |
| primary_provider_id | staff table id | string | False | 20 | Primary Provider. This is the staff member who the patient is scheduled to visit. |  |
| appointment_time | Appointment time | string | True | 10 | hh:mm a |  |
| appointment_type | Appointment type. Types are confirmed by the practice at the firm admin level. | string | True | 25 |  |  |
| financial_category | financial category name | string | True | 255 |  |  |
| appt_status | Appointment status | string | True | 40 | PENDING CONFIRMED ARRIVED CHECKED_IN CHECKED_OUT NO_SHOW CANCELLED |  |
| visit_status | Status of the visit | string | True | 50 | CHARGES_SENT CODED FINAL FINALIZING HELD_FOR_BILLING HELD_FOR_RESULTS HELD_FOR_TRANSCRIPTION PRELIMINARY RECORDING_IN_PROGRESS TRANSCRIPTION_FAILED TRANSCRIPTION_READY |  |
| bill_with_same_appointment_dos_exists | Indicates if there is a bill where the bill's date of service is the same as the appointment's date of service, regardless of facility | boolean | True |  |  |  |
| bill_with_same_appointment_dos_and_facility_exists | Indicates if there is a bill where the bill's date of service and facility are the same as the appointment's date of service and facility | boolean | True |  |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| scheduled_start_date | Appointment date | timestamp | True |  |  |  |
| scheduled_start_date_ld | Appointment date | timestamp | True |  |  |  |
| do_not_require_visit_creation | Indicates if a provider can address a patient's needs or provide a service without needing to schedule a formal, billed visit. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## refunds

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| refunds_id | refunds table id | string | False | 50 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| payer_id | payer table id | string | True | 20 | The payer associated to the refund |  |
| facility_id | facility table id | string | False | 20 | Service location |  |
| provider_id | staff table id | string | True | 20 | Staff member that performs the refund |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 | Staff who transacted the payment |  |
| code_category_id | code_category table id. | string | True | 20 |  |  |
| batch_id | batch table id | string | True | 20 |  |  |
| custom_payment_method_id | custom_payment_method table id | string | True | 20 |  |  |
| package_sale_id | package_sale table id | string | True | 20 |  |  |
| transaction_settlement_link_key | External UUID that identifies a Transaction (PAYFAC Session), shared between EMA and PAYFAC. | string | True | 50 |  |  |
| refund_link_key | Linking key between refunds and payments_received. | string | True | 75 |  |  |
| payment_link_key | Payment table(s) linking key. | string | True | 75 |  |  |
| original_payment_link_key | Linking key that ties transaction to original payment. This column will have a null value unless the transaction is a refund. | string | True | 100 |  |  |
| payer_check_key | Payer check key, used to link different payer payments to payment tables. | string | True | 20 |  |  |
| reference_number | Payment reference number. In PM this number may also be referred to as the check/trace number or the Transaction number | string | True | 60 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| batch_name | Batch name. | string | True | 100 |  |  |
| package_name | Package name. | string | True | 50 |  |  |
| payment_code | Payment code | string | True | 11 | UNAVAILABLE COPAY AVAILABLE |  |
| payment_source | Source of payment | string | True | 40 | PAYER_REFUND ERA PATIENT_PAYMENT PATIENT_PAYMENT_VOID EOB LEGACY_PATIENT_EXTERNAL_TRANSFER LEGACY_PATIENT_EXTERNAL_TRANSFER_VOID LEGACY_PATIENT_PAYMENT LEGACY_PATIENT_PAYMENT_VOID PATIENT_REFUND PATIENT_EXTERNAL_TRANSFER_VOID PATIENT_EXTERNAL_TRANSFER PATIENT_EXTERNAL_TRANSFER_REFUND BUSINESS_UNIT_TRANSFER_RECEIVED BUSINESS_UNIT_TRANSFER_RECEIVE_REFUND BUSINESS_UNIT_TRANSFER_SENT |  |
| payment_channel | The channel used for patient payments | string | True | 30 | STAFF TEXT_TO_PAY AUTOMATIC_PROCESSING KIOSK POCKET_PATIENT_ANDROID TERMINAL POCKET_PATIENT_IOS PATIENT_PORTAL QUICK_PAY PAYMENT_PLAN EXTERNAL_API ONLINE_CHECK_IN |  |
| payment_processor | Method by which payment was processed | string | True | 50 | EXTERNAL_TRANSFER MODMED PATIENT_CREDIT INSTAMED PATIENT_TRANSFER MANUAL BUSINESS_UNIT_TRANSFER PAYFAC NONE PAYJUNCTION MMPAY |  |
| payment_link | URL that links back to the payment transaction modal | string | True | 100 |  |  |
| payment_appointment_type | If applicable, type of appointment linked to payment transaction | string | True | 25 |  |  |
| patient_payment_status | Status of patient payment. If payer payment, this column will be null. | string | True | 25 | UNPOSTED: None of the payment has been posted to a charge. PARTIALLY_POSTED: Some of the payment has been posted to a charge. POSTED: All of the payment has been posted to a charge. UNKONWN: The payment was made prior to 2019 and the associated funds bucket (unallocated fund) has not been depleted. Prior to 2019, all payments were assigned to the same funds bucket, and it was therefore not possible to determine which dollars came from which payment. |  |
| payment_method | Method of payment such as cash, check, e-check, credit card, gift card, etc. | string | True | 60 |  |  |
| check_number | Check number associated with payment | string | True | 50 |  |  |
| credit_card_type | Type of credit card used for payments with payment method of credit card | string | True | 20 |  |  |
| credit_card_last_four_digits | Last four digits of the credit card used for payments with payment method of credit card | string | True | 20 |  |  |
| patient_auto_pay_status | Status of Patient's Auto Pay | string | True | 20 | ACTIVE CANCELLED DEACTIVATED DECLINED PENDING |  |
| notes | Notes entered for payment transaction | string | True | -1 |  |  |
| financial_category | The Financial Category listed for the responsible party. | string | True | 100 |  |  |
| ledger_refund_address | For refund method check-paper, this is the refund address. | string | True | 1000 |  |  |
| ledger_refund_city | For refund method check-paper, this is the refund city. | string | True | 255 |  |  |
| ledger_refund_state | For refund method check-paper, this is the refund state. | string | True | 50 |  |  |
| ledger_refund_zipcode | For refund method check-paper, this is the refund zipcode. | string | True | 50 |  |  |
| ledger_refund_reference | Transaction Identifier. This corresponds to the Transaction/Reference ID displayed in the user interface. | string | True | 75 |  |  |
| ledger_refund_amount | Refund amount | double | True |  |  |  |
| ledger_refund_notes | Refund notes documented by staff. | string | True | -1 |  |  |
| ledger_refund_date_created | Refund transaction date | timestamp | True |  |  |  |
| ledger_refund_date_created_ld | Localized refund transaction date | timestamp | True |  |  |  |
| ledger_activity_date | Activity date of the financial transaction | timestamp | True |  |  |  |
| ledger_activity_date_ld | Activity date of the financial transaction | timestamp | True |  |  |  |
| refund_method | Refund method. | string | True | 50 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| deposit_date_ld | Deposit date of payment | timestamp | True |  |  |  |
| adjudication_date_ld | The date when a payer approved payment for a claim. This field is automatically populated for ERAs but must be manually entered for EOBs. | timestamp | True |  |  |  |
| transaction_date | Transaction date (system date) | timestamp | True |  |  |  |
| transaction_date_ld | Transaction date (system date) | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## patient_collections_setting

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_collections_setting_id | patient_collections_setting table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| default_staff_assignee_id | staff table id | string | True | 20 |  |  |
| firm_group_assignee_id | firm_group table id | string | True | 20 |  |  |
| unique_custom_patient_adjustment_code_id | custom_patient_adjustment_code table id | string | True | 20 |  |  |
| default_custom_patient_adjustment_code_id | custom_patient_adjustment_code table id | string | True | 20 |  |  |
| appointment_booking_option | When user attempts to book an appointment for a patient in pre-collections. | string | True | 30 | ALLOW WARN DO_NOT_ALLOW |  |
| uncollected_appointment_booking_option | When the user attempts to book an appointment for a patient with an Uncollected status. | string | True | 30 | ALLOW WARN DO_NOT_ALLOW |  |
| pre_collection_ar_days | A/R Days for Pre-Collection. | int | True |  |  |  |
| minimum_patient_overdue_balance | Minimum Patient Overdue Balance. | double | True |  |  |  |
| default_bill_assignee_group_name | Populated when a staff group is chosen from the default assignee field. | string | True | 30 |  |  |
| collection_feature_enabled | Patient Pre-Collection Feature enabled flag. | boolean | True |  |  |  |
| bulk_adjustment_enabled | Bulk Adjustment Feature enabled flag. | boolean | True |  |  |  |
| bulk_adjustment_all_users_enabled | Groups/Users allowed to Bulk Adjust Balances. All users enabled flag. | boolean | True |  |  |  |
| bulk_adjustment_unique_code_enabled | Adjustment Code will default when performing a bulk adjustment. Unique option cannot be overridden. Unique adjustment enabled flag. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## patient_collections_access_restriction

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_collections_access_restriction_id | patient_collections_access_restriction table id | string | False | 20 |  |  |
| patient_collections_setting_id | patient_collections_setting table id | string | False | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| firm_group_id | firm_group table id | string | True | 20 |  |  |
| restriction_type | User or group feature and restriction type. | string | True | 35 | UNCOLLECTED_EXCLUDED BULK_ADJUSTMENT_STAFF_INCLUDED PRE_COLLECTION_EXCLUDED BULK_ADJUSTMENT_FIRM_GROUP_EXCLUDED BULK_ADJUSTMENT_FIRM_GROUP_INCLUDED BULK_ADJUSTMENT_STAFF_EXCLUDED |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pre_collections

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pre_collections_id | pre_collections table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| next_appointment_id | appointment table id | string | True | 20 |  |  |
| most_recent_facility_id | facility table id | string | True | 20 |  |  |
| most_recent_primary_provider_id | staff table id | string | True | 20 |  |  |
| most_recent_primary_biller_id | staff table id | string | True | 20 |  |  |
| current_status | Current status of pre-collection task | string | True |  | First Attempt New Payment Plan Second Attempt Uncollected |  |
| overdue | If due date is less than current date | boolean | True |  |  |  |
| patient_outstanding_balance | Patient total balance | decimal(38,2) | True |  |  |  |
| overdue_balance | Patient overdue balance | decimal(38,2) | True |  |  |  |
| patient_unallocated | Patient unallocated balance | decimal(38,2) | True |  |  |  |
| insurance_balance | Insurance balance | decimal(38,2) | True |  |  |  |
| last_payment_amount | Last payment amount | decimal(38,2) | True |  |  |  |
| most_recent_letter_title | Most recent letter title | string | True | 100 |  |  |
| assigned_to | Task assigned to | string | True | 100 |  |  |
| patient_statement_preference | Patient's preference for statements | string | True |  | ON OFF HOLD |  |
| cpt_codes | Concatenation of most recent CPTs associated with a pre_collection task. Codes separated by pipe \| | string | True | -1 |  |  |
| cpt_codes_descriptions | Concatenation of most recent CPT descriptions associated with a pre_collection task. Descriptions separated by pipe \| | string | True | -1 |  |  |
| most_recent_pre_collection_note | Patient's most recent pre_collection note | string | True | -1 |  |  |
| next_appointment_date | Patient's next appointment date | timestamp | True |  |  |  |
| next_appointment_date_ld | (Localized date) Patient's next appointment date | timestamp | True |  |  |  |
| last_payment_date | Last date of payment | timestamp | True |  |  |  |
| last_payment_date_ld | (Localized date) Last date of payment | timestamp | True |  |  |  |
| most_recent_letter_generated_date | Most recent date a letter was generated | timestamp | True |  |  |  |
| last_statement_date | Last statement date | timestamp | True |  |  |  |
| status_date | Date or pre-collection task status | timestamp | True |  |  |  |
| date_due | Date pre-collection task is due | timestamp | True |  |  |  |
| most_recent_pre_collection_note_date | Patient's most recent pre_collection note's date. | timestamp | True |  |  |  |
| most_recent_service_date_ld | (Localized date) Patient's most recent date of service | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pre_collections_charge_detail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pre_collections_charge_detail_id | pre_collections_charge_detail table id | string | False | 30 |  |  |
| pre_collections_id | pre_collections table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | True | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| charge_amount | Charge amount | decimal(38,2) | True |  |  |  |
| bill_type | bill type | string | True |  |  |  |
| cpt_product | cpt code associated with a charge | string | True | 100 |  |  |
| cpt_product_description | cpt code description associated with a charge | string | True | -1 |  |  |
| service_date_from | Service date of charge | timestamp | True |  |  |  |
| service_date_from_ld | (Localized date) Service date of charge | timestamp | True |  |  |  |
| posted_date_ld | (Localized date) Charge posted date | date | True |  |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| bill_assignee_id | bill_assignee table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| rule_type | Indicates if the Claim Scrub Rule is Standard or Custom | string | True | 50 | Standard Custom |  |
| business_unit_name | Name of the Business Unit the rule belongs to. | string | True | 50 |  |  |
| title | Title of the Claim Scrub Rule | string | True | 100 |  |  |
| failed_scrub_message | Message to send when the Scrub Rule fails. | string | True | 200 |  |  |
| failed_scrub_assignee | If a claim fails this scrub rule, specify the User or User Group for assignment. | string | True | 30 |  |  |
| scrub_rule_category | Category of the Scrub Rule | string | True | 50 |  |  |
| payer_type | Type of payer(s) associated to the Claim Scrub Rule | string | True | 80 |  |  |
| billing_type | Type of billing associated to the Claim Scrub Rule | string | True | 25 |  |  |
| active | Indicates if the Scrub Rule is active or not. | boolean | True |  |  |  |
| anesthesia_time_range_required |  | boolean | True |  |  |  |
| authorization_required |  | boolean | True |  |  |  |
| operating_physician_required | Operating Physician is only applicable to Facility Bills and rules regarding Operating Physician should only be written for Facility Bill types. This rule option is not available when Type of Billing is set to 'Professional' or 'Professional and Facility'. | boolean | True |  |  |  |
| ordering_physician_required | Ordering Physician is only applicable to Professional Bills and rules regarding Ordering Physician should only be written for Professional Bill types. This rule option is not available when Type of Billing is set to 'Facility' or 'Professional and Facility'. | boolean | True |  |  |  |
| policy_must_be_active | This rule will only apply to medical policy types with status 'Inactive' or 'Unknown/Error'. | boolean | True |  |  |  |
| referring_provider_required | When 'Does Not Contain Any' is selected, the claim scrub will not fail for the selected referring providers. When 'Contains Any' is selected, the claim scrub will fail if the referring provider is any of the selected referring providers. | boolean | True |  |  |  |
| should_remove_assignee | Clear Claim Assignment for Pass/Override | boolean | True |  |  |  |
| supervising_physician_required | Supervising Physician is only applicable to Professional Bills and rules regarding Supervising Physician should only be written for Professional Bill types. This rule option is not available when Type of Billing is set to 'Facility' or 'Professional and Facility'. | boolean | True |  |  |  |
| start_date | Date when the Scrub Rule starts being valid. | date | True |  |  |  |
| end_date | Date when the Scrub Rule finishes being valid. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_payer

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_payer_id | claim_scrub_rule_payer table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| payer_name | Name of the payer. | string | True | 255 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_primary_biller

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_primary_biller_id | claim_scrub_rule_primary_biller table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| primary_biller_id | staff table id | string | False | 20 |  |  |
| primary_biller_name | Name of the primary biller. | string | True | 255 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_primary_provider

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_primary_provider_id | claim_scrub_rule_primary_provider table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| primary_provider_id | staff table id | string | False | 20 |  |  |
| primary_provider_name | Name of the primary provider. | string | True | 255 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_service_location

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_service_location_id | claim_scrub_rule_service_location table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| service_location | Name of the service location (facility). | string | True | 255 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_policy_type

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_policy_type_id | claim_scrub_rule_policy_type table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| policy_type | Name of the policy type associated to the claim scrub rule. | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_payer_plan

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_payer_plan_id | claim_scrub_rule_payer_plan table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| payer_plan_id | payer_plan table id | string | False | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| payer_plan_name | Payer's plan name. | string | True | 100 |  |  |
| payer_id_number | Primary Payer ID number | string | False | 50 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_division

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_division_id | claim_scrub_rule_division table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| division_id | payer table id | string | False | 20 |  |  |
| division_name | Name of the division. | string | True | 35 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_referral_contact

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_referral_contact_id | claim_scrub_rule_referral_contact table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| referral_contact_id | referral_contact table id | string | True | 20 |  |  |
| referral_institution_id | referral_institution table id | string | True | 20 |  |  |
| referral_person_name | Name of the referral person. | string | True | 255 |  |  |
| referral_institution_name | Name of the referral institution. | string | True | 255 |  |  |
| matching_type | Indicates if value selected in the previous field is the one that should be matched or the one that should be filtered out. | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_procedure

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_procedure_id | claim_scrub_rule_procedure table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| type | Indicates if the rule corresponds to a single code, a code range or a code category. | string | True | 14 |  |  |
| code | When not null, indicates either the single code or the beginning of the code range to use for the rule validation. | string | True | 20 |  |  |
| code_end | When not null, indicates the last code in the range to use for the rule validation. | string | True | 20 |  |  |
| match_cpt | Scrub rule CPT to match with code_start. | string | True | 20 |  |  |
| modifier | Modifier to apply to the rule. | string | True | 2 |  |  |
| modifier_matching_type | Indicates if the modifier applies to codes that contain or not contain the modifier. | string | True | 50 |  |  |
| fail_rule_when | Indicates on which scenario the scrub rule should fail. | string | True | 20 |  |  |
| capture_non_reporting_cpt | Flag to determine whether or not $0 should be considered in Claim Scrub Rules. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_procedure_code_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_procedure_code_category_id | claim_scrub_rule_procedure_code_category table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_procedure_id | claim_scrub_rule_procedure table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| code_category_id | code_category table id | string | False | 20 |  |  |
| code_category | Code category name. | string | True | 75 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_scrub_rule_diagnosis

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_scrub_rule_diagnosis_id | claim_scrub_rule_diagnosis table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| claim_scrub_rule_id | claim_scrub_rule table id | string | False | 20 |  |  |
| type | Indicates if the ICD 10 field corresponds to a single code or a code range. | string | True | 11 |  |  |
| code_start | When 'type' is 'Single Code', indicates the single code to validate. Otherwise, indicates the beginning of the range. | string | True | 20 |  |  |
| code_end | When 'type' is 'Range', contains the last value of the range. Otherwise, it should be null. | string | True | 20 |  |  |
| order_on_claim | Indicates the order in which the code should appear in the claim to fail the rule. | string | True | 10 |  |  |
| fail_rule_when | Indicates on which scenario the scrub rule should fail. | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## claim_payer

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| claim_payer_id | claim_payer table id | string | False | 30 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| payer_id | payer table id | string | False | 20 |  |  |
| claim_id | claim table id | string | False | 20 |  |  |
| era_received_id | era_received table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| payer_claim_number | Payer claim reference number | string | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## custom_claim_scrub_rule

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| custom_claim_scrub_rule_id | custom_claim_scrub_rule table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| bill_assignee_id | bill_assignee table id | string | True | 20 |  |  |
| business_unit | Name of the Business Unit the rule belongs to. | string | True | 50 |  |  |
| claim_scrub_rule_title | Title of the Claim Scrub Rule | string | True | 100 |  |  |
| start_date | Date when the Scrub Rule starts being valid. | date | True |  |  |  |
| end_date | Date when the Scrub Rule finishes being valid. | date | True |  |  |  |
| scrub_fail_message | Message to send when the Scrub Rule fails. | string | True | 200 |  |  |
| assign_failed_scrub_to | If a claim fails this scrub rule, specify the User or User Group for assignment. | string | True | 30 |  |  |
| scrub_category | Category of the Scrub Rule | string | True | 50 |  |  |
| clear_claim_assignment_for_pass_override | Clear Claim Assignment for Pass/Override | boolean | True |  |  |  |
| type_of_billing | Type of billing associated to the Claim Scrub Rule | string | True | 25 |  |  |
| payer_selection | Indicates if values selected in field payers are the one that should be matched or the one that should be filtered out. | string | True | 80 |  |  |
| payers | Type of payer(s) associated to the Claim Scrub Rule | string | True | -1 |  |  |
| payer_type | Type of payer(s) associated to the Claim Scrub Rule | string | True | -1 |  |  |
| primary_biller_selection | Indicates if values selected in field primary_billers are the ones that should be matched or the ones that should be filtered out. | string | True | 80 |  |  |
| primary_billers | Type of payer(s) associated to the Claim Scrub Rule | string | True | -1 |  |  |
| policy_type | Type of policies associated to the Claim Scrub Rule | string | True | -1 |  |  |
| service_location_selection | Indicates if values selected in field service_locations are the ones that should be matched or the ones that should be filtered out. | string | True | 80 |  |  |
| service_locations | Service Locations associated to the Claim Scrub Rule | string | True | -1 |  |  |
| primary_provider_selection | Indicates if values selected in field primary_providers are the ones that should be matched or the ones that should be filtered out. | string | True | 80 |  |  |
| primary_providers | Primary providers associated to the Claim Scrub Rule | string | True | -1 |  |  |
| payer_plan_selection | Indicates if values selected in field payer_plans are the ones that should be matched or the ones that should be filtered out. | string | True | 80 |  |  |
| payer_plans | Payer Plans associated to the Claim Scrub Rule | string | True | -1 |  |  |
| division_selection | Indicates if values selected in field divisions are the ones that should be matched or the ones that should be filtered out. | string | True | 80 |  |  |
| divisions | Divisions associated to the Claim Scrub Rule | string | True | -1 |  |  |
| policy_must_be_active | This rule will only apply to medical policy types with status 'Inactive' or 'Unknown/Error'. | boolean | True |  |  |  |
| require_authorization |  | boolean | True |  |  |  |
| require_anesthesia_time_range |  | boolean | True |  |  |  |
| require_operating_physician | Operating Physician is only applicable to Facility Bills and rules regarding Operating Physician should only be written for Facility Bill types. This rule option is not available when Type of Billing is set to 'Professional' or 'Professional and Facility'. | boolean | True |  |  |  |
| require_ordering_physician | Ordering Physician is only applicable to Professional Bills and rules regarding Ordering Physician should only be written for Professional Bill types. This rule option is not available when Type of Billing is set to 'Facility' or 'Professional and Facility'. | boolean | True |  |  |  |
| require_supervising_physician | Supervising Physician is only applicable to Professional Bills and rules regarding Supervising Physician should only be written for Professional Bill types. This rule option is not available when Type of Billing is set to 'Facility' or 'Professional and Facility'. | boolean | True |  |  |  |
| require_referring_provider | When 'Does Not Contain Any' is selected, the claim scrub will not fail for the selected referring providers. When 'Contains Any' is selected, the claim scrub will fail if the referring provider is any of the selected referring providers. | boolean | True |  |  |  |
| last_posted_date_on_claim | Most recent posted date that the Claim Scrub Rule applies to. | date | True |  |  |  |
| scrub_rule_count_by_business_unit | Count of all scrub rules configured under the selected business unit. | int | True |  |  |  |
| claim_count | Number of claims this rule has been applied to. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
