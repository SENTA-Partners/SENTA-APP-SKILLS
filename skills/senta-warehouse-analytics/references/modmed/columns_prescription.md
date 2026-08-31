# Column Dictionary: Prescription (394 columns)


## rx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| rx_id | rx table id | string | False | 64 |  |  |
| patient_id | patient record identifier | string | False | 64 |  |  |
| written_by_id | staff table id | string | True | 64 | Staff member that wrote the prescription |  |
| facility_id | facility table id | string | True | 64 | Facility the rx was written from |  |
| diagnosis_id | diagnosis table id | string | True | 64 | Link to diagnosis if written from visit, NULL if written outside visit |  |
| compound_medication_id | compound_medication table id | string | True | 64 |  |  |
| written_on_date | Date rx was written | timestamp | True |  |  |  |
| drug_name | Dispensable drug name including dose form, route, and strength | string | True | 200 | Based on FirstDataBank (FDB) |  |
| short_name | Brand/generic name. | string | True | 35 | Based on FirstDataBank (FDB) |  |
| generic_name | Generic name of drug, may be same as drug_name if generic was prescribed. | string | True | 50 | Based on FirstDataBank (FDB) |  |
| is_generic | If the medication prescribed is a generic medication | boolean | True |  |  |  |
| nametypecode | Medication type | string | True | 1 | 1: Brand 2: Generic |  |
| medid | First Databank Medication Identifier. | int | True |  | Based on FirstDataBank (FDB) |  |
| ndc | Suggested NDC code sent to the pharmacy, not guaranteed to be the actual NDC that is filled. | string | True | 13 |  |  |
| dose_form | Dose form of the medication. May have a null value. | string | True | 100 | tablet, powder, capsule, etc. Based on FirstDataBank (FDB) |  |
| route | Route of the medication. May have a null value. | string | True | 50 | topical, oral, etc. Based on FirstDataBank (FDB) |  |
| strength | Strength of the medication. May have a null value. | string | True | 25 | Based on FirstDataBank (FDB) |  |
| strength_units | Units of measure for the strength field. May have a null value. | string | True | 25 | mg, %, etc. Based on FirstDataBank (FDB) |  |
| quantity | Quantity to dispense. | double | True |  |  |  |
| quantity_units | Units of measure for the quantity field. May have a null value. | string | True | 80 | Capsule, Bottle, Gram, Syringe, Tablet, etc. |  |
| refills | Number of refills for the prescription. | int | True |  |  |  |
| dose | Dose | string | True | 50 |  |  |
| frequency | Frequency | string | True | 100 |  |  |
| indication | Indication | string | True | 100 |  |  |
| package_size | Size of the packaging | string | True | 50 | Based on FirstDataBank (FDB) |  |
| package_type | Type of packaging. May have a null value. | string | True | 50 | Bottle, Tube, etc. Based on FirstDataBank (FDB) |  |
| package_size_units | Units of measure for package_size. May have a null value. | string | True | 50 | Grams, Milliliters, etc. Based on FirstDataBank (FDB) |  |
| sig | Sig | string | True | -1 |  |  |
| note | Note to pharmacist | string | True | -1 |  |  |
| allow_substitutions | Allow substitutions | boolean | True |  |  |  |
| status | Status of the rx. NOTE: when archiving a visit with an rx, the status of the rx will be the value it had when the visit was archived. | string | True | 30 | PENDING: rx not sent PRINTED: rx printed ERX: eRX sent VOIDED: pending rx voided (not sent) CANCELED: eRx cancelled |  |
| void_reason | Reason for voiding the pending rx | string | True | 255 |  |  |
| pharmacy_ncpdpid | National Council for Prescription Drug Programs ID. NULL if surescripts_pharmacy is False | string | True | 7 |  |  |
| pharmacy_name | Pharmacy Name | string | True | 100 |  |  |
| pharmacy_npi | National Provider Identifier | string | True | 35 |  |  |
| days_supply | Number of days for the prescription. | int | True |  |  |  |
| dea_class | The DEA class of the highest controlled substance of the compound ingredients. One being the highest. | int | True |  |  |  |
| location | Location of the prescription. | string | True | 10 |  |  |
| plan_payer_name | Name of plan payer | string | True | 60 |  |  |
| rxn_term_type | Term Type | string | True | 20 |  |  |
| side_effects | List of potential side effects | string | True | -1 |  |  |
| from_mobile | If True, prescription came from mobile device. | boolean | True |  |  |  |
| prior_authorization_required | If true, prior authorization is required for prescription. | boolean | True |  |  |  |
| earliest_fill_date | Earliest fill date. | date | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## compound_medication

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| compound_medication_id | compound_medication table id | string | False | 64 |  |  |
| firm_id | firm table id | string | True | 64 | Firm the compound medication was written from. |  |
| original_compound_medication_id | compound_medication table id | string | True | 64 | Reference to the original compound medication from which this record is created. |  |
| compound_medication_name | The name of the compound medication. | string | True | 200 |  |  |
| compound_drug_name | The drug name of the Compound Med. | string | True | -1 | Based on FirstDataBank (FDB) |  |
| route | Route of the compound medication. May have a null value. | string | True | 50 | topical, oral, etc. Based on FirstDataBank (FDB) |  |
| dose_form | Dose of the compound medication. | string | True | 100 | Cream, solution, capsule, etc. |  |
| version | The version of the compound medication. Default 1. | bigint | True |  |  |  |
| dea_class | The DEA class of the highest controlled substance of the compound ingredients. One being the highest. | int | True |  |  |  |
| archived | Flagged if the Compound Med is archived. | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## glasses_rx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| glasses_rx_id | glasses_rx table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 | NULL if rx written outside of visit |  |
| date_recorded | Date originally recorded. Rx may be modified after this date. | timestamp | True |  |  |  |
| active | If the rx is active | boolean | True |  |  |  |
| eyeglass_usage | Eyeglass Usage | string | True | 255 | See Appendix E |  |
| underlying_condition_od | (Prisms/PDs) Underlying condition. If not null, all other OD refraction values are null. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | (Prisms/PDs) Underlying condition. If not null, all other OS refraction values are null. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| sphere_od | (Rx Details) Sphere | double | True |  |  |  |
| sphere_os | (Rx Details) Sphere | double | True |  |  |  |
| cylinder_od | (Rx Details) Cylinder | double | True |  |  |  |
| cylinder_os | (Rx Details) Cylinder | double | True |  |  |  |
| axis_od | (Rx Details) Axis | int | True |  |  |  |
| axis_os | (Rx Details) Axis | int | True |  |  |  |
| add_od | (Rx Details) Add | double | True |  |  |  |
| add_os | (Rx Details) Add | double | True |  |  |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 30 | See Appendix F |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| start_date_od | (Rx Details) Start Date | timestamp | True |  |  |  |
| start_date_os | (Rx Details) Start Date | timestamp | True |  |  |  |
| expiration_date_od | (Rx Details) Expiration Date | timestamp | True |  |  |  |
| expiration_date_os | (Rx Details) Expiration Date | timestamp | True |  |  |  |
| horizontal_prism_od | (Prisms/PDs) HPrism | double | True |  |  |  |
| horizontal_prism_os | (Prisms/PDs) HPrism | double | True |  |  |  |
| horizontal_base_od | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| horizontal_base_os | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| vertical_prism_od | (Prisms/PDs) VPrism | double | True |  |  |  |
| vertical_prism_os | (Prisms/PDs) VPrism | double | True |  |  |  |
| vertical_base_od | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| vertical_base_os | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| pd_distance_od | Pupillary distance - Distance OD | double | True |  |  |  |
| pd_distance_os | Pupillary distance - Distance OS | double | True |  |  |  |
| pd_near_od | Pupillary distance - Near OD | double | True |  |  |  |
| pd_near_os | Pupillary distance - Near OS | double | True |  |  |  |
| prism_other_od | (Prisms/PDs) Other | string | True | 255 |  |  |
| prism_other_os | (Prisms/PDs) Other | string | True | 255 |  |  |
| seg_hgt_od | SEG HGT | double | True |  |  |  |
| seg_hgt_os | SEG HGT | double | True |  |  |  |
| oc_hgt_od | OC HGT | double | True |  |  |  |
| oc_hgt_os | OC HGT | double | True |  |  |  |
| dec_dist_od | DEC Dist | double | True |  |  |  |
| dec_dist_os | DEC Dist | double | True |  |  |  |
| inset_od | INSET | double | True |  |  |  |
| inset_os | INSET | double | True |  |  |  |
| total_dec_od | TOTAL DEC | double | True |  |  |  |
| total_dec_os | TOTAL DEC | double | True |  |  |  |
| pd_distance_ou | Binocular Pupillary Distance - Distance | double | True |  |  |  |
| pd_near_ou | Binocular Pupillary Distance - Near | double | True |  |  |  |
| qp_uv400 | (Quick Preferences) UV400 | boolean | True |  |  |  |
| qp_anti_reflective | (Quick Preferences) Anti-Reflective Coating | boolean | True |  |  |  |
| qp_single_vision | (Quick Preferences) SIngle Vision | boolean | True |  |  |  |
| qp_bifocal | (Quick Preferences) Bifocal | boolean | True |  |  |  |
| qp_progressives | (Quick Preferences) Progressives | boolean | True |  |  |  |
| qp_transition | (Quick Preferences) Transition | boolean | True |  |  |  |
| qp_polarized | (Quick Preferences) Polarized | boolean | True |  |  |  |
| qp_sunglasses | (Quick Preferences) Sunglasses | boolean | True |  |  |  |
| qp_slab_off | (Quick Preferences) Slab Off | boolean | True |  |  |  |
| qp_high_index | (Quick Preferences) High Index | boolean | True |  |  |  |
| qp_safety_lenses | (Quick Preferences) Safety Lenses | boolean | True |  |  |  |
| qp_other | (Quick Preferences) Other Notes | string | True | 255 |  |  |
| lens_style | (Lens Details) Lens Style | string | True | 100 | ASOHERIC_SINGLE_VISION DEFINITY DEFINITY_SHORT ESS_ACCOLADE ESS_IDEAL ESS_IDEAL_ADVANCED ESS_IDEAL_SPORT ESS_NATURAL ESS_SV_SPORT FLAT_TOP_25 FLAT_TOP_28 FLAT_TOP_35 FLAT_TOP_360 KBCO_WRAP_EOS KBCO_WRAP_SV KODAK_CONCISE KODAK_PRECISE NONE OTHER SINGLE_VISION SV360 UNITY_RELIEVE UNITY_SVX UNITY_SVXTRA UNITY_VIA UNITY_VIA_ELITE UNITY_VIA_OFFICEPRO UNITY_VIA_PLUS VLX_COMFORT VLX_COMFORT_360 VLX_ELLIPSE VLX_ELLIPSE_360 VLX_PANAMIC VLX_PHYSIO VLX_PHYSIO_360 VLX_PHYSIO_ENHANCED VLX_PHYSIO_SHORT VLX_PHYSIO_SHORT_360 VLX_SPORT VLX_SPORT X28 X35 YOUNGER_IMAGE UNITY_VIA_MOBILE |  |
| lens_style_other | (Quick Preferences) Other Notes | string | True | 100 |  |  |
| lens_material | (Lens Details) Lens Material | string | True | 100 | THIN_AND_LITE_174 THIN_AND_LITE_167 THIN_AND_LITE_160 HI_INDEX UNLTRA_LITE_POLY LITE_STYLE_POLY LITE_STYLE_ESS_JR TRIVEX CR_PLASTIC OTHER NONE |  |
| lens_material_other | (Quick Preferences) Other Notes | string | True | 255 |  |  |
| lens_coating | (Lens Details) Lens Coating | string | True | 100 | BKSDE_ONLY CZL_AVANCE_SCTH_GRD CZL_ALIZE CRIZAL CRIZAL_SUN CRIZAL_SUN_MIRROR NONE OTHER SHARP_VIEW TECHSHIELD TECHSHIELD_BLUE TECHSHIELD_ELITE TECHSHIELD_PLUS |  |
| lens_coating_other | (Quick Preferences) Other Notes | string | True | 100 |  |  |
| lens_tint | (Lens Details) Lens Tint | string | True | 100 | NONE OTHER SUNSYNC SUNSYNC_DRIVE_XT SUNSYNC_ELITE SUNSYNC_ELITE_XT TRANSITIONS_BROWN TRANSITIONS_GRAY XPERIO_POLAR_BROWN XPERIO_POLAR_G15 XPERIO_POLAR_GRAY |  |
| lens_tint_other | (Quick Preferences) Other Notes | string | True | 100 |  |  |
| color | (Lens Details) Color. May have a null value. | string | True | 100 | GRAY GREEN BROWN AMBER ROSE RED YELLOW ORANGE OTHER NONE |  |
| color_solid | (Lens Details) Color Solid % | int | True |  |  |  |
| color_gradient | (Lens Details) Color Gradient % | int | True |  |  |  |
| eye_size | (Lens Details) Glasses Eye Size | double | True |  |  |  |
| distance_between_lenses | (Lens Details) Distance Between Lenses | double | True |  |  |  |
| top_to_bottom | (Lens Details) Top to Bottom (B.) | double | True |  |  |  |
| effective_diameter | (Lens Details) Effective Diameter (E.D.) | double | True |  |  |  |
| lens_mirror | (Lens Details) Mirror | boolean | True |  |  |  |
| lens_uv | (Lens Details) UV | boolean | True |  |  |  |
| lens_uncut | (Lens Details) Uncut | boolean | True |  |  |  |
| lens_safety | (Lens Details) Safety | boolean | True |  |  |  |
| lens_polish_edges | (Lens Details) Polish Edges | boolean | True |  |  |  |
| lens_knife_edge | (Lens Details) Knife Edge | boolean | True |  |  |  |
| lens_tap | (Lens Details) TAP | boolean | True |  |  |  |
| lens_options_other | (Lens Details) Other | string | True | 255 |  |  |
| frame_name | Glasses Frame Name | string | True | 100 |  |  |
| frame_manufacturer_name | Glasses Frames Manufacturer Name | string | True | 100 |  |  |
| frame_color | Glasses Frame Color | string | True | 100 |  |  |
| temple_length | (Frame Details) Glasses Temple Length | double | True |  |  |  |
| frame_zyi | (Frame Details) ZYI | boolean | True |  |  |  |
| frame_metal | (Frame Details) Metal | boolean | True |  |  |  |
| frame_grooved | (Frame Details) Grooved | boolean | True |  |  |  |
| frame_drilled | (Frame Details) Drilled | boolean | True |  |  |  |
| frame_to_come | (Frame Details) Frame to come | boolean | True |  |  |  |
| frame_supply | (Frame Details) Supply | boolean | True |  |  |  |
| frame_edge_only | (Frame Details) Edge Only | boolean | True |  |  |  |
| frame_pattern_enclosed_only | (Frame Details) Pattern Enclosed Only | boolean | True |  |  |  |
| frame_circumference | (Frame Details) Circumference | double | True |  |  |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| print_notes | Display notes on Rx printout | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## contacts_rx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| contacts_rx_id | contacts_rx table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 | NULL if rx written outside of visit |  |
| date_recorded | Date originally recorded. Rx may be modified after this date. | timestamp | True |  |  |  |
| active | If the rx is active | boolean | True |  |  |  |
| contacts_usage | Contact Lens Usage | string | True | 255 | See Appendix E |  |
| status | Status. May have a null value. | string | True | 255 | DISPENSED DISPENSED_PATIENT_CAN_CONFIRM DISPENSED_SUCCESSFUL DISPENSED_UNSUCCESSFUL FINAL ORDER_TRIAL ORDER_TRIAL_NEEDS_FITTING_DOCTOR ORDER_TRIAL_NEEDS_FITTING_STAFF ORDER_TRIAL_PATIENT_CAN_CONFIRM SEE_NOTES |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| print_notes | Display notes on Rx printout | boolean | True |  |  |  |
| fitting_type | (Contact Lens Regimen) Contact Lens Fitting Type. May have a null value. | string | True | 50 | NEW FOLLOW_UP REFIT NONE |  |
| wearing_schedule | (Contact Lens Regimen) Wearing Schedule. May have a null value. | string | True | 30 | AS_NEEDED ANNUALLY DAILY DIAGNOSTIC_LENSES EXTENDED MONTHLY RELIABLE SEE_SPECIAL_INSTRUCTIONS TWO_WEEKS WEEKLY |  |
| replenishment | (Contact Lens Regimen) Replenishment. May have a null value. | string | True | 30 | ANNUALLY AS_NEEDED DAILY DIAGNOSTIC MONTHLY SEE_SPECIAL_INSTRUCTIONS SIX_MONTHS THREE_MONTHS TWO_WEEKS WEEKLY |  |
| disinfecting | (Contact Lens Regimen) Disinfecting. May have a null value. | string | True | 30 | AQUIFY BIOTRUE BLINK_REVITALENS BOSTON_ADVANCE BOSTON_ORIGINAL BOSTON_SIMPLUS CLEAR_CARE CLEAR_CARE_HYDRAGLYDE LOBOB_OPTIMUM LOBOB_OPTIMUM_CDS LOBOB_OPTIMUM_ESC LOBOB_SOF_PRO_2 MENICON_MENICARE_GP_CDS MENICON_MENICARE_GP_WRW MENICON_PROGENT NONE OPTIFREE OPTIFREE_GP OPTIFREE_PUREMOIST OPTIFREE_REPLENISH OTHER PEROXICARE RENU RGP_NONE RGP_SEE_SPECIAL_INSTRUCTIONS RGP_STORE_BRAND SAUFLON SEE_SPECIAL_INSTRUCTIONS STORE_BRAND UNIQUE_PH |  |
| underlying_condition_od | Underlying condition. If not null, all OD refraction values are null (not including over refraction). May have a null value. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | Underlying condition. If not null, all OS refraction values are null (not including over refraction). May have a null value. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| start_date_od | Start Date OD | timestamp | True |  |  |  |
| start_date_os | Start Date OS | timestamp | True |  |  |  |
| expiration_date_od | Expiration Date OD | timestamp | True |  |  |  |
| expiration_date_os | Expiration Date OS | timestamp | True |  |  |  |
| lens_manufacturer_od | Contact lens manufacturer OD | string | True | 100 | Based on ABB product database or free-text override |  |
| lens_manufacturer_os | Contact lens manufacturer OS | string | True | 100 | Based on ABB product database or free-text override |  |
| lens_brand_od | Contact lens brand OD | string | True | 100 | Based on ABB product database or free-text override |  |
| lens_brand_os | Contact lens brand OS | string | True | 100 | Based on ABB product database or free-text override |  |
| base_curve_od | Base Curve OD | double | True |  |  |  |
| base_curve_os | Base Curve OS | double | True |  |  |  |
| diameter_od | Diameter OD | double | True |  |  |  |
| diameter_os | Diameter OS | double | True |  |  |  |
| sphere_od | Sphere OD | double | True |  |  |  |
| sphere_os | Sphere OS | double | True |  |  |  |
| cylinder_od | Cylinder OD | double | True |  |  |  |
| cylinder_os | Cylinder OS | double | True |  |  |  |
| axis_od | Axis OD | int | True |  |  |  |
| axis_os | Axis OS | int | True |  |  |  |
| add_od | Add OD | double | True |  |  |  |
| add_os | Add OS | double | True |  |  |  |
| lens_color_od | Color / MF PWF OD | string | True | 100 | Based on ABB product database |  |
| lens_color_os | Color / MF PWF OS | string | True | 100 | Based on ABB product database |  |
| quantity_od | Quantity OD | int | True |  |  |  |
| quantity_os | Quantity OS | int | True |  |  |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_ou | Pinhole visual acuity DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| details_other_od | Other OD | string | True | 255 |  |  |
| details_other_os | Other OD | string | True | 255 |  |  |
| movement_od | (Assessment) Movement OD. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| movement_os | (Assessment) Movement OS. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| centration_od | (Assessment) Centration OD. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| centration_os | (Assessment) Centration OS. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| vision_od | (Assessment) Vision OD. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| vision_os | (Assessment) Vision OS. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| comfort_od | (Assessment) Comfort OD. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| comfort_os | (Assessment) Comfort OS. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| torics_right_od | (Assessment) Torics Right OD | boolean | True |  | True:ON False:OFF |  |
| torics_right_os | (Assessment) Torics Right OS | boolean | True |  | True:ON False:OFF |  |
| torics_rotated_right_od | (Assessment) Torics Rotated Right (degrees) OD | int | True |  |  |  |
| torics_rotated_right_os | (Assessment) Torics Rotated Right (degrees) OS | int | True |  |  |  |
| torics_rotated_left_od | (Assessment) Torics Rotated Left (degrees) OD | int | True |  |  |  |
| torics_rotated_left_os | (Assessment) Torics Rotated Left (degrees) OS | int | True |  |  |  |
| or_sphere_od | (Over Refraction) Sphere OD | double | True |  |  |  |
| or_sphere_os | (Over Refraction) Sphere OS | double | True |  |  |  |
| or_cylinder_od | (Over Refraction) Cylinder OD | double | True |  |  |  |
| or_cylinder_os | (Over Refraction) Cylinder OS | double | True |  |  |  |
| or_axis_od | (Over Refraction) Axis OD | int | True |  |  |  |
| or_axis_os | (Over Refraction) Axis OS | int | True |  |  |  |
| or_visual_acuity_dcc_od | (Over Refraction) Visual acuity DccOD | string | True | 20 | See Appendix F |  |
| or_visual_acuity_dcc_os | (Over Refraction) Visual acuity DccOS | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_od | (Over Refraction) Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_os | (Over Refraction) Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## rgp_contacts_rx

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| rgp_contacts_rx_id | rgp_contacts_rx table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| provider_id | staff table id | string | True | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| visit_id | visit table id | string | True | 20 | NULL if rx written outside of visit |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| active | If the rx is active | boolean | True |  |  |  |
| contacts_usage | Contact Lens Usage | string | True | 255 | See Appendix E |  |
| wearing_schedule | Wear Schedule | string | True | 30 | RELIABLE AS_NEEDED EXTENDED TWO_WEEKS DIAGNOSTIC_LENSES MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY |  |
| disinfecting | Disinfecting. May have a null value. | string | True | 30 | MENICON_MENICARE_GP_CDS RGP_NONE LOBOB_OPTIMUM_CDS UNIQUE_PH MENICON_MENICARE_GP_WRW OPTIFREE_GP MENICON_PROGENT LOBOB_OPTIMUM RGP_STORE_BRAND RGP_SEE_SPECIAL_INSTRUCTIONS OTHER BOSTON_ADVANCE BOSTON_SIMPLUS LOBOB_OPTIMUM_ESC BOSTON_ORIGINAL |  |
| dot | DOT. May have a null value. | string | True | 10 | OD OS NONE |  |
| status | Status. May have a null value. | string | True | 255 | DISPENSED DISPENSED_PATIENT_CAN_CONFIRM DISPENSED_SUCCESSFUL DISPENSED_UNSUCCESSFUL FINAL ORDER_TRIAL ORDER_TRIAL_NEEDS_FITTING_DOCTOR ORDER_TRIAL_NEEDS_FITTING_STAFF ORDER_TRIAL_PATIENT_CAN_CONFIRM SEE_NOTES |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| print_notes | Display notes on Rx printout | boolean | True |  |  |  |
| lens_manufacturer_od | Contact lens manufacturer OD | string | True | 100 | Based on ABB product database |  |
| lens_manufacturer_os | Contact lens manufacturer OS | string | True | 100 | Based on ABB product database |  |
| lens_product_od | Contact lens brand OD | string | True | 100 | Based on ABB product database |  |
| lens_product_os | Contact lens brand OS | string | True | 100 | Based on ABB product database |  |
| start_date | Start Date | timestamp | True |  |  |  |
| expiration_date | Expiration Date | timestamp | True |  |  |  |
| manual_lens_manufacturer_od | Manual entry - Contact lens manufacturer OD | string | True | 255 |  |  |
| manual_lens_manufacturer_os | Manual entry - Contact lens manufacturer OS | string | True | 255 |  |  |
| manual_lens_product_od | Manual entry - Contact lens brand OD | string | True | 255 |  |  |
| manual_lens_product_os | Manual entry - Contact lens brand OS | string | True | 255 |  |  |
| underlying_condition_od | Underlying condition. If not null, all OD refraction values are null (not including over refraction). | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | Underlying condition. If not null, all OS refraction values are null (not including over refraction). | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| rgp_type_od | RGP Type OD. May have a null value. | string | True | 30 | TRANSLATING_BIFOCAL_GP PROGRESSIVE_MULTIFOCAL_GP ASPHERIC_GP HYBRID_PROGRESSIVE CORNEAL_RESHAPING SPHERICAL_GP CUSTOM HYBRID_KERATOCONUS KERATOCONUS_GP REVERSE_GEOMETRY_GP HYBRID_SPHERE CRT SPHERE SCLERAL_GP TRIFOCAL_HYBRID_GP HYBRID_POST_SURGICAL TORIC_GP HYBRID_MULTIFOCAL BITORIC |  |
| rgp_type_os | RGP Type OS. May have a null value. | string | True | 30 | TRANSLATING_BIFOCAL_GP PROGRESSIVE_MULTIFOCAL_GP ASPHERIC_GP HYBRID_PROGRESSIVE CORNEAL_RESHAPING SPHERICAL_GP CUSTOM HYBRID_KERATOCONUS KERATOCONUS_GP REVERSE_GEOMETRY_GP HYBRID_SPHERE CRT SPHERE SCLERAL_GP TRIFOCAL_HYBRID_GP HYBRID_POST_SURGICAL TORIC_GP HYBRID_MULTIFOCAL BITORIC |  |
| manual_rgp_type_od | Manual entry - RGP Type OD | string | True | 255 |  |  |
| manual_rgp_type_os | Manual entry - RGP Type OS | string | True | 255 |  |  |
| base_curve_1_od | Base Curve OD | double | True |  |  |  |
| base_curve_1_os | Base Curve OS | double | True |  |  |  |
| base_curve_2_od | Base Curve 2 OD | double | True |  |  |  |
| base_curve_2_os | Base Curve 2 OS | double | True |  |  |  |
| diameter_od | Diameter OD | double | True |  |  |  |
| diameter_os | Diameter OS | double | True |  |  |  |
| sphere_1_od | Sphere OD | double | True |  |  |  |
| sphere_1_os | Sphere OS | double | True |  |  |  |
| sphere_2_od | Sphere 2 OD | double | True |  |  |  |
| sphere_2_os | Sphere 2 OS | double | True |  |  |  |
| cylinder_1_od | Cylinder OD | double | True |  |  |  |
| cylinder_1_os | Cylinder OS | double | True |  |  |  |
| cylinder_2_od | Cylinder 2 OD | double | True |  |  |  |
| cylinder_2_os | Cylinder 2 OS | double | True |  |  |  |
| axis_1_od | Axis OD | int | True |  |  |  |
| axis_1_os | Axis OS | int | True |  |  |  |
| axis_2_od | Axis 2 OD | int | True |  |  |  |
| axis_2_os | Axis 2 OS | int | True |  |  |  |
| pcr_1_od | Peripheral Curve Radius (PCR) OD | double | True |  |  |  |
| pcr_1_os | Peripheral Curve Radius (PCR) OS | double | True |  |  |  |
| pcw_1_od | Peripheral Curve Width (PCW) OD | double | True |  |  |  |
| pcw_1_os | Peripheral Curve Width (PCW) OS | double | True |  |  |  |
| pcr_2_od | Peripheral Curve Radius (PCR) 2 OD | double | True |  |  |  |
| pcr_2_os | Peripheral Curve Radius (PCR) 2 OS | double | True |  |  |  |
| pcw_2_od | Peripheral Curve Width (PCW) 2 OD | double | True |  |  |  |
| pcw_2_os | Peripheral Curve Width (PCW) 2 OS | double | True |  |  |  |
| pcr_3_od | Peripheral Curve Radius (PCR) 3 OD | double | True |  |  |  |
| pcr_3_os | Peripheral Curve Radius (PCR) 3 OS | double | True |  |  |  |
| pcw_3_od | Peripheral Curve Width (PCW) 3 OD | double | True |  |  |  |
| pcw_3_os | Peripheral Curve Width (PCW) 3 OS | double | True |  |  |  |
| add_od | Add OD | double | True |  |  |  |
| add_os | Add OS | double | True |  |  |  |
| prism_od | Prism OD | double | True |  |  |  |
| prism_os | Prism OS | double | True |  |  |  |
| center_thickness_od | Center Thickness OD | double | True |  |  |  |
| center_thickness_os | Center Thickness OS | double | True |  |  |  |
| edge_thickness_od | Edge Thickness OD | double | True |  |  |  |
| edge_thickness_os | Edge Thickness OS | double | True |  |  |  |
| optical_zone_od | Optical Zone OD | double | True |  |  |  |
| optical_zone_os | Optical Zone OS | double | True |  |  |  |
| segment_height_od | Segment Height OD | double | True |  |  |  |
| segment_height_os | Segment Height OS | double | True |  |  |  |
| blend_od | Blend OD. May have a null value. | string | True | 30 | LIGHT MEDIUM HEAVY |  |
| blend_os | Blend OS. May have a null value. | string | True | 30 | LIGHT MEDIUM HEAVY |  |
| material_od | Material OD | string | True | 255 |  |  |
| material_os | Material OS | string | True | 255 |  |  |
| tint_od | Tint OD. May have a null value. | string | True | 30 | AQUA BLUE CRYSTAL_BLUE MAJESTIC_BLUE BROWN GRAY GREEN RED VIOLET BABY_BLUE CHESTNUT_BROWN CLEAR TURQUOISE AQUA_ENHANCER BLUE_BLOCKER BLUE_ENHANCER BLUE_GRAY CARIBBEAN_AQUA COBALT DARK_COCOA EMERALD_GREEN EVERGREEN MIGRAINE_55 GRANITE GREEN_ENHANCER HONEY ICE_BLUE LAVENDER PECAN PISTACHIO SAPPHIRE_BLUE STORMY_GRAY TEAL |  |
| tint_os | Tint OS. May have a null value. | string | True | 30 | AQUA BLUE CRYSTAL_BLUE MAJESTIC_BLUE BROWN GRAY GREEN RED VIOLET BABY_BLUE CHESTNUT_BROWN CLEAR TURQUOISE AQUA_ENHANCER BLUE_BLOCKER BLUE_ENHANCER BLUE_GRAY CARIBBEAN_AQUA COBALT DARK_COCOA EMERALD_GREEN EVERGREEN MIGRAINE_55 GRANITE GREEN_ENHANCER HONEY ICE_BLUE LAVENDER PECAN PISTACHIO SAPPHIRE_BLUE STORMY_GRAY TEAL |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| movement_od | (Assessment) Movement OD. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| movement_os | (Assessment) Movement OS. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| centration_od | (Assessment) Centration OD. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| centration_os | (Assessment) Centration OS. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| vision_od | (Assessment) Vision OD. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| vision_os | (Assessment) Vision OS. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| comfort_od | (Assessment) Comfort OD. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| comfort_os | (Assessment) Comfort OS. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| torics_right_od | (Assessment) Torics Right OD. May have a null value. | boolean | True |  | True: ON, False: OFF |  |
| torics_right_os | (Assessment) Torics Right OS. May have a null value. | boolean | True |  | True: ON, False: OFF |  |
| torics_rotated_right_od | (Assessment) Torics Rotated Right (degrees) OD | int | True |  |  |  |
| torics_rotated_right_os | (Assessment) Torics Rotated Right (degrees) OS | int | True |  |  |  |
| torics_rotated_left_od | (Assessment) Torics Rotated Left (degrees) OD | int | True |  |  |  |
| torics_rotated_left_os | (Assessment) Torics Rotated Left (degrees) OS | int | True |  |  |  |
| or_sphere_od | (Over Refraction) Sphere OD | double | True |  |  |  |
| or_sphere_os | (Over Refraction) Sphere OS | double | True |  |  |  |
| or_cylinder_od | (Over Refraction) Cylinder OD | double | True |  |  |  |
| or_cylinder_os | (Over Refraction) Cylinder OS | double | True |  |  |  |
| or_axis_od | (Over Refraction) Axis OD | int | True |  |  |  |
| or_axis_os | (Over Refraction) Axis OS | int | True |  |  |  |
| or_visual_acuity_dcc_od | (Over Refraction) Visual acuity DccOD | string | True | 20 | See Appendix F |  |
| or_visual_acuity_dcc_os | (Over Refraction) Visual acuity DccOS | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_od | (Over Refraction) Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_os | (Over Refraction) Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## ss_prescriber

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| ss_prescriber_id | ss_prescriber table id | string | False | 64 |  |  |
| firm_id | firm table id | string | False | 64 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| staff_id | staff table id | string | True | 20 |  |  |
| staff_facility_rx_registration_id | staff_facility_rx_registration table id | string | True | 64 |  |  |
| facility_name | Facility name | string | True | 100 |  |  |
| surescripts_prescriber_identifier | Surescripts prescriber identifier associated to a user | string | True | 13 |  |  |
| prefix | Prescriber prefix | string | True | 10 |  |  |
| first_name | Prescriber first name | string | True | 35 |  |  |
| middle_name | Prescriber middle name | string | True | 35 |  |  |
| last_name | Prescriber last name | string | True | 35 |  |  |
| suffix_name | Prescriber suffix | string | True | 10 |  |  |
| npi | Prescriber NPI | string | True | 35 |  |  |
| dea | DEA Location | string | True | 35 |  |  |
| clinic_name | Clinic name | string | True | 70 |  |  |
| clinic_address_line_1 | Clinic address line 1 | string | True | 40 |  |  |
| clinic_address_line_2 | Clinic address line 2 | string | True | 40 |  |  |
| clinic_city | Clinic city | string | True | 35 |  |  |
| clinic_state | Clinic state | string | True | 2 |  |  |
| clinic_zipcode | Clinic zipcode | string | True | 11 |  |  |
| clinic_phone_primary | Clinic primary phone number | string | True | 25 |  |  |
| clinic_fax | Clinic fax | string | True | 25 |  |  |
| facility_address_line_1 | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility address line 1 | string | True | 40 |  | True |
| facility_address_line_2 | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility address line 2 | string | True | 40 |  | True |
| facility_city | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility city | string | True | 35 |  | True |
| facility_state | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility state | string | True | 2 |  | True |
| facility_zipcode | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility zipcode | string | True | 11 |  | True |
| facility_phone_primary | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility primary phone number | string | True | 25 |  | True |
| facility_fax | Deprecated and will be removed in 1.26: Field contains clinic information. Join facility table for facility fax | string | True | 25 |  | True |
| prescriber_email | email | string | True | 80 |  |  |
| prescriber_service_level_cancel | Service level cancel status. | boolean | True |  |  |  |
| prescriber_service_level_change | Service level change status. | boolean | True |  |  |  |
| prescriber_service_level_electronic_prior_auth | Service level electronic prior authorization status. | boolean | True |  |  |  |
| prescriber_service_level_new_rx | Service level new rx status. | boolean | True |  |  |  |
| prescriber_service_level_rx_fill | Service level rx fill status. | boolean | True |  |  |  |
| prescriber_service_level_rx_refill | Service level rx refill status. | boolean | True |  |  |  |
| prescriber_service_controlled_substance | Service level ControlledSubstance status. | boolean | True |  |  |  |
| active_start_time | Service level active start time. | timestamp | True |  |  |  |
| active_end_time | Service level active end time. | timestamp | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier. | string | False | 10 |  |  |

## staff_facility_rx_registration

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| staff_facility_rx_registration_id | staff_facility_rx_registration table id | string | False | 20 |  |  |
| staff_id | staff table id | string | False | 20 |  |  |
| facility_id | facility table id | string | True | 20 |  |  |
| dea_id | DEA ID | string | True | 20 |  |  |
| license_number | License Number | string | True | 20 |  |  |
| license_state | License State | string | True | 2 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |
