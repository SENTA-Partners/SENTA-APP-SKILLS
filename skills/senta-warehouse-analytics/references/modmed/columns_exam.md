# Column Dictionary: Exam (27 columns)


## exam_set

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| exam_set_id | exam_set table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| exam_set | Name of the exam set performed. | string | True | 255 | See static_exam_set.exam_set |  |
| medical_domain | Medical domain the chief complaint is part of. | string | True | 255 | AESTHETICS ALLERGY COSMETIC DERMATOLOGY ENT FAMILY_MEDICINE GI INTERNAL_MEDICINE OB_GYN OPHTHALMOLOGY OPTOMETRY ORTHOPEDICS PAIN_MANAGEMENT PEDIATRICS PLASTICS PODIATRY PRIMARY_CARE RHEUMATOLOGY UROLOGY |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## exam_element

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| exam_element_id | exam_element table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| exam_set_id | exam_set table id | string | True | 20 |  |  |
| element | Exam element | string | True | 255 | See static_exam_element.element |  |
| system | Bodily system the element is a part of | string | True | 255 | See static_exam_element.system |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## exam_element_metadata

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| exam_element_metadata_id | exam_element_metadata table id | string | False | 20 |  |  |
| exam_element_id | exam_element table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| variable | Variable name for the metadata item. Variables are defined and entered for each exam element. | string | True | 50 | See static_exam_element_metadata.variable |  |
| question_text | Question displayed to the user | string | True | 255 | See static_exam_element_metadata.question_text |  |
| type | Data type of the metadata item | string | True | 20 | See static_exam_element_metadata.type |  |
| value | Metadata response value for single-select or text input items. | string | True | 8000 | See static_exam_element_metadata_selection.value |  |
| range_value | Numeric response value | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## exam_element_metadata_selection

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| exam_element_metadata_selection_id | exam_element_metadata_selection table id | string | False | 20 |  |  |
| exam_element_metadata_id | exam_element_metadata table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| value | Metadata response value | string | True | 255 | See static_exam_element_metadata_selection.value |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
