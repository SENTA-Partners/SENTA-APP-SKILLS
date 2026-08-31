# Column Dictionary: Inventory (341 columns)


## product

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| product_id | Product table id | string | False | 20 |  |  |
| firm_id | Firm table id | string | False | 20 |  |  |
| manufacturer_id | Manufacturer table id | string | True | 20 |  |  |
| product_category_id | product_category table id | string | True | 20 |  |  |
| created_by_staff_id | Staff table id | string | False | 20 |  |  |
| manufacturer_name | Manufacturer name | string | True | 100 |  |  |
| manufacturer_description | Manufacturer description | string | True | 300 |  |  |
| manufacturer_active | Active flag for manufacturer | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| product_name | Product name | string | True | 100 |  |  |
| product_category | Product category name | string | True | 100 |  |  |
| product_category_description | Product category description | string | True | 300 |  |  |
| product_category_active | Active flag for product category | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| price | Total price of product. Number of units multiplied by the price per unit | double | True |  |  |  |
| floor_price_per_unit | Minimum price allowed for sale | double | True |  |  |  |
| price_per_unit | Price per unit | double | True |  |  |  |
| is_taxable | Product is taxable flag | boolean | True |  |  |  |
| description | Product description | string | True | 300 |  |  |
| units_per_package | Number of units in a package | int | True |  |  |  |
| unit_of_measure | Unit of measurement for a single unit | string | True | 25 | EA MILLILITERS UNITS OZ PCS |  |
| package_type | Packaging type for product | string | True | 20 | BOX BOTTLE PACKAGE COMPACT APPLICATOR SHEET PUMP AERO_BOTTLE JAR VIAL TUBE PACKET PILLS CAN TUBE_SPRAY SYRINGE BRUSH BOTTLE_SPRAY |  |
| payment_method | Payment method | string | True | 25 | SUPPLY PLAN_BILLING INVENTORY_BILLING |  |
| used_during_visit | Whether the product was used during the visit | boolean | True |  |  |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| upc | Universal Product Code | string | True | 50 |  |  |
| barcode | Product bar code | string | True | 50 |  |  |
| sku | Stock Keeping Unit | string | True | 50 |  |  |
| ndc | National Drug Code | string | True | 15 |  |  |
| product_type |  | string | True | 10 |  |  |
| frequency | frequency | string | True | 4 |  |  |
| priority_of_use | Product usage priority | string | True | 20 | PRIORITY_20 PRIORITY_30 PRIORITY_50 PRIORITY_70 PRIORITY_80 |  |
| directions | Product usage directions | string | True | 4000 |  |  |
| low_stock_warning | Threshold for low stock warning | int | True |  |  |  |
| critical_stock_warning | Threshold for low stock warning | int | True |  |  |  |
| order_max_stock | Max stock allowed to order | int | True |  |  |  |
| display_on_handout | Whether image is displayed on handout | boolean | True |  | Yes: True No: False |  |
| product_status | Active status for product | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| allow_posting_at_checkout | Allow posting at checkout flag | boolean | True |  | Yes: True No: False |  |
| is_system_product | Whether product was created from established system product | boolean | True |  |  |  |
| body_location | Location for product application | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## stock

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| stock_id | Stock table id | string | False | 20 |  |  |
| product_id | Product table id | string | False | 20 |  |  |
| firm_id | Firm table id | string | False | 20 |  |  |
| cabinet_id | Cabinet table id | string | False | 20 |  |  |
| status | Active status for stock | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| cabinet_name | Cabinet name | string | True | 150 |  |  |
| expiration_date | Stock expiration date | date | True |  |  |  |
| last_received_date | Last stocking date | date | True |  |  |  |
| last_reconciled_datetime | Last date stock was audited | timestamp | True |  |  |  |
| units_in_stock | Number of units currently in stock | int | True |  |  |  |
| lot_number | Lot location number | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## cabinet

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cabinet_id | Cabinet table id | string | False | 20 |  |  |
| facility_id | Facility table id | string | False | 20 |  |  |
| firm_id | Firm table id | string | False | 20 |  |  |
| created_by_staff_id | Staff table id | string | False | 20 |  |  |
| status | Active status for cabinet | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| cabinet_name | Cabinet name | string | True | 150 |  |  |
| facility_name | Facility name | string | True | 150 |  |  |
| color | Cabinet color | string | True | 10 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## patient_product

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| patient_product_id | Patient product table id | string | False | 20 |  |  |
| stock_id | Stock table id | string | False | 20 |  |  |
| seller_staff_id | Seller's Staff table id | string | True | 20 |  |  |
| removed_by_staff_id | Staff table id for staff that removed product from stock | string | True | 20 |  |  |
| transfer_to_cabinet_id | If transaction was a transfer then Staff table ID of transferring staff | string | True | 20 |  |  |
| product_id | Product table id | string | False | 20 |  |  |
| product_name | Product name | string | True | 100 |  |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| product_sku | Product sku | string | True | 100 |  |  |
| product_description | Product description | string | True | 300 |  |  |
| is_taxable | Product is taxable flag | boolean | True |  |  |  |
| price | Product price | double | True |  |  |  |
| units | Number of product units purchased | double | True |  |  |  |
| unit_charge | Charge per unit for services rendered | double | True |  |  |  |
| units_other | Number of product units not purchase | double | True |  |  |  |
| units_other_reason | Reason for other product unit count | string | True | 50 | ADD_STOCK BREAKAGE COST_ADJUSTMENT DECLINED EXPIRED FREE_PRODUCT INITIAL_STOCK INPUT_ERROR LOT_EXP_EDIT MANUAL_ADJUSTMENT_NEGATIVE MANUAL_ADJUSTMENT_POSTIVE MANUAL_COUNT_ADJUSTMENT PRODUCT_FOR_OFFICE_USE RETURNED_TO_INVENTORY RETURNED_AS_INITIAL_STOCK RETURNED_TO_VENDOR TRANSFER WASTE |  |
| frequency | frequency | string | True | 50 |  |  |
| priority_of_use | Product usage priority | string | True | 20 | PRIORITY_20 PRIORITY_30 PRIORITY_50 PRIORITY_70 PRIORITY_80 |  |
| removed | Whether product was removed from order | boolean | True |  | Yes: True No: False |  |
| removed_datetime | Removed datetime | timestamp | True |  |  |  |
| removed_reason | Reason product was removed from order | string | True | 20 | ALT_PRODUCT DECLINED CHARGE_VOIDED COST OUT_OF_STOCK UNKNOWN REFUSED |  |
| removed_reason_notes | Additional removed reason notes | string | True | 100 |  |  |
| new_exp_date | New expiration date | date | True |  |  |  |
| charge_created | Whether charge was created for product | boolean | True |  |  |  |
| directions | Product usage directions | string | True | 4000 |  |  |
| comments | Additional comments | string | True | 300 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## manufacturer

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| manufacturer_id | Manufacturer table id | string | False | 20 |  |  |
| firm_id | Firm table id | string | False | 20 |  |  |
| created_by_staff_id | Staff table id | string | True | 20 |  |  |
| manufacturer_name | Manufacturer name | string | True | 100 |  |  |
| manufacturer_description | Manufacturer description | string | True | 300 |  |  |
| status | Active status for manufacturer | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## product_category

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| product_category_id | product_category table id | string | False | 20 |  |  |
| firm_id | Firm table id | string | False | 20 |  |  |
| created_by_staff_id | Staff table id | string | False | 20 |  |  |
| product_category_name | Product category name | string | True | 100 |  |  |
| product_category_description | Product category description | string | True | 300 |  |  |
| status | Active status for product category | boolean | True |  | ACTIVE: True INACTIVE: False |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_id | package table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| default_location_id | facility table id (default) | string | True | 20 |  |  |
| default_fee_schedule_id | fee_schedule table id (default) | string | True | 20 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| package_description | Package description | string | True | 255 |  |  |
| package_status | Package status | string | True | 20 | ACTIVE INACTIVE |  |
| package_discount_reason | Package discount reason | string | True | 30 | OTHER PACKAGES PROMOTIONAL PROFESSIONAL_COURTESY CUSTOM_DISCOUNT |  |
| package_pricing_type | Package pricing type | string | True | 30 | INDIVIDUAL_BY_AMOUNT INDIVIDUAL_BY_PERCENTAGE TOTAL_PACKAGE |  |
| package_expiration_days | Number of days until the package expires after purchase | int | True |  |  |  |
| package_total_units | Number of units (products) within package. | double | True |  |  |  |
| package_total_amount | Total cost of units (products) within package. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_item

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_item_id | package_item table id | string | False | 20 |  |  |
| package_id | package table id | string | False | 20 |  |  |
| product_id | product table id | string | True | 20 |  |  |
| custom_code_id | custom_code table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| package_item_type | Package item type | string | True | 20 | CPT CUSTOM_CHARGE CUSTOM_CODE INVENTORY_PRODUCT LEGACY_PRODUCT |  |
| package_item_description | Package item description | string | True | 255 |  |  |
| package_item_units | For given item, count of that item within package | double | True |  |  |  |
| package_item_price_per_unit | For given item, cost for one (1) of that item | double | True |  |  |  |
| package_item_visible | Is package item currently visible. | boolean | True |  |  |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or inventory product description. | string | True | 500 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_location

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_location_id | package_location table id | string | False | 20 |  |  |
| package_id | package table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_sale

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_sale_id | package_sale table id | string | False | 20 |  |  |
| package_id | package table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| financial_category_id | financial_category table id | string | True | 20 |  |  |
| sold_by_staff_id | staff table id | string | True | 20 |  |  |
| void_by_id | staff table id | string | True | 20 |  |  |
| expiration_date_modified_by_id | staff table id to identify the user who modified the expiration date of the package | string | True | 20 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| package_description | Package description | string | True | 255 |  |  |
| quantity_remaining | Unused package items quantity remaining. | double | True |  |  |  |
| package_status | Package status | string | True | 20 | ACTIVE INACTIVE |  |
| void_status | Package void status | string | True | 20 | VOIDED PARTIAL_VOID |  |
| package_discount_reason | Package discount reason | string | True | 30 | OTHER PACKAGES PROMOTIONAL PROFESSIONAL_COURTESY CUSTOM_DISCOUNT |  |
| custom_discount_reason | Package sale custom discount reason. | string | True | 50 |  |  |
| package_notes | Package notes | string | True | 255 |  |  |
| package_tax_rate_local | Local Tax Rate | double | True |  |  |  |
| package_tax_rate_state | State Tax Rate | double | True |  |  |  |
| package_total_amount | Total amount charged | double | True |  |  |  |
| package_allocated_amount | Total amount of payments allocated | double | True |  |  |  |
| package_collected_amount | Total amount of payments collected | double | True |  |  |  |
| has_voided_items | Flag indicating item has been voided in this package. | boolean | True |  |  |  |
| void_date | Date voided | timestamp | True |  |  |  |
| void_date_ld | Localized date of void | date | True |  |  |  |
| expiration_date | Date of expiration | date | True |  |  |  |
| expiration_date_modified_on | Date when the expiration date was modified. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_item_sale

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_item_sale_id | package_item_sale table id | string | False | 20 |  |  |
| package_sale_id | package_sale table id | string | False | 20 |  |  |
| product_id | product table id | string | True | 20 |  |  |
| package_id | package table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| custom_code_id | custom_code table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| financial_category_id | financial_category table id | string | True | 20 |  |  |
| sold_by_staff_id | staff table id | string | True | 20 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| package_description | Package description | string | True | 255 |  |  |
| package_status | Package status | string | True | 10 | ACTIVE INACTIVE |  |
| package_discount_reason | Package Discount Reason | string | True | 30 | OTHER PACKAGES PROMOTIONAL PROFESSIONAL_COURTESY CUSTOM_DISCOUNT |  |
| package_notes | Package notes | string | True | 255 |  |  |
| package_item_type | Package item type | string | True | 20 | CPT CUSTOM_CHARGE CUSTOM_CODE INVENTORY_PRODUCT LEGACY_PRODUCT |  |
| package_item_description | Package item description | string | True | 255 |  |  |
| package_item_units | For given item, count of that item in patient package | double | True |  |  |  |
| package_item_price_per_unit | For given item, cost for one (1) of those items | double | True |  |  |  |
| package_tax_rate_local | Local tax rate | double | True |  |  |  |
| package_tax_rate_state | State tax rate | double | True |  |  |  |
| package_item_tax_amount | For given item, total amount of tax for that item in patient package | double | True |  |  |  |
| package_item_total_amount | For given item, total amount for that item in patient package | double | True |  |  |  |
| package_item_remaining_units | For given item, count of items in patient package that are unused | double | True |  |  |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or inventory product description. | string | True | 500 |  |  |
| financial_category | Financial category name. | string | True | 255 |  |  |
| status | Package item sale status | string | True | 20 | CHARGED VOIDED |  |
| void_date_ld | Localized date for when the package item was voided. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_item_sale_utilization

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_item_sale_utilization_id | package_item_sale_utilization table id | string | False | 20 |  |  |
| package_item_sale_id | package_item_sale table id | string | False | 20 |  |  |
| package_sale_id | package_sale table id | string | False | 20 |  |  |
| product_id | product table id | string | True | 20 |  |  |
| package_id | package table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| facility_id | facility table id (facility at which the package item was utilized) | string | False | 20 |  |  |
| package_item_sale_facility_id | facility table id (facility at which the package item was purchased) | string | False | 20 |  |  |
| business_unit_id | business_unit table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| division_id | division table id | string | True | 20 |  |  |
| custom_code_id | custom_code table id | string | True | 20 |  |  |
| custom_non_bill_code_id | custom_non_bill_code table id | string | True | 20 |  |  |
| financial_category_id | financial_category table id | string | True | 20 |  |  |
| sold_by_staff_id | staff table id | string | True | 20 |  |  |
| charge_link_key | Linking key between package_item_sale_utilization and charges. | string | True | 20 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| package_description | Package description | string | True | 255 |  |  |
| package_status | Package status | string | True | 10 | ACTIVE INACTIVE |  |
| package_discount_reason | Package Discount Reason | string | True | 30 | OTHER PACKAGES PROMOTIONAL PROFESSIONAL_COURTESY CUSTOM_DISCOUNT |  |
| package_notes | Package notes | string | True | 255 |  |  |
| package_item_type | Package item type | string | True | 20 | CPT CUSTOM_CHARGE CUSTOM_CODE INVENTORY_PRODUCT LEGACY_PRODUCT |  |
| package_item_description | Package item description | string | True | 255 |  |  |
| package_item_units | For given item, count of that item in patient package | double | True |  |  |  |
| package_item_price_per_unit | For given item, cost for one (1) of those items | double | True |  |  |  |
| package_tax_rate_local | Local tax rate | double | True |  |  |  |
| package_tax_rate_state | State tax rate | double | True |  |  |  |
| package_item_tax_amount | For given item, total amount of tax for that item in patient package | double | True |  |  |  |
| package_item_total_amount | For given item, total amount for that item in patient package | double | True |  |  |  |
| package_item_remaining_units | For given item, count of items in patient package that are unused | double | True |  |  |  |
| cpt_product | The CPT/HCPCS procedure code for the bill charge or category for a non-bill charge, or inventory product code | string | True | 100 |  |  |
| cpt_product_description | The CPT/HCPCS procedure code or category description for the bill charge or non-bill charge, or inventory product description. | string | True | 500 |  |  |
| financial_category | Financial category name. | string | True | 255 |  |  |
| status | Package item sale status | string | True | 20 | CHARGED VOIDED |  |
| void_date_ld | Localized date for when the package item was voided. | date | True |  |  |  |
| package_item_sale_date_created | Date on which the package item was sold | timestamp | True |  |  |  |
| package_item_sale_utilization_units | The number of package items utilized. | double | True |  |  |  |
| package_item_sale_utilization_visible | If True, the package_item_sale_utilization is visible. | boolean | True |  |  |  |
| date_created | Date on which the package item sale was utilized | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_sale_to_bill

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_sale_to_bill_id | package_sale_to_bill table id | string | False | 20 |  |  |
| package_sale_id | package_sale table id | string | False | 20 |  |  |
| bill_id | bill table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| sold_by_id | staff table id | string | True | 20 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| package_description | Package description | string | True | 255 |  |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## package_sale_to_appointment

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| package_sale_to_appointment_id | package_sale_to_appointment table id | string | False | 20 |  |  |
| package_sale_id | package_sale table id | string | False | 20 |  |  |
| appointment_id | appointment table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| package_name | Package name | string | True | 50 |  |  |
| package_description | Package description | string | True | 255 |  |  |
| package_sale_date_created | Date on which the package was sold. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## stock_transaction

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| stock_transaction_id | stock_transaction table id | string | False | 20 |  |  |
| stock_id | stock table id | string | False | 20 |  |  |
| product_id | product table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| cabinet_id | cabinet table id | string | False | 20 |  |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| product_order_number | Product order identifier. If stock transaction is associated with a product order | string | True | 100 |  |  |
| type | Transaction type | string | True | 50 |  |  |
| transaction_note | Transaction note | string | True | 2000 |  |  |
| lot_number | Lot location number | string | True | 255 |  |  |
| expiration_date | Product expiration date | date | True |  |  |  |
| cabinet_name | Name of cabinet with a transaction | string | True | 150 |  |  |
| units_changed | Count of units changed by transaction | int | True |  |  |  |
| new_units | count of units after transaction | int | True |  |  |  |
| unit_price | Price of unit | decimal(10,2) | True |  |  |  |
| sequence_number | Sequence of transaction | int | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## stock_reconciliation

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| stock_reconciliation_id | stock_reconciliation table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| stock_transaction_id | stock_transaction table id | string | True | 20 |  |  |
| reconciliation_created_by_staff_id | staff table id | string | False | 20 |  |  |
| cabinet_audit_completed_by_staff_id | staff table id | string | True | 20 |  |  |
| audit_completed_by_staff_id | staff table id | string | True | 20 |  |  |
| reconciliation_finalized_by_staff_id | staff table id | string | True | 20 |  |  |
| cabinet_id | cabinet table id | string | False | 20 |  |  |
| product_id | product table id | string | False | 20 |  |  |
| stock_id | stock table id | string | False | 20 |  |  |
| reconciliation_number | Unique identifier to group by reconciliation | string | True | 20 |  |  |
| reconciliation_status | Status of reconciliation | string | True | 20 | IN_PROGRESS PENDING READY_TO_RECONCILE RECONCILED |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| snapshot_units | Count of units on the snapshot date/time | decimal(10,2) | True |  |  |  |
| audit_unit_count | Audited count of units | decimal(10,2) | True |  |  |  |
| audit_unit_difference | audit units - snapshot units | decimal(10,2) | True |  |  |  |
| post_adjustment_unit_count | Count of units after adjustment | decimal(10,2) | True |  |  |  |
| reason_for_adjustment | Reason for adjustment | string | True | 50 | BREAKAGE DECLINED EXPIRED INPUT_ERROR MANUAL_ADJUSTMENT_NEGATIVE MANUAL_ADJUSTMENT_POSTIVE RETURNED_TO_INVENTORY RETURNED_TO_VENDOR WASTE |  |
| stock_adjusted_note | Note for stock adjustment | string | True | -1 |  |  |
| cabinet_note | Note for cabinet | string | True | -1 |  |  |
| cabinet_audit_completed_datetime | Cabinet audit completed date/time | timestamp | True |  |  |  |
| audit_completed_datetime | Audit completed date/time | timestamp | True |  |  |  |
| reconciliation_finalized_datetime | Reconciliation finalized date/time | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cabinet_preference

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cabinet_preference_id | cabinet_preference table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| cabinet_id | cabinet table id | string | False | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## product_facility_pricing

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| product_facility_pricing_id | product_facility_pricing table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| product_id | product table id | string | False | 20 |  |  |
| units_per_package | Firm Admin -> Inventory -> Setup -> Products -> Edit Pricing | double | True |  |  |  |
| facility_package_price | Facility set price of package | decimal(10,2) | True |  |  |  |
| facility_price_per_unit | Facility set price per unit | decimal(10,2) | True |  |  |  |
| facility_is_taxable | Facility set taxable status | boolean | True |  |  |  |
| base_package_price | Base package price | decimal(10,2) | True |  |  |  |
| base_price_per_unit | Base price per unit | decimal(10,2) | True |  |  |  |
| base_is_taxable | Base taxable status | boolean | True |  |  |  |
| price_floor | Lowest allowable sale price per unit | decimal(10,2) | True |  |  |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## product_vendor

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| product_vendor_id | product_vendor table id | string | False | 20 |  |  |
| firm_id | firm table id | string | False | 20 |  |  |
| name | Name of vendor | string | True | 255 |  |  |
| description | Description of vendor | string | True | 255 |  |  |
| active | Active vendor | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## product_order_item

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| product_order_item_id | product_order_item table id | string | False | 20 |  |  |
| facility_id | facility table id | string | False | 20 |  |  |
| product_id | product table id | string | False | 20 |  |  |
| product_vendor_id | product_vendor table id | string | True | 20 |  |  |
| ordered_by_staff_id | staff table id | string | True | 20 |  |  |
| approved_by_staff_id | staff table id | string | True | 20 |  |  |
| closed_by_staff_id | staff table id | string | True | 20 |  |  |
| order_number | Order identifier | string | True | 100 |  |  |
| order_status | Status of order | string | True | 25 | APPROVED CLOSED_AS_INCOMPLETE CLOSED_NOT_APPROVED FULLY_STOCKED PARTIALLY_STOCKED PENDING |  |
| product_name | Product name | string | True | 100 |  |  |
| product_code | Unique product code used in code category and bill lookups | string | True | 20 |  |  |
| bar_code | Product bar code | string | True | 100 |  |  |
| package_type | Type of packaging | string | True | 20 |  |  |
| units_per_package | Units per package | double | True |  |  |  |
| units_ordered | Units ordered | double | True |  |  |  |
| packages_ordered | Packages ordered | double | True |  |  |  |
| order_cost | Cost of order | decimal(10,2) | True |  |  |  |
| unit_cost | Cost per unit | decimal(10,2) | True |  |  |  |
| package_cost | Cost per package | decimal(10,2) | True |  |  |  |
| lot_number | Lot location number | string | True | 255 |  |  |
| ordered_datetime | Date/time ordered | timestamp | True |  |  |  |
| approved_date | Date order approved | date | True |  |  |  |
| closed_date | Date/time order closed | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
