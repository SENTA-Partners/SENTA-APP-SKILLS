# Column Dictionary: Document Management (121 columns)


## document_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| document_category_id | document_category table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| category | Name of the category | string | True | 2000 |  |  |
| description | Description of the category | string | True | 2000 |  |  |
| section | Section of the category | string | True | 2000 | CONSENTS CORRESPONDENCE FINANCIAL INSURANCE MEDICAL NARCOTICS PRACTICE TELEMEDICINE_CONSENT TEST_RESULTS |  |
| status | Status of the category | string | True | 20 | ACTIVE ALWAYS_ACTIVE INACTIVE |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## document_firm

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| document_firm_id | document_firm table id | string | False | 20 |  |  |
| firm_id | firm table id | string | True | 20 |  |  |
| document_category_id | document_category table id | string | True | 20 |  |  |
| title | Title of document | string | True | 1000 |  |  |
| file_name | Document filename | string | True | 255 |  |  |
| enabled | Indicates if the document is enabled | boolean | True |  |  |  |
| enable_all_facilities | Indicates if the document is enabled for all facilities | boolean | True |  |  |  |
| enable_all_providers | Indicates if the document is enabled for all providers | boolean | True |  |  |  |
| finalize_document_upon_patient_submission | Indicates whether the document is finalized upon patient submission | boolean | True |  |  |  |
| read_only_when_sent_to_portal | Indicates whether the document is read only when sent to the portal | boolean | True |  |  |  |
| visible | Indicates whether the document is visible | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## file_attachment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| file_attachment_id | file_attachment table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| uploaded_by_staff_id | staff table id | string | True | 20 | Staff member that uploaded the file |  |
| uploaded_by_patient_id | patient table id | string | True | 20 | Patient that uploaded the file |  |
| patient_id | patient table id | string | True | 20 | Patient the attachment is assigned to. NULL if not assigned to a patient. |  |
| visit_id | visit table id | string | True | 20 | Visit the attachment is assigned to. NULL if not assigned to a visit. |  |
| document_category_id | document_category table id | string | True | 20 | Category assigned to the file attachment. NULL if there is no category. |  |
| document_firm_id | document_firm table id | string | True | 20 | Document assigned to the file attachment. NULL if there is no document. |  |
| diagnosis_id | diagnosis table id | string | True | 20 |  |  |
| elab_order_id | elab_order table id | string | True | 20 |  |  |
| lab_request_id | lab_request table id | string | True | 20 |  |  |
| procedure_id | procedure table id | string | True | 20 |  |  |
| procedure_body_location_id | procedure_body_location table id | string | True | 20 |  |  |
| document_category | Category of the file attachment | string | True | 2000 |  |  |
| title | Title of the file attachment | string | True | 2000 |  |  |
| file_name | File name of the attachment | string | True | 255 |  |  |
| file_type | Type of the file attached. | string | True | 1 |  |  |
| file_size | Size (in bytes) of the file attached. | bigint | True |  |  |  |
| document_status | Indicates if the document is final or a draft. | string | True | 20 |  |  |
| photo_permission | Indicates the level of access to an attached picture. | string | True | 10 |  |  |
| file_exists_checked | Flag to show that file existence was checked. | boolean | True |  |  |  |
| imported | Indicates if the file attachment is imported. | boolean | True |  |  |  |
| in_visit_note | Indicates if the file attachment is in visit note. | boolean | True |  |  |  |
| is_editable | Indicates if the file attachment is editable. | boolean | True |  |  |  |
| is_primary_photo | Indicates if the file attachment is a primary photo. | boolean | True |  |  |  |
| visible | Indicates if the file attachment is visible or not. | boolean | True |  |  |  |
| added_on_date | Date the file was uploaded | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fax_template

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fax_template_id | fax_template table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| position | Position in the list of templates | int | True |  |  |  |
| title | Title of the template | string | True | 100 |  |  |
| type | Type of the template. All except HTML are deprecated. Non-HTML types represent all templates built before version 4.0 where the templates were refactored to use Textbox.io. | string | True | 100 | HTML SURGICAL CUSTOM REFER_TO ATTACHMENTS THANKS_FOR_REFERRAL THANKS_FOR_REFERRAL_SIMPLE |  |
| single_visit | If true, template is used for single visits. | boolean | True |  |  |  |
| referral | If the template is a builtin referral template (see diagnosis_referral table). | boolean | True |  |  |  |
| referral_thanks | If the template is a builtin referral thanks template (see diagnosis_referral_correspondence table). | boolean | True |  |  |  |
| archived | If the fax template is archived. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fax_management

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fax_management_id | fax_management table id | string | False | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| fax_template_id | fax_template table id | string | True | 20 |  |  |
| created_by_staff_id | staff table id | string | True | 20 |  |  |
| released_by_staff_id | id of the staff that released the fax. | string | True | 20 |  |  |
| file_name | Filename of the fax attachment. | string | True | 1000 |  |  |
| intro | Intro of the fax message. | string | True | 10000 |  |  |
| body | Body of the fax message. | string | True | -1 |  |  |
| ending | End text of the fax message. | string | True | 10000 |  |  |
| include_antepartum_record | If true, antepartum record is included in fax. | boolean | True |  |  |  |
| include_body_diagram | If true, body diagram is included in fax. Only appears if Visit Notes have been added to fax. | boolean | True |  |  |  |
| include_ccd | If true, ccd is included in fax. Only appears if Visit Notes have been added to fax. | boolean | True |  |  |  |
| include_ccr | If true, ccr is included in fax. | boolean | True |  |  |  |
| include_face_sheet | If true, face sheet is included in the fax. | boolean | True |  |  |  |
| include_hipaa_cover_sheet | If true, HIPAA cover sheet is included in the fax. | boolean | True |  |  |  |
| include_notes | If true, notes are included in the fax. | boolean | True |  |  |  |
| include_summary | If true, summary is included in the fax. | boolean | True |  |  |  |
| save_to_chart | If true, fax is saved to the patient's chart. | boolean | True |  |  |  |
| archived | If true, fax is archived. | boolean | True |  |  |  |
| queued_date | Date on which fax was queued. | timestamp | True |  |  |  |
| released_date | Date on which the fax was released. | timestamp | True |  |  |  |
| archived_date | Date on which fax was archived. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fax_outbound

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fax_outbound_id | fax_outbound table id | string | False | 20 |  |  |
| fax_link_id | fax_link id (used for tables that link through fax_management_id) *Note*: This column will be deprecated on our next release. Please use fax_management_id instead. | string | True | 20 |  |  |
| fax_management_id | fax_management table id | string | True | 20 |  |  |
| fax_template_id | fax_template table id | string | False | 20 |  |  |
| queued_by_staff_id | staff table id | string | True | 20 | Staff member that queued the fax |  |
| released_by_staff_id | staff table id | string | True | 20 | Staff member that released the fax |  |
| referral_contact_id | referral_contact table id | string | True | 20 | Recipient of the fax (person). |  |
| referral_institution_id | referral_institution table id | string | True | 20 | Recipient of the fax (institution). |  |
| patient_id | patient table id | string | True | 20 | Patient associated with the fax. |  |
| visit_id | visit table id | string | True | 20 | Visit associated with the fax. |  |
| transaction_id | Transaction ID. If positive, indicates a transaction identifier for the fax transmission. If negative, indicates a failure code. | bigint | True |  |  |  |
| date_queued | Date fax was queued | timestamp | True |  |  |  |
| date_released | Date fax was released | timestamp | True |  |  |  |
| date_submitted | Date fax was submitted. Does not get populated until the fax is sent (at the same time as date_sent). | timestamp | True |  |  |  |
| date_sent | Date fax was sent. | timestamp | True |  |  |  |
| recipient_type | Recipient Type | string | True | 50 | TO CC FAX_NUMBER |  |
| include_body_diagram | If body diagram is included in the fax | boolean | True |  |  |  |
| include_ccd | If CCD is included in the fax | boolean | True |  |  |  |
| include_hipaa_cover_sheet | If HIPAA cover sheet is included in the fax | boolean | True |  |  |  |
| include_notes | If notes are included in the fax | boolean | True |  |  |  |
| include_summary | If summary is included in the fax | boolean | True |  |  |  |
| include_ccr | If CCR is included in the fax | boolean | True |  |  |  |
| auto_fax | Designates if a fax was automatically sent by the Auto Fax feature in EMA | boolean | True |  |  |  |
| pages | Number of pages in the queued fax | int | True |  |  |  |
| pages_sent | Number of pages sent | int | True |  |  |  |
| status | Title of the status code | string | True | 100 | See Appendix C |  |
| date_created | Date created (system generated). | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## fax_inbound

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| fax_inbound_id | fax_inbound table id | string | False | 20 |  |  |
| fax_line_id | fax_line table id *Note*: This column will be deprecated on our next release. | string | False | 20 |  | True |
| file_attachment_id | file_attachment table id | string | True | 20 |  |  |
| patient_id | patient table id | string | True | 20 |  |  |
| date_received | Date/time received | timestamp | True |  |  |  |
| pages | Number of pages | int | True |  |  |  |
| csid | CSID | string | True | 255 |  |  |
| transaction_id | Transaction ID | int | True |  |  |  |
| caller_id | Caller ID | string | True | 255 |  |  |
| status | Title of the status code | string | True | 100 | See Appendix C |  |
| phone_number | Receive phone number for the fax line | string | True | 50 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
