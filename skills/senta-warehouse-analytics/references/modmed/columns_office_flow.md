# Column Dictionary: Office Flow (124 columns)


## facility_resource

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| facility_resource_id | facility_resource table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| facility_resource_pms_identifier | External ID for facility resource | string | True | 20 |  |  |
| capacity_alert | Alert if the patient queue reaches this number. (same as patients_at_once) | int | True |  |  |  |
| room_warning_minutes | Warn me if the patient has been in the room for this many minutes. | int | True |  |  |  |
| patients_at_once | Alert if the patient queue reaches this number. (same as capacity_alert) | int | True |  |  |  |
| reserve_on_check_in | Reserve this room until patient is checked out? | boolean | True |  |  |  |
| status | Status of the Facility Resource | boolean | True |  | Active, Available: True Inactive, Unavailable: False |  |
| resource_type | Type of facility resource. Can be Room, Equpiment, or both. | string | True | 20 | ROOM EQUIPMENT ROOM_AND_EQUIPMENT |  |
| equipment_name | Equipment name | string | True | 50 |  |  |
| room_name | Room name | string | True | 50 |  |  |
| room_type | Type of room | string | True | 20 | SINGLE: Single Patient MULTI: Mutli Patient CHECKED_IN: Checked In PARKING_LOT: Parking Lot |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## facility_resource_detail

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| facility_resource_detail_id | facility_resource_detail table id | string | False | 20 |  |  |
| facility_resource_id | facility_resource table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| appointment_type_id | appointment_type table id | string | True | 20 |  |  |
| facility_name | Name of facility | string | True | 150 |  |  |
| provider_name | Name of provider | string | True | 250 |  |  |
| appointment_type_name | Name of appointment type | string | True | 25 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## appointment_facility_resource_reservation

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| appointment_facility_resource_reservation_id | appointment_facility_resource_reservation table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| facility_resource_id | facility_resource table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## facility_resource_utilization_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| facility_resource_utilization_log_id | facility_resource_utilization_log table id | string | False | 20 |  |  |
| facility_resource_id | facility_resource table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| checked_in_by_staff_id | staff table id | string | True | 20 |  |  |
| checked_out_by_staff_id | staff table id | string | True | 20 |  |  |
| come_in_notification_sent | Notification has been sent for patient to come into room. | boolean | True |  |  |  |
| room_leave_reason | Reason patient left the room | string | True | 20 | CHECK_OUT: Patient is checking out OTHER: Patient has left the building / Other CHANGE_ROOM: Changed to different room TIMEOUT: Patient was checked into the room for more than 8 hours |  |
| check_in_time | Time of check in | timestamp | True |  |  |  |
| check_out_time | Time of check out | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_id | task table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| patient_assignee_id | patient table id. Only for routing ownership of Task when assignee is a patient. | string | True | 20 |  |  |
| parent_task_id | task table id. Indicates the id of the parent task. | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| appointment_id | appointment table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| business_unit_id | business_unit table id | string | True | 20 |  |  |
| result_log_id | result_log table id | string | True | 20 |  |  |
| chart_note_id | chart_note table id. Note: This column will be deprecated in release 1.25 and removed in 1.26. | string | True | 20 |  | True |
| intra_mail_id | intra_mail table id. Note: This column will be deprecated in release 1.25 and removed in 1.26. | string | True | 20 |  | True |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| modified_by_staff_id | staff table id | string | True | 20 |  |  |
| task_unique_identifier | Task unique id | string | True | 50 |  |  |
| task_patient_name | Name of the patient associated to the task | string | True | 150 |  |  |
| task_name | Title of the task | string | True | 50 | AUTHORIZATION CC_HPI COLLECTION COMMUNICATION FAX NOTIFY NOTIFY_WHEN_ARRIVE OBTAIN ONLINE_CHECK_IN ORDER PATHOLOGY PRESCRIBE REASSURE RECALL REFER RETURN_TO_CLINIC REVIEW RE_EVALUATE SCHEDULE SIGN TEST |  |
| task_detail | Details of the task | string | True | 250 |  |  |
| main_note | Main note for the task | string | True | 2000 |  |  |
| priority | Priority of the task | string | True | 50 | HIGH NORMAL STAT 4707648 |  |
| task_type | Type of task | string | True | 25 | ASSIGNABLE COLLECTION PATIENT_ASSIGNABLE |  |
| current_status | Task status | string | True | 25 | Archived Completed New New (Reopened) Pending |  |
| appointment | Appointment associated to the task. | string | True | 45 |  |  |
| task_facility_name | Facility associated to the task. | string | True | 100 |  |  |
| bill_assignee_group_name | Name of the bill assignee group associated to the task. | string | True | 50 |  |  |
| intra_mail | IntraMail associated with the task. Note: This column will be deprecated in release 1.25 and removed in 1.26. | string | True | 280 |  | True |
| is_complete | Indicates if the task is complete or not. | boolean | True |  |  |  |
| track_history | Indicates if the task has history tracking enabled on not. Only available for task type 'COLLECTION' and 'PATIENT_ASSIGNABLE'. | boolean | True |  |  |  |
| time_zone | Facility time zone | string | True | 30 |  |  |
| visit_date | Date of the visit associated to the task. | timestamp | True |  |  |  |
| date_assigned | Date when the task was assigned. | timestamp | True |  |  |  |
| date_due | Date when the task will be due. | timestamp | True |  |  |  |
| date_completed | Date when the task was completed. | timestamp | True |  |  |  |
| date_restarted | Date when the task was restarted. | timestamp | True |  |  |  |
| date_last_note_added | Date when the last note was added to the task. | timestamp | True |  |  |  |
| visit_date_ld | Localized date of the visit associated with the task | timestamp | True |  |  |  |
| date_assigned_ld | Localized date when the task was assigned | timestamp | True |  |  |  |
| date_due_ld | Localized date when the task will be due | timestamp | True |  |  |  |
| date_completed_ld | Localized date when the task was completed | timestamp | True |  |  |  |
| date_restarted_ld | Localized date when the task was restarted | timestamp | True |  |  |  |
| date_last_note_added_ld | Localized date when the last node for the task was added | timestamp | True |  |  |  |
| date_created | Date the visit was created (database generated). | timestamp | True |  |  |  |
| date_modified | Date the visit was modified (database generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_note

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_note_id | task_note table id | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| current_task_note_id | task_note table id. Indicates what note has superseded this note when editing. May equal self, which indicates that the note is the latest in a series of edits. | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| note | The note left by the user in the task. | string | True | 2000 |  |  |
| note_type | Task type associated with note. | string | True | 100 |  |  |
| archived | Indicates if the note has been archived. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_attachment_id | task_attachment table id | string | False | 30 |  |  |
| file_attachment_id | file_attachment table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_fax_inbound

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_fax_inbound_id | task_fax_inbound table id | string | False | 30 |  |  |
| fax_inbound_id | fax_inbound table id. | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_staff_assignee

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_staff_assignee_id | task_staff_assignee table id | string | False | 30 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| task_id | task table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| assignee_by_group | Indicates if the user was assigned to the task as part of a group. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_group_assignee

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_group_assignee_id | task_group_assignee table id | string | False | 20 |  |  |
| firm_group_id | firm_group table id | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_order_log

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_order_log_id | task_order_log table id | string | False | 30 |  |  |
| order_log_id | order_log table id | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## task_additional

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| task_additional_id | task_additional table id | string | False | 20 |  |  |
| task_id | task table id | string | False | 20 |  |  |
| chart_note_id | chart_note table id | string | True | 20 |  |  |
| intra_mail_id | intra_mail table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| intra_mail | IntraMail associated with the task. | string | True | 280 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
