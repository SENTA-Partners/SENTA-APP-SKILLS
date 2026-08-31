# Column Dictionary: Appointment (246 columns)


## appointment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_id | appointment table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| provider_id | staff table id | string | False | 20 |  |  |
| primary_provider_id | staff table id for the primary provider assigned to the patient's appointment | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| cancelled_by_staff_id | staff table id | string | True | 20 |  |  |
| appointment_type_id | appointment_type table id | string | False | 20 |  |  |
| referral_contact_id | referral_contact table id | string | True | 20 |  |  |
| referral_institution_id | referral_institution table id. | string | True | 20 |  |  |
| linked_appointment_id | appointment table id for linked appointment | string | True | 20 |  |  |
| insurance_policy_auth_primary_id | insurance_policy_authorization table id | string | True | 20 |  |  |
| insurance_policy_auth_secondary_id | insurance_policy_authorization table id | string | True | 20 |  |  |
| insurance_policy_auth_tertiary_id | insurance_policy_authorization table id | string | True | 20 |  |  |
| facility_resource_id | facility_resource table id. *Note*: This field is deprecated. The appointment-to-facility-resource relationship is one-to-many. Please use the appointment_facility_resource_reservation to retrieve this information. | string | True | 20 |  | True |
| appointment_reminder_id | appointment_reminder table id | string | True | 20 |  |  |
| patient_case_id | patient_case table id | string | True | 20 |  |  |
| financial_category_id | financial_category table id | string | True | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| ordering_provider_id | staff table id | string | True | 20 |  |  |
| ordering_referral_contact_id | referral_contact table id. | string | True | 20 |  |  |
| appointment_created_by | Full name of firm user who created appointment | string | True | 200 |  |  |
| appointment_pms_id | PMS ID | string | True | 50 |  |  |
| guarantor_name | Full name of guarantor | string | True | 220 |  |  |
| appointment_rescheduled | Indicates appointment was rescheduled | boolean | True |  |  |  |
| appointment_type | appointment type name | string | True | 250 |  |  |
| appointment_groups | Appointment group(s) name(s) associated to the Appointment Type | string | True | -1 |  |  |
| authorization_number_list | Combined list of insurance authorization numbers | string | True | 250 |  |  |
| financial_category | financial category name | string | True | 255 |  |  |
| reportable_reason | Reportable reason | string | True | 25 | MEDICAL_NON_EMERGENCY MEDICAL_EMERGENCY AUTOMOBILE_ACCIDENT COSMETIC_SERVICES VISION WORKERS_COMP OTHER |  |
| payment_method | Payment method | string | True | 15 | MEDICAL AUTOMOBILE VISION WORKERS_COMP NONE_SELF_PAY OTHER |  |
| primary_insurance_policy_number | Primary insurance policy number | string | True | 100 |  |  |
| primary_payer_name | Primary insurance company name for payment | string | True | 250 |  |  |
| secondary_insurance_policy_number | Secondary insurance policy number | string | True | 100 |  |  |
| secondary_payer_name | Secondary insurance company name for payment | string | True | 250 |  |  |
| tertiary_insurance_policy_number | Tertiary insurance policy number | string | True | 100 |  |  |
| tertiary_payer_name | Tertiary insurance company name for payment | string | True | 250 |  |  |
| appointment_status | status | string | True | 14 | PENDING CONFIRMED ARRIVED CHECKED_IN CHECKED_OUT NO_SHOW CANCELLED |  |
| duration | Appointment duration. | int | False |  |  |  |
| reason_for_visit | Reason for visit | string | True | 110 |  |  |
| reason_for_visit_notes | Reason for visit (free form text) | string | True | 110 |  |  |
| appointment_notes | Appointment notes | string | True | 3000 |  |  |
| new_patient_flag | If patient was created inside of appointment details | boolean | True |  |  |  |
| cancel_reason | Reason for cancellation | string | True | 100 |  |  |
| cancel_notes | Cancellation notes | string | True | 2048 |  |  |
| custom_cancel_reason | Custom reason for cancellation. | string | True | 100 |  |  |
| reschedule_reason | Reason for reschedule | string | True | 40 |  |  |
| patient_first_name | Patient's first name for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 100 |  |  |
| patient_last_name | Patient's last name for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 100 |  |  |
| patient_middle_name | Patient's middle name for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 100 |  |  |
| patient_date_of_birth | Patient's date of birth. May take 1-2 days to update after appointment takes place. | timestamp | True |  |  |  |
| patient_sex | Patient's sex. May take 1-2 days to update after appointment takes place. | string | True | 20 |  |  |
| patient_mrn | Patient's mrn for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 20 |  |  |
| patient_email | Patient's email for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 100 |  |  |
| patient_home_phone | Patient's home phone for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 50 |  |  |
| patient_mobile_phone | Patient's mobile phone for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 20 |  |  |
| patient_work_phone | Patient's work phone for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 50 |  |  |
| patient_preferred_phone_type | Patient's preferred phone for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 20 |  |  |
| patient_status | Patient's status for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 50 | ACTIVE INACTIVE INACTIVE_DUPLICATE DISCHARGED DECEASED |  |
| patient_auto_pay_status | Status of Patient's Auto Pay. May take 1-2 days to update after appointment takes place. | string | True | 20 | ACTIVE CANCELLED DEACTIVATED DECLINED PENDING |  |
| room_equipment_name | Room and equipment names used for given appointment. May take 1-2 days to update after appointment takes place. | string | True | 2000 |  |  |
| previous_copay_amount | Copay amount at the time of the patient's previous appointment | double | True |  |  |  |
| previous_copay_deductible | Copay deductible amount at the time of the patient's previous appointment | double | True |  |  |  |
| previous_copay_percent | Copay percent amount at the time of the patient's previous appointment | double | True |  |  |  |
| previous_deductible_remaining | Deductible amount remaining at the time of the patient's previous appointment | double | True |  |  |  |
| previous_eligibility_active | Indicates the patient's insurance eligibility status at the time of the patient's previous appointment | boolean | True |  |  |  |
| appointment_authorization_is_expired | If an Appointment has a linked Authorization from the Primary Insurance Policy, does the Authorization expire before the appointment_start_date? | boolean | True |  | TRUE: appointment_start_date >= primary_insurance_policy_authorization_start_date AND appointment_start_date < primary_insurance_policy_authorization_end_date FALSE: appointment_start_date >= primary_insurance_policy_authorization_start_date AND appointment_start_date >= primary_insurance_policy_authorization_end_date NULL: appointment_start_date < primary_insurance_policy_authorization_start_date OR primary_insurance_policy_authorization_start_date IS NULL |  |
| appointment_was_confirmed | Indicates if at any point in time this appointment has ever been confirmed. | boolean | True |  |  |  |
| most_recent_time_slot_was_confirmed | Indicates if the most recent appointment time slot was confirmed. | boolean | True |  |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| appointment_start_date | Appointment date. | timestamp | True |  |  |  |
| appointment_end_date | Appointment date, in case it was not close the same day. | timestamp | True |  |  |  |
| appointment_date_created | Date the appointment was created. | timestamp | True |  |  |  |
| appointment_date_cancelled | Date the appointment was cancelled. | timestamp | True |  |  |  |
| arrival_time | Patient appointment arrival time. | timestamp | True |  |  |  |
| check_in_time | Patient appointment check-in time. | timestamp | True |  |  |  |
| check_out_time | Patient appointment check-out time. | timestamp | True |  |  |  |
| patient_info_date | Patient's demographic information capture date. May take 1-2 days to update after appointment takes place. | timestamp | True |  |  |  |
| rescheduled_date | Patient's appointment rescheduled date. May be 1-2 hours behind. | timestamp | True |  |  |  |
| patient_date_of_birth_ld | (Localized date) Patient's date of birth. May take 1-2 days to update after appointment takes place. | timestamp | True |  |  |  |
| appointment_start_date_ld | (Localized date) Appointment date. | timestamp | True |  |  |  |
| appointment_end_date_ld | (Localized date) Appointment date, in case it was not close the same day. | timestamp | True |  |  |  |
| appointment_date_created_ld | (Localized date) Date the appointment was created. | timestamp | True |  |  |  |
| appointment_date_cancelled_ld | (Localized date) Date the appointment was cancelled. | timestamp | True |  |  |  |
| arrival_time_ld | (Localized date) Patient appointment arrival time. | timestamp | True |  |  |  |
| check_in_time_ld | (Localized date) Patient appointment check-in time. | timestamp | True |  |  |  |
| check_out_time_ld | (Localized date) Patient appointment check-out time. | timestamp | True |  |  |  |
| patient_info_date_ld | (Localized date) Patient's demographic information capture date. May take 1-2 days to update after appointment takes place. | timestamp | True |  |  |  |
| rescheduled_date_ld | (Localized date) Patient's appointment rescheduled date. May be 1-2 hours behind. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_log_id | appointment_log table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| previous_facility_id | facility table id. | string | False | 20 |  |  |
| event_by_staff_id | staff table id if event is generated by staff. | string | True | 20 |  |  |
| event_by_patient_id | patient table id if event is generated by patient. | string | True | 20 |  |  |
| new_facility_id | facility table id for the new facility. If facility was changed. | string | True | 20 |  |  |
| previous_provider_id | staff table id for the provider. | string | False | 20 |  |  |
| new_provider_id | staff table id for the new provider. If provider was changed. | string | True | 20 |  |  |
| rescheduled | Appointment re-scheduled flag. | boolean | False |  |  |  |
| previous_appointment_duration | Active flag for appointment type link | int | True |  |  |  |
| new_appointment_duration | Active flag for appointment type link | int | True |  |  |  |
| status_changed | Appointment status changed flag. | boolean | False |  |  |  |
| previous_appointment_status | Previous appointment status. | string | True | 14 | PENDING CONFIRMED ARRIVED CHECKED_IN CHECKED_OUT NO_SHOW CANCELLED |  |
| new_appointment_status | New appointment status. | string | True | 14 | PENDING CONFIRMED ARRIVED CHECKED_IN CHECKED_OUT NO_SHOW CANCELLED |  |
| cancel_notes | Cancellation notes. | string | True | 2048 |  |  |
| cancel_reason | Reason for cancellation. | string | True | 100 |  |  |
| custom_cancel_reason | Custom reason for cancellation. | string | True | 100 |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| appointment_log_time | appointment_log time stamp. | timestamp | True |  |  |  |
| previous_appointment_date | Date for previous appointment. | timestamp | True |  |  |  |
| new_appointment_date | Date for new appointment. | timestamp | True |  |  |  |
| appointment_log_time_ld | (Localized date) appointment_log time stamp. | timestamp | True |  |  |  |
| previous_appointment_date_ld | (Localized date) Date for previous appointment. | timestamp | True |  |  |  |
| new_appointment_date_ld | (Localized date) Date for new appointment. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_authorization

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_authorization_id | appointment_authorization table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| insurance_policy_authorization_id | insurance_policy_authorization table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_waitlist

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_waitlist_id | appointment_waitlist table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| appointment_type_id | appointment_type table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| added_by_staff_id | Staff table id for user which added patient to wait list. | string | False | 20 |  |  |
| removed_by_staff_id | Staff table id for user which removed patient from wait list. | string | True | 20 |  |  |
| waitlist_note | Wait list notes. | string | True | -1 |  |  |
| start_date_ld | Requested start date for appointment (local date). | date | True |  |  |  |
| end_date_ld | End date for appointment (local date). | date | True |  |  |  |
| entered_date | Entry added from wait list time stamp. | timestamp | True |  |  |  |
| removed_date | Entry removed from wait list time stamp. | timestamp | True |  |  |  |
| day_monday | Patient appointment day preference. | boolean | True |  |  |  |
| day_tuesday | Patient appointment day preference. | boolean | True |  |  |  |
| day_wednesday | Patient appointment day preference. | boolean | True |  |  |  |
| day_thursday | Patient appointment day preference. | boolean | True |  |  |  |
| day_friday | Patient appointment day preference. | boolean | True |  |  |  |
| day_saturday | Patient appointment day preference. | boolean | True |  |  |  |
| day_sunday | Patient appointment day preference. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_facility_waitlist

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_facility_waitlist_id | appointment_facility_waitlist table id | string | False | 20 |  |  |
| appointment_waitlist_id | appointment_waitlist table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_provider_waitlist

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_provider_waitlist_id | appointment_provider_waitlist table id | string | False | 20 |  |  |
| appointment_waitlist_id | appointment_waitlist table id | string | False | 20 |  |  |
| provider_id | staff table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_reminder

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_reminder_id | appointment_reminder table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| contact_type | Appointment reminder contact type. | string | True | 45 | PHONE EMAIL SMS UNKNOWN |  |
| confirmation_status | Reminder confirmation status. | string | True | 1000 | UNCONFIRMED CONFIRMED CANCELED RESCHEDULED REQUESTED_RESCHEDULE REQUESTED_CANCELLATION UNKNOWN |  |
| response_type | Reminder response entry types. | string | True | 45 | ANSWERING_MACHINE AUTO_UPDATE BAD_EMAIL_ADDRESS BAD_NUMBER BUSY_NUMBER EMAIL_SENT EMAIL_VIEWED HANGUP NO_ANSWER NO_RESPONSE REPEAT SMS_RECEIVED SMS_SENT SMS_UNDELIVERED TRANSFER |  |
| note | Reminder notes. | string | True | -1 |  |  |
| activity_date | Reminder entry date. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_insurance_policy

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_insurance_policy_id | appointment_insurance_policy table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_attachment_id | appointment_attachment table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| file_attachment_id | file_attachment table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_insurance_policy_snapshot

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_insurance_policy_snapshot_id | appointment_insurance_policy_snapshot table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| insurance_policy_id | insurance_policy table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Order of insurance policy history. | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_attachment_snapshot

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_attachment_snapshot_id | appointment_attachment_snapshot table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## recall_type

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| recall_type_id | recall_type table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| appointment_type_id | appointment_type table id | string | False | 20 |  |  |
| recall_type | Recall Type. | string | True | 100 |  |  |
| appointment_type | Appointment type name. | string | True | 25 |  |  |
| duration | Integer value for recall duration. | int | True |  |  |  |
| frequency | Frequency of duration field value. | string | True | 25 | MONTH WEEK YEAR |  |
| frequency_in_days | Duration times frequency. | int | True |  |  |  |
| status | Status flag for the recall type. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## recall

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| recall_id | recall table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| recall_type_id | recall_type table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| appointment_type_id | appointment_type table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| recall_created_by_staff_id | staff table id | string | True | 20 |  |  |
| duration | Recall duration. | string | True | 50 |  |  |
| reason | Recall reason | string | True | 100 |  |  |
| recall_appointment_notes | Recall notes. | string | True | 255 |  |  |
| status | Status of recall. | string | True | 50 | CLOSED COMPLETED OPEN OVERDUE SCHEDULED |  |
| pms_id | PMS ID | string | True | 50 |  |  |
| pms_id_type | PMS ID type | string | True | 100 |  |  |
| target_due_date | Recall target due date. | date | True |  |  |  |
| recall_created_date | Recall date created. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## recall_activity

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| recall_activity_id | recall_activity table id | string | False | 20 |  |  |
| recall_id | recall table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| activity_created_by_staff_id | staff table id | string | False | 20 |  |  |
| update_action_taken | Recall update action taken | string | True | 100 | CLOSED_BAD_DATA CLOSED_DUPLICATE_RECALL CLOSED_OTHER CLOSED_PATIENT_REFUSED_SERVICE LETTER_SENT PHONE_CALL PORTAL_MESSAGE_SENT |  |
| recall_status | Recall status. | string | True | 50 | CLOSED COMPLETED OPEN OVERDUE SCHEDULED |  |
| recall_activity_history_notes | Recall activity history notes | string | True | 300 |  |  |
| activity_date | Recall activity date. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## calendar_event

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| calendar_event_id | calendar_event table id | string | False | 60 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| calendar_event_identifier | Calendar event identifier. Used for filtering all providers, facilities and dates associated to one event. | string | True | 20 |  |  |
| provider_name | Name of the provider associated with the event | string | True | 250 |  |  |
| notes | Notes associated with the event | string | True | 512 |  |  |
| event_type | Indicates if the calendar event is either a time block or a note. | string | True | 5 | BLOCK NOTE |  |
| from_time_in_minutes | Start time of the calendar event, in minutes, from the start of the day. | int | True |  |  |  |
| to_time_in_minutes | End time of the calendar event, in minutes, from the start of the day. | int | True |  |  |  |
| full_day_block | Indicates if the event is a full day block | boolean | True |  |  |  |
| blocking | Indicates if the event is a blocking event | boolean | True |  |  |  |
| visible | Indicates if the calendar event has been deleted. | boolean | True |  |  |  |
| all_providers | Indicates if the event is associated with all providers | boolean | True |  |  |  |
| all_locations | Indicates if the event is associated with all locations | boolean | True |  |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| event_date | Event date. | date | True |  |  |  |
| scheduled_start_time | Scheduled start date time. | timestamp | True |  |  |  |
| scheduled_end_time | Scheduled end date time. | timestamp | True |  |  |  |
| scheduled_start_time_ld | (Localized) Schedule start date time. | timestamp | True |  |  |  |
| scheduled_end_time_ld | (Localized) Schedule end date time. | timestamp | True |  |  |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
