# Column Dictionary: Ophth Pretesting (1209 columns)


## wearing_glasses

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| wearing_glasses_id | wearing_glasses table id | string | False | 20 |  |  |
| visit_id | visit table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| eyeglass_type | Eyeglass type | string | True | 40 | null BIFOCAL BROKEN LEFT_AT_HOME NONE OTHER PROGRESSIVES SINGLE_VISION_DISTANCE SINGLE_VISION_INTERMEDIATE SINGLE_VISION_NEAR TRIFOCAL |  |
| eyeglass_usage | Eyeglass usage | string | True | 255 | See Appendix E |  |
| anti_reflective_coating | Eyeglass option (Anti-Reflective coating) | boolean | True |  |  |  |
| hi_index_lenses | Eyeglass option (Hi-Index lenses) | boolean | True |  |  |  |
| polarized | Eyeglass option (Polarized) | boolean | True |  |  |  |
| polycarbonate | Eyeglass option (Polycarbonate) | boolean | True |  |  |  |
| scratch_coating | Eyeglass option (Scratch Coating) | boolean | True |  |  |  |
| slab_off | Eyeglass option (Slab Off) | boolean | True |  |  |  |
| sunglasses | Eyeglass option (Sunglasses) | boolean | True |  |  |  |
| transition_lenses | Eyeglass option (Transition Lenses) | boolean | True |  |  |  |
| uv_coating | Eyeglass option (UV Coating) | boolean | True |  |  |  |
| eyeglass_option_other | Eyeglass option (other) | string | True | 20000 |  |  |
| pd_distance_ou | Binocular Pupillary Distance - Distance | double | True |  |  |  |
| pd_near_ou | Binocular Pupillary Distance - Near | double | True |  |  |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| underlying_condition_od | (Prisms/PDs) Underlying condition. If not null, all other OD refraction values are null. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | (Prisms/PDs) Underlying condition. If not null, all other OS refraction values are null. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| sphere_od | (Refractions) Sphere | double | True |  |  |  |
| sphere_os | (Refractions) Sphere | double | True |  |  |  |
| cylinder_od | (Refractions) Cylinder | double | True |  |  |  |
| cylinder_os | (Refractions) Cylinder | double | True |  |  |  |
| axis_od | (Refractions) Axis | int | True |  |  |  |
| axis_os | (Refractions) Axis | int | True |  |  |  |
| add_od | (Refractions) Add | double | True |  |  |  |
| add_os | (Refractions) Add | double | True |  |  |  |
| horizontal_prism_od | (Prisms/PDs) HPrism | double | True |  |  |  |
| horizontal_prism_os | (Prisms/PDs) HPrism | double | True |  |  |  |
| horizontal_base_od | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| horizontal_base_os | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| vertical_prism_od | (Prisms/PDs) VPrism | double | True |  |  |  |
| vertical_prism_os | (Prisms/PDs) VPrism | double | True |  |  |  |
| vertical_base_od | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| vertical_base_os | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| slab_off_od | (Prisms/PDs) Slab Off | boolean | True |  |  |  |
| slab_off_os | (Prisms/PDs) Slab Off | boolean | True |  |  |  |
| vertex_distance_od | (Prisms/PDs) VD | double | True |  |  |  |
| vertex_distance_os | (Prisms/PDs) VD | double | True |  |  |  |
| pd_distance_od | Pupillary distance - Distance OD | double | True |  |  |  |
| pd_distance_os | Pupillary distance - Distance OS | double | True |  |  |  |
| pd_near_od | Pupillary distance - Near OD | double | True |  |  |  |
| pd_near_os | Pupillary distance - Near OS | double | True |  |  |  |
| refraction_other_od | Refraction other OD | string | True | 255 |  |  |
| refraction_other_os | Refraction other OS | string | True | 255 |  |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_ou | Pinhole visual acuity DccOU | string | True | 20 | See Appendix F |  |
| glare_dcc_od | Glare DccOD | string | True | 20 | See Appendix F |  |
| glare_dcc_os | Glare DccOS | string | True | 20 | See Appendix F |  |
| glare_dcc_ou | Glare DccOU | string | True | 20 | See Appendix F |  |
| bat_dcc_od | Brightness acuity test DccOD | string | True | 20 | See Appendix F |  |
| bat_dcc_os | Brightness acuity test DccOS | string | True | 20 | See Appendix F |  |
| bat_dcc_ou | Brightness acuity test DccOU | string | True | 20 | See Appendix F |  |
| pam_dcc_od | Potential acuity meter DccOD | string | True | 20 | See Appendix F |  |
| pam_dcc_os | Potential acuity meter DccOS | string | True | 20 | See Appendix F |  |
| pam_dcc_ou | Potential acuity meter DccOU | string | True | 20 | See Appendix F |  |
| ram_dcc_od | Retinal acuity meter DccOD | string | True | 20 | See Appendix F |  |
| ram_dcc_os | Retinal acuity meter DccOS | string | True | 20 | See Appendix F |  |
| ram_dcc_ou | Retinal acuity meter DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_dcc_od | Visual acuity other DccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_os | Visual acuity other DccOS | string | True | 255 |  |  |
| visual_acuity_other_dcc_ou | Visual acuity other DccOU | string | True | 255 |  |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| pinhole_ncc_od | Pinhole visual acuity NccOD | string | True | 20 | See Appendix F |  |
| pinhole_ncc_os | Pinhole visual acuity NccOS | string | True | 20 | See Appendix F |  |
| pinhole_ncc_ou | Pinhole visual acuity NccOU | string | True | 20 | See Appendix F |  |
| glare_ncc_od | Glare NccOD | string | True | 20 | See Appendix F |  |
| glare_ncc_os | Glare NccOS | string | True | 20 | See Appendix F |  |
| glare_ncc_ou | Glare NccOU | string | True | 20 | See Appendix F |  |
| bat_ncc_od | Brightness acuity test NccOD | string | True | 20 | See Appendix F |  |
| bat_ncc_os | Brightness acuity test NccOS | string | True | 20 | See Appendix F |  |
| bat_ncc_ou | Brightness acuity test NccOU | string | True | 20 | See Appendix F |  |
| pam_ncc_od | Potential acuity meter NccOD | string | True | 20 | See Appendix F |  |
| pam_ncc_os | Potential acuity meter NccOS | string | True | 20 | See Appendix F |  |
| pam_ncc_ou | Potential acuity meter NccOU | string | True | 20 | See Appendix F |  |
| ram_ncc_od | Retinal acuity meter NccOD | string | True | 20 | See Appendix F |  |
| ram_ncc_os | Retinal acuity meter NccOS | string | True | 20 | See Appendix F |  |
| ram_ncc_ou | Retinal acuity meter NccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_ncc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_os | Visual acuity other NccOS | string | True | 255 |  |  |
| visual_acuity_other_ncc_ou | Visual acuity other NccOU | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## wearing_rgp_contacts

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| wearing_rgp_contacts_id | wearing_rgp_contacts table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| wearing_schedule | Wear Schedule. May have a null value. | string | True | 30 | AS_NEEDED TWO_WEEKS MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY |  |
| disinfecting | Disinfecting | string | True | 30 | MENICON_MENICARE_GP_CDS RGP_NONE LOBOB_OPTIMUM_CDS UNIQUE_PH MENICON_MENICARE_GP_WRW OPTIFREE_GP MENICON_PROGENT LOBOB_OPTIMUM RGP_STORE_BRAND RGP_SEE_SPECIAL_INSTRUCTIONS OTHER BOSTON_ADVANCE BOSTON_SIMPLUS LOBOB_OPTIMUM_ESC BOSTON_ORIGINAL |  |
| dot | DOT. May have a null value. | string | True | 10 | OD OS NONE |  |
| contacts_usage | Contacts Usage | string | True | 255 | See Appendix E |  |
| status | Status. May have a null value. | string | True | 255 | DISPENSED DISPENSED_PATIENT_CAN_CONFIRM DISPENSED_SUCCESSFUL DISPENSED_UNSUCCESSFUL FINAL ORDER_TRIAL ORDER_TRIAL_NEEDS_FITTING_DOCTOR ORDER_TRIAL_NEEDS_FITTING_STAFF ORDER_TRIAL_PATIENT_CAN_CONFIRM SEE_NOTES |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| lens_manufacturer_od | Contact lens manufacturer OD | string | True | 100 | Based on ABB product database |  |
| lens_manufacturer_os | Contact lens manufacturer OS | string | True | 100 | Based on ABB product database |  |
| lens_product_od | Contact lens brand OD | string | True | 100 | Based on ABB product database |  |
| lens_product_os | Contact lens brand OS | string | True | 100 | Based on ABB product database |  |
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

## wearing_contacts

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| wearing_contacts_id | wearing_contacts table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| bifocal | Contacts options (Bifocal) | boolean | True |  |  |  |
| monovision | Contacts options (Monovision) | boolean | True |  |  |  |
| toric | Contacts options (Toric) | boolean | True |  |  |  |
| contacts_option_other | Contacts options (other) | boolean | True |  |  |  |
| contacts_option_other_value | Contacts options (other) | string | True | 20000 |  |  |
| contacts_usage | Contacts Usage | string | True | 255 | See Appendix E |  |
| status | Status. May have a null value. | string | True | 255 | DISPENSED DISPENSED_PATIENT_CAN_CONFIRM DISPENSED_SUCCESSFUL DISPENSED_UNSUCCESSFUL FINAL ORDER_TRIAL ORDER_TRIAL_NEEDS_FITTING_DOCTOR ORDER_TRIAL_NEEDS_FITTING_STAFF ORDER_TRIAL_PATIENT_CAN_CONFIRM SEE_NOTES |  |
| wearing_schedule | (Contact Lens Regimen) Wearing Schedule. May have a null value. | string | True | 30 | AS_NEEDED TWO_WEEKS MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY |  |
| replenishment | (Contact Lens Regimen) Replenishment. May have a null value. | string | True | 30 | THREE_MONTHS AS_NEEDED TWO_WEEKS SIX_MONTHS DIAGNOSTIC MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY |  |
| disinfecting | (Contact Lens Regimen) Disinfecting. May have a null value. | string | True | 30 | CLEAR_CARE_HYDRAGLYDE AQUIFY BOSTON_ADVANCE STORE_BRAND RENU OPTIFREE SAUFLON BIOTRUE LOBOB_SOF_PRO_2 OPTIFREE_PUREMOIST BLINK_REVITALENS CLEAR_CARE NONE OPTIFREE_REPLENISH PEROXICARE SEE_SPECIAL_INSTRUCTIONS |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| expiration_date_od | Expiration Date OD | timestamp | True |  |  |  |
| expiration_date_os | Expiration Date OS | timestamp | True |  |  |  |
| lens_manufacturer_od | Contact lens manufacturer OD | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_manufacturer_os | Contact lens manufacturer OS | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_brand_od | Contact lens brand OD | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_brand_os | Contact lens brand OS | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_color_od | Color / MF PWF OD | string | True | 100 | Based on ABB product database |  |
| lens_color_os | Color / MF PWF Os | string | True | 100 | Based on ABB product database |  |
| start_date_od | Start Date OD | timestamp | True |  |  |  |
| start_date_os | Start Date OS | timestamp | True |  |  |  |
| base_curve_od | Base Curve OD | double | True |  |  |  |
| base_curve_os | Base Curve OS | double | True |  |  |  |
| diameter_od | Diameter OD | double | True |  |  |  |
| diameter_os | Diameter OS | double | True |  |  |  |
| underlying_condition_od | Underlying condition. If not null, all OD refraction values are null (not including over refraction). | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | Underlying condition. If not null, all OS refraction values are null (not including over refraction). | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| sphere_od | Sphere OD | double | True |  |  |  |
| sphere_os | Sphere OS | double | True |  |  |  |
| cylinder_od | Cylinder OD | double | True |  |  |  |
| cylinder_os | Cylinder OS | double | True |  |  |  |
| axis_od | Axis OD | int | True |  |  |  |
| axis_os | Axis OS | int | True |  |  |  |
| add_od | Add OD | double | True |  |  |  |
| add_os | Add OS | double | True |  |  |  |
| refraction_other_od | Refraction other OD | string | True | 255 |  |  |
| refraction_other_os | Refraction other OD | string | True | 255 |  |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_ou | Pinhole visual acuity DccOU | string | True | 20 | See Appendix F |  |
| glare_dcc_od | Glare DccOD | string | True | 20 | See Appendix F |  |
| glare_dcc_os | Glare DccOS | string | True | 20 | See Appendix F |  |
| glare_dcc_ou | Glare DccOU | string | True | 20 | See Appendix F |  |
| bat_dcc_od | Brightness acuity test DccOD | string | True | 20 | See Appendix F |  |
| bat_dcc_os | Brightness acuity test DccOS | string | True | 20 | See Appendix F |  |
| bat_dcc_ou | Brightness acuity test DccOU | string | True | 20 | See Appendix F |  |
| pam_dcc_od | Potential acuity meter DccOD | string | True | 20 | See Appendix F |  |
| pam_dcc_os | Potential acuity meter DccOS | string | True | 20 | See Appendix F |  |
| pam_dcc_ou | Potential acuity meter DccOU | string | True | 20 | See Appendix F |  |
| ram_dcc_od | Retinal acuity meter DccOD | string | True | 20 | See Appendix F |  |
| ram_dcc_os | Retinal acuity meter DccOS | string | True | 20 | See Appendix F |  |
| ram_dcc_ou | Retinal acuity meter DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_dcc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_os | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_ou | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| pinhole_ncc_od | Pinhole visual acuity NccOD | string | True | 20 | See Appendix F |  |
| pinhole_ncc_os | Pinhole visual acuity NccOS | string | True | 20 | See Appendix F |  |
| pinhole_ncc_ou | Pinhole visual acuity NccOU | string | True | 20 | See Appendix F |  |
| glare_ncc_od | Glare NccOD | string | True | 20 | See Appendix F |  |
| glare_ncc_os | Glare NccOS | string | True | 20 | See Appendix F |  |
| glare_ncc_ou | Glare NccOU | string | True | 20 | See Appendix F |  |
| bat_ncc_od | Brightness acuity test NccOD | string | True | 20 | See Appendix F |  |
| bat_ncc_os | Brightness acuity test NccOS | string | True | 20 | See Appendix F |  |
| bat_ncc_ou | Brightness acuity test NccOU | string | True | 20 | See Appendix F |  |
| pam_ncc_od | Potential acuity meter NccOD | string | True | 20 | See Appendix F |  |
| pam_ncc_os | Potential acuity meter NccOS | string | True | 20 | See Appendix F |  |
| pam_ncc_ou | Potential acuity meter NccOU | string | True | 20 | See Appendix F |  |
| ram_ncc_od | Retinal acuity meter NccOD | string | True | 20 | See Appendix F |  |
| ram_ncc_os | Retinal acuity meter NccOS | string | True | 20 | See Appendix F |  |
| ram_ncc_ou | Retinal acuity meter NccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_ncc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_os | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_ou | Visual acuity other NccOD | string | True | 255 |  |  |
| movement_od | (Assessment) Movement OD. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| movement_os | (Assessment) Movement OS. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| centration_od | (Assessment) Centration OD. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| centration_os | (Assessment) Centration OS. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| vision_od | (Assessment) Vision OD. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| vision_os | (Assessment) Vision OS. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| comfort_od | (Assessment) Comfort OD | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| comfort_os | (Assessment) Comfort OS. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| torics_right_od | (Assessment) Torics Right OD | boolean | True |  | True: ON, False: OFF |  |
| torics_right_os | (Assessment) Torics Right OS | boolean | True |  | True: ON, False: OFF |  |
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
| or_visual_acuity_dcc_ou | (Over Refraction) Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_od | (Over Refraction) Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_os | (Over Refraction) Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_ou | (Over Refraction) Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## refraction

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| refraction_id | refraction table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| refraction_type | Refraction Type | string | True | 30 | AUTO_REFRACTION MANIFEST_REFRACTION CYCLOPLEGIC_REFRACTION RETINOSCOPY FINAL_GLASSES_REFRACTION |  |
| eyeglass_usage | Eyeglass Usage | string | True | 255 | See Appendix E |  |
| pd_distance_ou | Binocular Pupillary Distance - Distance | double | True |  |  |  |
| pd_near_ou | Binocular Pupillary Distance - Near | double | True |  |  |  |
| reading_distance | Reading Distance | double | True |  |  |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| print_notes | Display notes on Rx printout. May have a null value. | boolean | True |  |  |  |
| underlying_condition_od | (Prisms/PDs) Underlying condition. If not null, all other OD refraction values are null. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | (Prisms/PDs) Underlying condition. If not null, all other OS refraction values are null. | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| sphere_od | (Refractions) Sphere | double | True |  |  |  |
| sphere_os | (Refractions) Sphere | double | True |  |  |  |
| cylinder_od | (Refractions) Cylinder | double | True |  |  |  |
| cylinder_os | (Refractions) Cylinder | double | True |  |  |  |
| axis_od | (Refractions) Axis | int | True |  |  |  |
| axis_os | (Refractions) Axis | int | True |  |  |  |
| add_od | (Refractions) Add | double | True |  |  |  |
| add_os | (Refractions) Add | double | True |  |  |  |
| horizontal_prism_od | (Prisms/PDs) HPrism | double | True |  |  |  |
| horizontal_prism_os | (Prisms/PDs) HPrism | double | True |  |  |  |
| horizontal_base_od | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| horizontal_base_os | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| vertical_prism_od | (Prisms/PDs) VPrism | double | True |  |  |  |
| vertical_prism_os | (Prisms/PDs) VPrism | double | True |  |  |  |
| vertical_base_od | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| vertical_base_os | (Prisms/PDs) Base. May have a null value. | string | True | 20 | OUT IN UP DOWN |  |
| slab_off_od | (Prisms/PDs) Slab Off | boolean | True |  |  |  |
| slab_off_os | (Prisms/PDs) Slab Off | boolean | True |  |  |  |
| vertex_distance_od | (Prisms/PDs) VD | double | True |  |  |  |
| vertex_distance_os | (Prisms/PDs) VD | double | True |  |  |  |
| pd_distance_od | Pupillary distance - Distance OD | double | True |  |  |  |
| pd_distance_os | Pupillary distance - Distance OS | double | True |  |  |  |
| pd_near_od | Pupillary distance - Near OD | double | True |  |  |  |
| pd_near_os | Pupillary distance - Near OS | double | True |  |  |  |
| refraction_other_od | Refraction other OD | string | True | 255 |  |  |
| refraction_other_os | Refraction other OS | string | True | 255 |  |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_ou | Pinhole visual acuity DccOU | string | True | 20 | See Appendix F |  |
| glare_dcc_od | Glare DccOD | string | True | 20 | See Appendix F |  |
| glare_dcc_os | Glare DccOS | string | True | 20 | See Appendix F |  |
| glare_dcc_ou | Glare DccOU | string | True | 20 | See Appendix F |  |
| bat_dcc_od | Brightness acuity test DccOD | string | True | 20 | See Appendix F |  |
| bat_dcc_os | Brightness acuity test DccOS | string | True | 20 | See Appendix F |  |
| bat_dcc_ou | Brightness acuity test DccOU | string | True | 20 | See Appendix F |  |
| pam_dcc_od | Potential acuity meter DccOD | string | True | 20 | See Appendix F |  |
| pam_dcc_os | Potential acuity meter DccOS | string | True | 20 | See Appendix F |  |
| pam_dcc_ou | Potential acuity meter DccOU | string | True | 20 | See Appendix F |  |
| ram_dcc_od | Retinal acuity meter DccOD | string | True | 20 | See Appendix F |  |
| ram_dcc_os | Retinal acuity meter DccOS | string | True | 20 | See Appendix F |  |
| ram_dcc_ou | Retinal acuity meter DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_dcc_od | Visual acuity other DccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_os | Visual acuity other DccOS | string | True | 255 |  |  |
| visual_acuity_other_dcc_ou | Visual acuity other DccOU | string | True | 255 |  |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| pinhole_ncc_od | Pinhole visual acuity NccOD | string | True | 20 | See Appendix F |  |
| pinhole_ncc_os | Pinhole visual acuity NccOS | string | True | 20 | See Appendix F |  |
| pinhole_ncc_ou | Pinhole visual acuity NccOU | string | True | 20 | See Appendix F |  |
| glare_ncc_od | Glare NccOD | string | True | 20 | See Appendix F |  |
| glare_ncc_os | Glare NccOS | string | True | 20 | See Appendix F |  |
| glare_ncc_ou | Glare NccOU | string | True | 20 | See Appendix F |  |
| bat_ncc_od | Brightness acuity test NccOD | string | True | 20 | See Appendix F |  |
| bat_ncc_os | Brightness acuity test NccOS | string | True | 20 | See Appendix F |  |
| bat_ncc_ou | Brightness acuity test NccOU | string | True | 20 | See Appendix F |  |
| pam_ncc_od | Potential acuity meter NccOD | string | True | 20 | See Appendix F |  |
| pam_ncc_os | Potential acuity meter NccOS | string | True | 20 | See Appendix F |  |
| pam_ncc_ou | Potential acuity meter NccOU | string | True | 20 | See Appendix F |  |
| ram_ncc_od | Retinal acuity meter NccOD | string | True | 20 | See Appendix F |  |
| ram_ncc_os | Retinal acuity meter NccOS | string | True | 20 | See Appendix F |  |
| ram_ncc_ou | Retinal acuity meter NccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_ncc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_os | Visual acuity other NccOS | string | True | 255 |  |  |
| visual_acuity_other_ncc_ou | Visual acuity other NccOU | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## contacts_trial

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| contacts_trial_id | contacts_trial table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  | May be different than the visit date and edited by the physician or staff member. |  |
| contacts_usage | Contact Lens Trial Usage | string | True | 255 | See Appendix E |  |
| status | Status | string | True | 255 | DISPENSED DISPENSED_PATIENT_CAN_CONFIRM DISPENSED_SUCCESSFUL DISPENSED_UNSUCCESSFUL FINAL ORDER_TRIAL ORDER_TRIAL_NEEDS_FITTING_DOCTOR ORDER_TRIAL_NEEDS_FITTING_STAFF ORDER_TRIAL_PATIENT_CAN_CONFIRM SEE_NOTES |  |
| wearing_schedule | (Contact Lens Regimen) Wearing Schedule | string | True | 30 | AS_NEEDED TWO_WEEKS MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY |  |
| replenishment | (Contact Lens Regimen) Replenishment | string | True | 30 | THREE_MONTHS AS_NEEDED TWO_WEEKS SIX_MONTHS DIAGNOSTIC MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY |  |
| disinfecting | (Contact Lens Regimen) Disinfecting | string | True | 30 | CLEAR_CARE_HYDRAGLYDE AQUIFY STORE_BRAND RENU OPTIFREE SAUFLON BIOTRUE LOBOB_SOF_PRO_2 OPTIFREE_PUREMOIST BLINK_REVITALENS CLEAR_CARE NONE OPTIFREE_REPLENISH PEROXICARE SEE_SPECIAL_INSTRUCTIONS UNIQUE_PH |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| print_notes | Display notes on Rx printout | boolean | True |  |  |  |
| expiration_date_od | Expiration Date OD | timestamp | True |  |  |  |
| expiration_date_os | Expiration Date OS | timestamp | True |  |  |  |
| lens_manufacturer_od | Contact lens manufacturer OD | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_manufacturer_os | Contact lens manufacturer OS | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_brand_od | Contact lens brand OD | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_brand_os | Contact lens brand OS | string | True | 100 | Based on ABB product database, or free-text override |  |
| lens_color_od | Color / MF PWF OD | string | True | 100 | Based on ABB product database |  |
| lens_color_os | Color / MF PWF Os | string | True | 100 | Based on ABB product database |  |
| start_date_od | Start Date OD | timestamp | True |  |  |  |
| start_date_os | Start Date OS | timestamp | True |  |  |  |
| base_curve_od | Base Curve OD | double | True |  |  |  |
| base_curve_os | Base Curve OS | double | True |  |  |  |
| diameter_od | Diameter OD | double | True |  |  |  |
| diameter_os | Diameter OS | double | True |  |  |  |
| underlying_condition_od | Underlying condition. If not null, all OD refraction values are null (not including over refraction). | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| underlying_condition_os | Underlying condition. If not null, all OS refraction values are null (not including over refraction). | string | True | 30 | PROSTHESIS BALANCE_LENS NOT_RECORDED NO_LENS |  |
| sphere_od | Sphere OD | double | True |  |  |  |
| sphere_os | Sphere OS | double | True |  |  |  |
| cylinder_od | Cylinder OD | double | True |  |  |  |
| cylinder_os | Cylinder OS | double | True |  |  |  |
| axis_od | Axis OD | int | True |  |  |  |
| axis_os | Axis OS | int | True |  |  |  |
| add_od | Add OD | double | True |  |  |  |
| add_os | Add OS | double | True |  |  |  |
| refraction_other_od | Refraction other OD | string | True | 255 |  |  |
| refraction_other_os | Refraction other OD | string | True | 255 |  |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_ou | Pinhole visual acuity DccOU | string | True | 20 | See Appendix F |  |
| glare_dcc_od | Glare DccOD | string | True | 20 | See Appendix F |  |
| glare_dcc_os | Glare DccOS | string | True | 20 | See Appendix F |  |
| glare_dcc_ou | Glare DccOU | string | True | 20 | See Appendix F |  |
| bat_dcc_od | Brightness acuity test DccOD | string | True | 20 | See Appendix F |  |
| bat_dcc_os | Brightness acuity test DccOS | string | True | 20 | See Appendix F |  |
| bat_dcc_ou | Brightness acuity test DccOU | string | True | 20 | See Appendix F |  |
| pam_dcc_od | Potential acuity meter DccOD | string | True | 20 | See Appendix F |  |
| pam_dcc_os | Potential acuity meter DccOS | string | True | 20 | See Appendix F |  |
| pam_dcc_ou | Potential acuity meter DccOU | string | True | 20 | See Appendix F |  |
| ram_dcc_od | Retinal acuity meter DccOD | string | True | 20 | See Appendix F |  |
| ram_dcc_os | Retinal acuity meter DccOS | string | True | 20 | See Appendix F |  |
| ram_dcc_ou | Retinal acuity meter DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_dcc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_os | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_ou | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| pinhole_ncc_od | Pinhole visual acuity NccOD | string | True | 20 | See Appendix F |  |
| pinhole_ncc_os | Pinhole visual acuity NccOS | string | True | 20 | See Appendix F |  |
| pinhole_ncc_ou | Pinhole visual acuity NccOU | string | True | 20 | See Appendix F |  |
| glare_ncc_od | Glare NccOD | string | True | 20 | See Appendix F |  |
| glare_ncc_os | Glare NccOS | string | True | 20 | See Appendix F |  |
| glare_ncc_ou | Glare NccOU | string | True | 20 | See Appendix F |  |
| bat_ncc_od | Brightness acuity test NccOD | string | True | 20 | See Appendix F |  |
| bat_ncc_os | Brightness acuity test NccOS | string | True | 20 | See Appendix F |  |
| bat_ncc_ou | Brightness acuity test NccOU | string | True | 20 | See Appendix F |  |
| pam_ncc_od | Potential acuity meter NccOD | string | True | 20 | See Appendix F |  |
| pam_ncc_os | Potential acuity meter NccOS | string | True | 20 | See Appendix F |  |
| pam_ncc_ou | Potential acuity meter NccOU | string | True | 20 | See Appendix F |  |
| ram_ncc_od | Retinal acuity meter NccOD | string | True | 20 | See Appendix F |  |
| ram_ncc_os | Retinal acuity meter NccOS | string | True | 20 | See Appendix F |  |
| ram_ncc_ou | Retinal acuity meter NccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_ncc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_os | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_ou | Visual acuity other NccOD | string | True | 255 |  |  |
| movement_od | (Assessment) Movement OD | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| movement_os | (Assessment) Movement OS. May have a null value. | string | True | 100 | GOOD TIGHT LOOSE NONE |  |
| centration_od | (Assessment) Centration OD. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| centration_os | (Assessment) Centration OS. May have a null value. | string | True | 100 | GOOD DECENTERED_NASAL DECENTERED_TEMPORAL SUPERIOR_APERTURE DROPS_WITH_BLINK NONE |  |
| vision_od | (Assessment) Vision OD. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| vision_os | (Assessment) Vision OS. May have a null value. | string | True | 100 | GOOD FUNCTIONAL ADEQUATE POOR NONE |  |
| comfort_od | (Assessment) Comfort OD. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| comfort_os | (Assessment) Comfort OS. May have a null value. | string | True | 100 | COMFORTABLE UNCOMFORTABLE DRY NONE |  |
| torics_right_od | (Assessment) Torics Right OD | boolean | True |  | True: ON, False: OFF |  |
| torics_right_os | (Assessment) Torics Right OS | boolean | True |  | True: ON, False: OFF |  |
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
| or_visual_acuity_dcc_ou | (Over Refraction) Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_od | (Over Refraction) Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_os | (Over Refraction) Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| or_visual_acuity_ncc_ou | (Over Refraction) Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## rgp_contacts_trial

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| rgp_contacts_trial_id | rgp_contacts_trial table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| wearing_schedule | Wear Schedule. May have a null value. | string | True | 30 | AS_NEEDED TWO_WEEKS MONTHLY WEEKLY ANNUALLY SEE_SPECIAL_INSTRUCTIONS DAILY DIAGNOSTIC_LENSES EXTENDED RELIABLE |  |
| disinfecting | Disinfecting. May have a null value. | string | True | 30 | MENICON_MENICARE_GP_CDS RGP_NONE LOBOB_OPTIMUM_CDS UNIQUE_PH MENICON_MENICARE_GP_WRW OPTIFREE_GP MENICON_PROGENT LOBOB_OPTIMUM RGP_STORE_BRAND RGP_SEE_SPECIAL_INSTRUCTIONS OTHER BOSTON_ADVANCE BOSTON_SIMPLUS LOBOB_OPTIMUM_ESC BOSTON_ORIGINAL disinfecting OPTIFREE |  |
| dot | DOT. May have a null value. | string | True | 10 | OD OS NONE |  |
| contacts_usage | Contacts Usage | string | True | 255 | See Appendix E |  |
| status | Status. May have a null value. | string | True | 255 | DISPENSED DISPENSED_PATIENT_CAN_CONFIRM DISPENSED_SUCCESSFUL DISPENSED_UNSUCCESSFUL FINAL ORDER_TRIAL ORDER_TRIAL_NEEDS_FITTING_DOCTOR ORDER_TRIAL_NEEDS_FITTING_STAFF ORDER_TRIAL_PATIENT_CAN_CONFIRM SEE_NOTES |  |
| notes | (Notes) Notes | string | True | -1 |  |  |
| print_notes | Display notes on Rx printout | boolean | True |  |  |  |
| lens_manufacturer_od | Contact lens manufacturer OD | string | True | 100 | Based on ABB product database |  |
| lens_manufacturer_os | Contact lens manufacturer OS | string | True | 100 | Based on ABB product database |  |
| lens_product_od | Contact lens brand OD | string | True | 100 | Based on ABB product database |  |
| lens_product_os | Contact lens brand OS | string | True | 100 | Based on ABB product database |  |
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

## visual_acuity

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visual_acuity_id | visual_acuity table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| distance_test_type | Distance Test Type. May have a null value. | string | True | 20 | SNELLEN ETDRS LOGMAR LANDOLT HOTV HOME_TESTING LEA PATTI TUMBLING_E ALLEN_CARDS ALLEN_SLIDES ALLEN_PICS OTHER NONE |  |
| near_test_type | Near Test Type. May have a null value. | string | True | 20 | NONE SNELLEN JAEGER APT MNOT HOME_TESTING ALLEN_CARDS ALLEN_SLIDES ALLEN_PICS OTHER |  |
| distance_correction_type | Distance Correction Type. May have a null value. | string | True | 20 | GLASSES CONTACTS PHOROPTER OTHER NONE |  |
| near_correction_type | Near Correction Type. May have a null value. | string | True | 20 | GLASSES CONTACTS PHOROPTER OTHER NONE |  |
| visual_acuity_dcc_od | Visual acuity DccOD | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_os | Visual acuity DccOS | string | True | 30 | See Appendix F |  |
| visual_acuity_dcc_ou | Visual acuity DccOU | string | True | 20 | See Appendix F |  |
| pinhole_dcc_od | Pinhole visual acuity DccOD | string | True | 20 | See Appendix F |  |
| pinhole_dcc_os | Pinhole visual acuity DccOS | string | True | 20 | See Appendix F |  |
| pinhole_dcc_ou | Pinhole visual acuity DccOU | string | True | 20 | See Appendix F |  |
| glare_dcc_od | Glare DccOD | string | True | 20 | See Appendix F |  |
| glare_dcc_os | Glare DccOS | string | True | 20 | See Appendix F |  |
| glare_dcc_ou | Glare DccOU | string | True | 20 | See Appendix F |  |
| bat_dcc_od | Brightness acuity test DccOD | string | True | 20 | See Appendix F |  |
| bat_dcc_os | Brightness acuity test DccOS | string | True | 20 | See Appendix F |  |
| bat_dcc_ou | Brightness acuity test DccOU | string | True | 20 | See Appendix F |  |
| pam_dcc_od | Potential acuity meter DccOD | string | True | 20 | See Appendix F |  |
| pam_dcc_os | Potential acuity meter DccOS | string | True | 20 | See Appendix F |  |
| pam_dcc_ou | Potential acuity meter DccOU | string | True | 20 | See Appendix F |  |
| ram_dcc_od | Retinal acuity meter DccOD | string | True | 20 | See Appendix F |  |
| ram_dcc_os | Retinal acuity meter DccOS | string | True | 20 | See Appendix F |  |
| ram_dcc_ou | Retinal acuity meter DccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_dcc_od | Visual acuity other DccOD | string | True | 255 |  |  |
| visual_acuity_other_dcc_os | Visual acuity other DccOS | string | True | 255 |  |  |
| visual_acuity_other_dcc_ou | Visual acuity other DccOU | string | True | 255 |  |  |
| visual_acuity_ncc_od | Visual acuity NccOD | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_os | Visual acuity NccOS | string | True | 20 | See Appendix F |  |
| visual_acuity_ncc_ou | Visual acuity NccOU | string | True | 20 | See Appendix F |  |
| pinhole_ncc_od | Pinhole visual acuity NccOD | string | True | 20 | See Appendix F |  |
| pinhole_ncc_os | Pinhole visual acuity NccOS | string | True | 20 | See Appendix F |  |
| pinhole_ncc_ou | Pinhole visual acuity NccOU | string | True | 20 | See Appendix F |  |
| glare_ncc_od | Glare NccOD | string | True | 20 | See Appendix F |  |
| glare_ncc_os | Glare NccOS | string | True | 20 | See Appendix F |  |
| glare_ncc_ou | Glare NccOU | string | True | 20 | See Appendix F |  |
| bat_ncc_od | Brightness acuity test NccOD | string | True | 20 | See Appendix F |  |
| bat_ncc_os | Brightness acuity test NccOS | string | True | 20 | See Appendix F |  |
| bat_ncc_ou | Brightness acuity test NccOU | string | True | 20 | See Appendix F |  |
| pam_ncc_od | Potential acuity meter NccOD | string | True | 20 | See Appendix F |  |
| pam_ncc_os | Potential acuity meter NccOS | string | True | 20 | See Appendix F |  |
| pam_ncc_ou | Potential acuity meter NccOU | string | True | 20 | See Appendix F |  |
| ram_ncc_od | Retinal acuity meter NccOD | string | True | 20 | See Appendix F |  |
| ram_ncc_os | Retinal acuity meter NccOS | string | True | 20 | See Appendix F |  |
| ram_ncc_ou | Retinal acuity meter NccOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_ncc_od | Visual acuity other NccOD | string | True | 255 |  |  |
| visual_acuity_other_ncc_os | Visual acuity other NccOS | string | True | 255 |  |  |
| visual_acuity_other_ncc_ou | Visual acuity other NccOU | string | True | 255 |  |  |
| visual_acuity_dsc_od | Visual acuity DscOD | string | True | 30 | See Appendix F |  |
| visual_acuity_dsc_os | Visual acuity DscOS | string | True | 30 | See Appendix F |  |
| visual_acuity_dsc_ou | Visual acuity DscOU | string | True | 21 | See Appendix F |  |
| pinhole_dsc_od | Pinhole visual acuity DscOD | string | True | 30 | See Appendix F |  |
| pinhole_dsc_os | Pinhole visual acuity DscOS | string | True | 30 | See Appendix F |  |
| pinhole_dsc_ou | Pinhole visual acuity DscOU | string | True | 20 | See Appendix F |  |
| glare_dsc_od | Glare DscOD | string | True | 20 | See Appendix F |  |
| glare_dsc_os | Glare DscOS | string | True | 20 | See Appendix F |  |
| glare_dsc_ou | Glare DscOU | string | True | 20 | See Appendix F |  |
| bat_dsc_od | Brightness acuity test DscOD | string | True | 20 | See Appendix F |  |
| bat_dsc_os | Brightness acuity test DscOS | string | True | 20 | See Appendix F |  |
| bat_dsc_ou | Brightness acuity test DscOU | string | True | 20 | See Appendix F |  |
| pam_dsc_od | Potential acuity meter DscOD | string | True | 20 | See Appendix F |  |
| pam_dsc_os | Potential acuity meter DscOS | string | True | 20 | See Appendix F |  |
| pam_dsc_ou | Potential acuity meter DscOU | string | True | 20 | See Appendix F |  |
| ram_dsc_od | Retinal acuity meter DscOD | string | True | 20 | See Appendix F |  |
| ram_dsc_os | Retinal acuity meter DscOS | string | True | 20 | See Appendix F |  |
| ram_dsc_ou | Retinal acuity meter DscOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_dsc_od | Visual acuity other DscOD | string | True | 255 |  |  |
| visual_acuity_other_dsc_os | Visual acuity other DscOS | string | True | 255 |  |  |
| visual_acuity_other_dsc_ou | Visual acuity other DscOU | string | True | 255 |  |  |
| visual_acuity_nsc_od | Visual acuity NscOD | string | True | 20 | See Appendix F |  |
| visual_acuity_nsc_os | Visual acuity NscOS | string | True | 20 | See Appendix F |  |
| visual_acuity_nsc_ou | Visual acuity NscOU | string | True | 20 | See Appendix F |  |
| pinhole_nsc_od | Pinhole visual acuity NscOD | string | True | 20 | See Appendix F |  |
| pinhole_nsc_os | Pinhole visual acuity NscOS | string | True | 20 | See Appendix F |  |
| pinhole_nsc_ou | Pinhole visual acuity NscOU | string | True | 20 | See Appendix F |  |
| glare_nsc_od | Glare NscOD | string | True | 20 | See Appendix F |  |
| glare_nsc_os | Glare NscOS | string | True | 20 | See Appendix F |  |
| glare_nsc_ou | Glare NscOU | string | True | 20 | See Appendix F |  |
| bat_nsc_od | Brightness acuity test NscOD | string | True | 20 | See Appendix F |  |
| bat_nsc_os | Brightness acuity test NscOS | string | True | 20 | See Appendix F |  |
| bat_nsc_ou | Brightness acuity test NscOU | string | True | 20 | See Appendix F |  |
| pam_nsc_od | Potential acuity meter NscOD | string | True | 20 | See Appendix F |  |
| pam_nsc_os | Potential acuity meter NscOS | string | True | 20 | See Appendix F |  |
| pam_nsc_ou | Potential acuity meter NscOU | string | True | 20 | See Appendix F |  |
| ram_nsc_od | Retinal acuity meter NscOD | string | True | 20 | See Appendix F |  |
| ram_nsc_os | Retinal acuity meter NscOS | string | True | 20 | See Appendix F |  |
| ram_nsc_ou | Retinal acuity meter NscOU | string | True | 20 | See Appendix F |  |
| visual_acuity_other_nsc_od | Visual acuity other NscOD | string | True | 255 |  |  |
| visual_acuity_other_nsc_os | Visual acuity other NscOS | string | True | 255 |  |  |
| visual_acuity_other_nsc_ou | Visual acuity other NscOU | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## infant_vision

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| infant_vision_id | infant_vision table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| corneal_light_reflex_od | Corneal light reflex OD. May have a null value. | string | True | 20 | C: Central UC: Uncentral OTHER: Other NONE: None |  |
| corneal_light_reflex_os | Corneal light reflex OS. May have a null value. | string | True | 20 | C: Central UC: Uncentral OTHER: Other NONE: None |  |
| steadiness_od | Steadiness OD. May have a null value. | string | True | 20 | S: Steady US: Unsteady OTHER: Other NONE: None |  |
| steadiness_os | Steadiness OS. May have a null value. | string | True | 20 | S: Steady US: Unsteady OTHER: Other NONE: None |  |
| maintains_alignment_od | Maintains alignment OD. May have a null value. | string | True | 20 | M: Maintains UM: Unmaintained OTHER: Other NONE: None |  |
| maintains_alignment_os | Maintains alignment OS. May have a null value. | string | True | 20 | M: Maintains UM: Unmaintained OTHER: Other NONE: None |  |
| other_od | Infant vision other OD. | string | True | 100 |  |  |
| other_os | Infant vision other OD. | string | True | 100 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## keratometry

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| keratometry_id | keratometry table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| notes | Notes. | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## keratometry_reading

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| keratometry_reading_id | keratometry table id | string | False | 20 |  |  |
| keratometry_id | keratometry table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| position | Row index in EMA table. | int | True |  |  |  |
| date_recorded_od | Date reading was recorded. | timestamp | True |  |  |  |
| date_recorded_os | Date reading was recorded. | timestamp | True |  |  |  |
| flat_od | Flat OD. | double | True |  |  |  |
| flat_os | Flat OS. | double | True |  |  |  |
| flat_axis_od | Flat Axis OD. | int | True |  |  |  |
| flat_axis_os | Flat Axis OS. | int | True |  |  |  |
| steep_od | Steep OD. | double | True |  |  |  |
| steep_os | Steep OS. | double | True |  |  |  |
| steep_axis_od | Steep Axis OD. | int | True |  |  |  |
| steep_axis_os | Steep Axis OS. | int | True |  |  |  |
| mires_quality_od | Mires Quality OD. | string | True | 30 | ONE_PLUS TWO_PLUS THREE_PLUS FOUR_PLUS |  |
| mires_quality_os | Mires Quality OS. May have a null value. | string | True | 30 | ONE_PLUS TWO_PLUS THREE_PLUS FOUR_PLUS |  |
| method_od | Method OD. May have a null value. | string | True | 30 | MANUAL AUTO CORNEAL_TOPOGRAPHER |  |
| method_os | Method OS. May have a null value. | string | True | 30 | MANUAL AUTO CORNEAL_TOPOGRAPHER |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## binocular

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| binocular_id | Binocular table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| near_point_conv_test | (Near Point Convergence) Test | string | True | 50 |  |  |
| near_point_conv_reliability | (Near Point Convergence) Reliability | string | True | 20 |  |  |
| near_point_conv_blur | (Near Point Convergence) Blur | int | True |  |  |  |
| near_point_conv_blur_selection | (Near Point Convergence) Blur. Null if near_point_conv_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| near_point_conv_break | (Near Point Convergence) Break | double | True |  |  |  |
| near_point_conv_break_selection | (Near Point Convergence) Break. Null if near_point_conv_break is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| near_point_conv_recover | (Near Point Convergence) Recover | int | True |  |  |  |
| near_point_conv_recover_selection | (Near Point Convergence) Recover. Null if near_point_conv_recover is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| near_point_accom_od | (Near Point Accommodation) OD | double | True |  |  |  |
| near_point_accom_od_selection | (Near Point Accommodation) OD. Null if near_point_accom_od is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| near_point_accom_os | (Near Point Accommodation) OS | double | True |  |  |  |
| near_point_accom_os_selection | (Near Point Accommodation) OS. Null if near_point_accom_os is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| near_point_accom_ou | (Near Point Accommodation) OU | double | True |  |  |  |
| near_point_accom_ou_selection | (Near Point Accommodation) OU. Null if near_point_accom_ou is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| phorias_distance_test | (Phorias - Distance) Test Method | string | True | 50 |  |  |
| phorias_distance_measured_with | (Phorias - Distance) Measured With | string | True | 50 | Manifest -2.00 -1.75 -1.50 -1.25 -1.00 -0.75 -0.50 -0.25 +2.00 +1.75 +1.50 +1.25 +1.00 +0.75 +0.50 +0.25 2.00 1.75 1.50 1.25 1.00 0.75 0.50 0.25 |  |
| phorias_distance_horiz | (Phorias - Distance) Horiz | double | True |  |  |  |
| phorias_distance_horiz_selection | (Phorias - Distance) Horiz. Null if phorias_horiz is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| phorias_distance_deviation | (Phorias - Distance) Deviation | string | True | 50 |  |  |
| phorias_distance_od | (Phorias - Distance) Vertical OD Value | double | True |  |  |  |
| phorias_distance_od_selection | (Phorias - Distance) Vertical OD Value. Null if phorias_distance_od is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| phorias_distance_od_base | (Phorias - Distance) Vertical OD Base | string | True | 20 |  |  |
| phorias_distance_os | (Phorias - Distance) Vertical OS Value | double | True |  |  |  |
| phorias_distance_os_selection | (Phorias - Distance) Vertical OS Value. Null if phorias_distance_os is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| phorias_distance_os_base | (Phorias - Distance) Vertical OS Base | string | True | 2000 |  |  |
| phorias_near_test | (Phorias - Near) Test Method | string | True | 50 |  |  |
| phorias_near_measured_with | (Phorias - Near) Measured With | string | True | 50 | Manifest -2.00 -1.75 -1.50 -1.25 -1.00 -0.75 -0.50 -0.25 +2.00 +1.75 +1.50 +1.25 +1.00 +0.75 +0.50 +0.25 2.00 1.75 1.50 1.25 1.00 0.75 0.50 0.25 |  |
| phorias_near_horiz | (Phorias - Near) Horiz | double | True |  |  |  |
| phorias_near_horiz_selection | (Phorias - Near) Horiz. Null if phorias_horiz is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| phorias_near_deviation | (Phorias - Near) Deviation | string | True | 50 |  |  |
| phorias_near_od | (Phorias - Near) Vertical OD Value | double | True |  |  |  |
| phorias_near_od_selection | (Phorias - Near) Vertical OD Value. Null if phorias_near_od is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| phorias_near_od_base | (Phorias - Near) Vertical OD Base | string | True | 20 |  |  |
| phorias_near_os | (Phorias - Near) Vertical OS Value | double | True |  |  |  |
| phorias_near_os_selection | (Phorias - Near) Vertical OS Value. Null if phorias_near_os is non-null | string | True | 20 |  |  |
| phorias_near_os_base | (Phorias - Near) Vertical OS Base | string | True | 20 |  |  |
| vergence_measured_with | (Vergence) Measured With | string | True | 50 | Manifest -2.00 -1.75 -1.50 -1.25 -1.00 -0.75 -0.50 -0.25 +2.00 +1.75 +1.50 +1.25 +1.00 +0.75 +0.50 +0.25 2.00 1.75 1.50 1.25 1.00 0.75 0.50 0.25 |  |
| divergence_distance_blur | (Vergence) Divergence (BI) Distance Blur | double | True |  |  |  |
| divergence_distance_blur_selection | (Vergence) Divergence (BI) Distance Blur. Null if divergence_distance_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| divergence_distance_break | (Vergence) Divergence (BI) Distance Break | double | True |  |  |  |
| divergence_distance_break_selection | (Vergence) Divergence (BI) Distance Break. Null if divergence_distance_break is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| divergence_distance_recover | (Vergence) Divergence (BI) Distance Recover | double | True |  |  |  |
| divergence_distance_recover_selection | (Vergence) Divergence (BI) Distance Recover. Null if divergence_distance_recover is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| divergence_near_blur | (Vergence) Divergence (BI) Near Blur | double | True |  |  |  |
| divergence_near_blur_selection | (Vergence) Divergence (BI) Near Blur. Null if divergence_near_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| divergence_near_break | (Vergence) Divergence (BI) Near Break | double | True |  |  |  |
| divergence_near_break_selection | (Vergence) Divergence (BI) Near Break. Null if divergence_near_break is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| divergence_near_recover | (Vergence) Divergence (BI) Near Recover | double | True |  |  |  |
| divergence_near_recover_selection | (Vergence) Divergence (BI) Near Recover. Null if divergence_near_recover is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| convergence_distance_blur | (Vergence) Convergence (BO) Distance Blur | double | True |  |  |  |
| convergence_distance_blur_selection | (Vergence) Convergence (BO) Distance Blur. Null if convergence_distance_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| convergence_distance_break | (Vergence) Convergence (BO) Distance Break | double | True |  |  |  |
| convergence_distance_break_selection | (Vergence) Convergence (BO) Distance Break. Null if convergence_distance_break is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| convergence_distance_recover | (Vergence) Convergence (BO) Distance Recover | double | True |  |  |  |
| convergence_distance_recover_selection | (Vergence) Convergence (BO) Distance Recover. Null if convergence_distance_recover is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| convergence_near_blur | (Vergence) Convergence (BO) Near Blur | double | True |  |  |  |
| convergence_near_blur_selection | (Vergence) Convergence (BO) Near Blur. Null if convergence_near_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| convergence_near_break | (Vergence) Convergence (BO) Near Break | double | True |  |  |  |
| convergence_near_break_selection | (Vergence) Convergence (BO) Near Break. Null if convergence_near_break is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| convergence_near_recover | (Vergence) Convergence (BO) Near Recover | double | True |  |  |  |
| convergence_near_recover_selection | (Vergence) Convergence (BO) Near Recover. Null if convergence_near_recover is non-null | string | True | 20 |  |  |
| cross_cylinder_bxc | (Cross-Cylinder) BXC/14b | double | True |  |  |  |
| cross_cylinder_bxc_selection | (Cross-Cylinder) BXC/14b. Null if cross_cylinder_bxc is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| relative_accom_nra_blur | (Relative Accommodation) NRA Blur | double | True |  |  |  |
| relative_accom_nra_blur_selection | (Relative Accommodation) NRA Blur. Null if relative_accom_nra_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| relative_accom_nra_recover | (Relative Accommodation) NRA Recover | double | True |  |  |  |
| relative_accom_nra_recover_selection | (Relative Accommodation) NRA Recover. Null if relative_accom_nra_recover is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| relative_accom_pra_blur | (Relative Accommodation) PRA Blur | double | True |  |  |  |
| relative_accom_pra_blur_selection | (Relative Accommodation) PRA Blur. Null if relative_accom_pra_blur is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| relative_accom_pra_recover | (Relative Accommodation) PRA Recover | double | True |  |  |  |
| relative_accom_pra_recover_selection | (Relative Accommodation) PRA Recover. Null if relative_accom_pra_recover is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| relative_accom_add | (Relative Accommodation) Add | double | True |  |  |  |
| relative_accom_acuity | (Relative Accommodation) Acuity | string | True | 20 |  |  |
| aca_numerator | (AC/A Ratio) Numerator | double | True |  |  |  |
| aca_numerator_selection | (AC/A Ratio) Numerator. Null if aca_numerator is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| aca_denominator | (AC/A Ratio) Denominator | int | True |  |  |  |
| aca_denominator_selection | (AC/A Ratio) Denominator. Null if aca_denominator is non-null | string | True | 20 | UNRESPONSIVE NOT_RECORDED |  |
| fusion_stereo_test | (Fusion/Stereopsis) Test Type | string | True | 20 |  |  |
| fusion_stereo_reliability | (Fusion/Stereopsis) Reliability | string | True | 20 |  |  |
| fusion_stereo_distance | (Fusion/Stereopsis) Distance | int | True |  |  |  |
| fusion_stereo_near | (Fusion/Stereopsis) Near | int | True |  |  |  |
| worth_6_m | (Worth Four Dot Test) at 6 Meters | string | True | 20 |  |  |
| worth_33_cm | (Worth Four Dot Test) at 33 Centimeters | string | True | 20 |  |  |
| titmus_stereo_fly | (Titmus Stereo Test) Stereo Fly Wings | boolean | True |  |  |  |
| titmus_animal_a | (Titmus Stereo Test) Animals - Row A. | boolean | True |  |  |  |
| titmus_animal_b | (Titmus Stereo Test) Animals - Row B. | boolean | True |  |  |  |
| titmus_animal_c | (Titmus Stereo Test) Animals - Row C. | boolean | True |  |  |  |
| titmus_dots_1 | (Titmus Stereo Test) Four Dots - Box 1 | boolean | True |  |  |  |
| titmus_dots_2 | (Titmus Stereo Test) Four Dots - Box 2 | boolean | True |  |  |  |
| titmus_dots_3 | (Titmus Stereo Test) Four Dots - Box 3 | boolean | True |  |  |  |
| titmus_dots_4 | (Titmus Stereo Test) Four Dots - Box 4 | boolean | True |  |  |  |
| titmus_dots_5 | (Titmus Stereo Test) Four Dots - Box 5 | boolean | True |  |  |  |
| titmus_dots_6 | (Titmus Stereo Test) Four Dots - Box 6 | boolean | True |  |  |  |
| titmus_dots_7 | (Titmus Stereo Test) Four Dots - Box 7 | boolean | True |  |  |  |
| titmus_dots_8 | (Titmus Stereo Test) Four Dots - Box 8 | boolean | True |  |  |  |
| titmus_dots_9 | (Titmus Stereo Test) Four Dots - Box 9 | boolean | True |  |  |  |
| dominance | (Dominance) Eye Dominance | string | True | 50 |  |  |
| accom_facility_method | (Accommodative Facility) Method | string | True | 30 |  |  |
| accom_facility_results | (Accommodative Facility) Results | string | True | 20 |  |  |
| accom_facility_rock_power | (Accommodative Facility) Rock Power | double | True |  |  |  |
| accom_facility_reliability | (Accommodative Facility) Reliability | string | True | 20 |  |  |
| mem_ret_accom_lag | (MEM Retinoscopy) Accommodative Lag | string | True | 30 | 1 (Very Weak) +0.25D 4 (Strong) +0.55D 1 (Very Weak) +1.25D 2 (Weak) +1.00D 4 (Strong) +0.50D 5 (Very Strong) +0.25D 3 (Adequate) +0.75D |  |
| mem_ret_accom_excess | (MEM Retinoscopy) Excess | string | True | 30 | 1 (Very Weak) +0.25D 4 (Strong) +0.55D 1 (Very Weak) +1.25D 2 (Weak) +1.00D 4 (Strong) +0.50D 5 (Very Strong) +0.25D 3 (Adequate) +0.75D |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |

## pupil

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pupil_id | Pupil table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| result | Result. May have a null value. | string | True | 20 | NORMAL ABNORMAL UNSPECIFIED |  |
| light_od | Light (mm) OD | double | True |  |  |  |
| light_os | Light (mm) OS | double | True |  |  |  |
| dark_od | Dark (mm) OD | double | True |  |  |  |
| dark_os | Dark (mm) OS | double | True |  |  |  |
| near_od | Near (mm) OD | double | True |  |  |  |
| near_os | Near (mm) OS | double | True |  |  |  |
| size_od | Size OD. May have a null value. | string | True | 20 | NORMAL DILATED MIOTIC UNSPECIFIED |  |
| size_os | Size OS. May have a null value. | string | True | 20 | NORMAL DILATED MIOTIC UNSPECIFIED |  |
| round_od | Round OD. May have a null value. | string | True | 20 | ROUND OVAL PEAKED UNSPECIFIED |  |
| round_os | Round OS. May have a null value. | string | True | 20 | ROUND OVAL PEAKED UNSPECIFIED |  |
| regular_od | Regular OD. May have a null value. | string | True | 20 | REGULAR IRREGULAR PEAKED UNSPECIFIED |  |
| regular_os | Regular OS. May have a null value. | string | True | 20 | REGULAR IRREGULAR PEAKED UNSPECIFIED |  |
| reacts_od | Reacts OD. May have a null value. | string | True | 20 | REACTS_WELL SLUGGISH FIXED HIPPUS NON_REACTIVE UNSPECIFIED |  |
| reacts_os | Reacts OS. May have a null value. | string | True | 20 | REACTS_WELL SLUGGISH FIXED HIPPUS NON_REACTIVE UNSPECIFIED |  |
| apd_od | Afferent pupillary defect (APD) OD. May have a null value. | string | True | 20 | NONE: No APD TRACE: Trace P1: 1+ P2: 2+ P3: 3+ POSITIVE: Positive |  |
| apd_os | Afferent pupillary defect (APD) OS. May have a null value. | string | True | 20 | NONE: No APD TRACE: Trace P1: 1+ P2: 2+ P3: 3+ POSITIVE: Positive |  |
| rapd_od | Relative afferent pupillary defect (APD) OD. May have a null value. | string | True | 45 | TRACE: Trace ZERO_POINT_THREE: 0-0.3 POINT_THREE: 0.3 POINT_THREE_POINT_SIX: 0.3-0.6 POINT_SIX: 0.6 POINT_SIX_POINT_NINE: 0.6-0.9 POINT_NINE: 0.9 POINT_NINE_ONE_POINT_TWO: 0.9-1.2 ONE_POINT_TWO: 1.2 GREATER_THAN_ONE_POINT_TWO: >1.2 NONE: None |  |
| rapd_os | Relative afferent pupillary defect (APD) OS. May have a null value. | string | True | 45 | TRACE: Trace ZERO_POINT_THREE: 0-0.3 POINT_THREE: 0.3 POINT_THREE_POINT_SIX: 0.3-0.6 POINT_SIX: 0.6 POINT_SIX_POINT_NINE: 0.6-0.9 POINT_NINE: 0.9 POINT_NINE_ONE_POINT_TWO: 0.9-1.2 ONE_POINT_TWO: 1.2 GREATER_THAN_ONE_POINT_TWO: >1.2 NONE: None |  |
| other_od | Other OD (right eye) | string | True | 255 |  |  |
| other_os | Other OS (left eye) | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## motility

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| motility_id | Motility table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| result | Motility Result. May have a null value. | string | True | 50 | FULL_OU FULL_OD FULL_OS ABNORMAL ATTEMPTED_BUT_NOT_ACHIEVED UNSPECIFIED |  |
| other | Notes. | string | True | 5000 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## duction

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| duction_id | Duction table id | string | False | 20 |  |  |
| motility_id | Motility table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| top_left_od | Motility measurement for top left sector | double | True |  |  |  |
| top_left_os | Motility measurement for top left sector | double | True |  |  |  |
| top_right_od | Motility measurement for top right sector | double | True |  |  |  |
| top_right_os | Motility measurement for top right sector | double | True |  |  |  |
| middle_left_od | Motility measurement for middle left sector | double | True |  |  |  |
| middle_left_os | Motility measurement for middle left sector | double | True |  |  |  |
| middle_right_od | Motility measurement for middle right sector | double | True |  |  |  |
| middle_right_os | Motility measurement for middle right sector | double | True |  |  |  |
| bottom_left_od | Motility measurement for bottom left sector | double | True |  |  |  |
| bottom_left_os | Motility measurement for bottom left sector | double | True |  |  |  |
| bottom_right_od | Motility measurement for bottom right sector | double | True |  |  |  |
| bottom_right_os | Motility measurement for bottom right sector | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## cover_test

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| cover_test_id | cover_test table id | string | False | 20 |  |  |
| motility_id | Motility table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| near_horizontal_defect | Cover-Uncover Tests. Null if Alternate Cover Tests columns are non-null | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| near_horizontal_defect_eye | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| near_horizontal_defect_amount | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null. | double | True |  |  |  |
| near_vertical_defect | Cover-Uncover Tests. Null if Alternate Cover Tests columns are non-null | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| near_vertical_defect_eye | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| near_vertical_defect_amount | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null. | double | True |  |  |  |
| distance_horizontal_defect | Cover-Uncover Tests. Null if Alternate Cover Tests columns are non-null | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| distance_horizontal_defect_eye | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| distance_horizontal_defect_amount | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null. | double | True |  |  |  |
| distance_vertical_defect | Cover-Uncover Tests. Null if Alternate Cover Tests columns are non-null | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| distance_vertical_defect_eye | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| distance_vertical_defect_amount | Cover-Uncover Tests. Null if Alternate Cover Tests colums are non-null. | double | True |  |  |  |
| top_right_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| top_right_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| top_right_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| top_right_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| top_right_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| top_right_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| top_center_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| top_center_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| top_center_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| top_center_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| top_center_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| top_center_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| top_left_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| top_left_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| top_left_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| top_left_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| top_left_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| top_left_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| tilt_right_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| tilt_right_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| tilt_right_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| tilt_right_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| tilt_right_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| tilt_right_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| middle_right_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| middle_right_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| middle_right_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| middle_right_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| middle_right_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| middle_right_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| middle_center_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| middle_center_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| middle_center_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| middle_center_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| middle_center_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| middle_center_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| middle_left_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| middle_left_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| middle_left_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| middle_left_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| middle_left_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| middle_left_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| tilt_left_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| tilt_left_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| tilt_left_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| tilt_left_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| tilt_left_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| tilt_left_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| bottom_right_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| bottom_right_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| bottom_right_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| bottom_right_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| bottom_right_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| bottom_right_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| bottom_center_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| bottom_center_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| bottom_center_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| bottom_center_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| bottom_center_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| bottom_center_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| bottom_left_horizontal_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE ESOTROPIA INTERMITTENT_ESOTROPIA ESOPHORIA EXOTROPIA INTERMITTENT_EXOTROPIA EXOPHORIA OTHER |  |
| bottom_left_horizontal_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| bottom_left_horizontal_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| bottom_left_vertical_defect | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 50 | NONE HYPERTROPIA INTERMITTENT_HYPERTROPIA HYPERPHORIA HYPOTROPIA INTERMITTENT_HYPOTROPIA HYPOPHORIA OTHER |  |
| bottom_left_vertical_defect_eye | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | string | True | 3 | OD: Oculus Dextrus OS: Oculus Sinister ALT: Alternating |  |
| bottom_left_vertical_defect_amount | Alternate Cover Tests. Null if Cover-Uncover Tests columns are non-null. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## light_reflex

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| light_reflex_id | light_reflex table id | string | False | 20 |  |  |
| motility_id | motility table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| correction | Correction. | string | True | 20 | CORRECTION_WITH CORRECTION_WITHOUT |  |
| working_distance | Working Distance. | string | True | 30 | WORKING_DISTANCE_AT_DISTANCE WORKING_DISTANCE_AT_NEAR |  |
| fixation | Fixation. | string | True | 30 | FIXATION_OD FIXATION_OS FIXATION_NA |  |
| prism | Prism. Free-text field, only numeric values are included. | double | True |  |  |  |
| reflex_prism | Prism. | string | True | 20 | PRISM_BI PRISM_BO PRISM_BU PRISM_BD |  |
| with_lens | With Lens. Free-text field, only numeric values are included. | double | True |  |  |  |
| post_occlusion | Post Occlusion (time in minutes). | int | True |  |  |  |
| hirschberg_amount | (Hirschberg) Diopters. | int | True |  |  |  |
| hirschberg_defect | (Hirschberg) Tropia. | string | True | 20 | ESOTROPIA EXOTROPIA HYPERTROPIA HYPOTROPIA OTHER NONE |  |
| hirschberg_eye | (Hirschberg) Eye | string | True | 10 | OCULUS_NA OD OS |  |
| krimsky_amount | (Krimsky) Diopters. | int | True |  |  |  |
| krimsky_defect | (Krimsky) Tropia. | string | True | 20 | ESOTROPIA EXOTROPIA HYPERTROPIA HYPOTROPIA OTHER NONE |  |
| krimsky_eye | (Krimsky) Eye | string | True | 10 | OCULUS_NA OD OS |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## visual_field

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| visual_field_id | visual_field table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| test_type | Visual Field Test Type | string | True | 20 | FDT: FDT PERIMETRY: Auto-Perimetry CVF: Confrontation Visual Fields APPROACH_WITH_TOY: Approach with Toy OTHER |  |
| test_other | Test type other free text. Will be null is test type is not other. | string | True | 255 |  |  |
| result | Result | string | True | 30 | ABNORMAL ABNORMAL_FINGER_CT ATTEMPTED_BUT_NOT_ACHIEVED CONSTRICTED_VISUAL_FIELD FULL_FINGER_CT_OD FULL_FINGER_CT_OS FULL_FINGER_CT_OU GROSSLY_NORMAL_CT NORMAL_OD NORMAL_OS NORMAL_OU POSSIBLY_ABNORMAL UNSPECIFIED VISUAL_FIELD_ABNORMAL VISUAL_FIELD_NORMAL |  |
| additional_notes | Additional visual field notes. | string | True | 255 |  |  |
| top_left_outer_od | Top left outer OD (right eye) | boolean | True |  |  |  |
| top_left_outer_os | Top left outer OS (left eye) | boolean | True |  |  |  |
| top_left_inner_od | Top left inner OD (right eye) | boolean | True |  |  |  |
| top_left_inner_os | Top left inner OS (left eye) | boolean | True |  |  |  |
| top_right_outer_od | Top right outer OD (right eye) | boolean | True |  |  |  |
| top_right_outer_os | Top right outer OS (left eye) | boolean | True |  |  |  |
| top_right_inner_od | Top right inner OD (right eye) | boolean | True |  |  |  |
| top_right_inner_os | Top right inner OS (left eye) | boolean | True |  |  |  |
| bottom_left_outer_od | Bottom left outer OD (right eye) | boolean | True |  |  |  |
| bottom_left_outer_os | Bottom left outer OS (left eye) | boolean | True |  |  |  |
| bottom_left_inner_od | Bottom left inner OD (right eye) | boolean | True |  |  |  |
| bottom_left_inner_os | Bottom left inner OS (left eye) | boolean | True |  |  |  |
| bottom_right_outer_od | Bottom right outer OD (right eye) | boolean | True |  |  |  |
| bottom_right_outer_os | Bottom right outer OS (left eye) | boolean | True |  |  |  |
| bottom_right_inner_od | Bottom right inner OD (right eye) | boolean | True |  |  |  |
| bottom_right_inner_os | Bottom right inner OS (left eye) | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## iop

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| iop_id | IOP table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | True | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| eye | Eye evaluated | string | True | 2 | OS OD |  |
| method | Method | string | True | 30 | APPLANATION GOLDMANN TONOPEN MCKAY_MARG PERKINS DCT NCT PALPATION PASCAL PNEUMOTONOMETER ICARE OTHER NONE |  |
| measurement | Numeric measurement. Null if measurement_selection is non-null. | int | True |  |  |  |
| measurement_selection | Non-numeric measurement. Null if measurement is non-null. | string | True | 30 | ATTEMPTED_BUT_NOT_ACHIEVED DEFERRED SOFT NORMAL HARD |  |
| reliability | Reliability | string | True | 30 | RELIABLE SQUINTING UNCOOPERATIVE |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## diagnostic_drops

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| diagnostic_drops_id | diagnostic_drops table id | string | False | 20 |  |  |
| visit_id | visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| date_recorded | Date recorded. May be different than the visit date and edited by the physician or staff member. | timestamp | True |  |  |  |
| counsel_od | If patient was counseled on the risks of dilation OD | boolean | True |  |  |  |
| counsel_os | If patient was counseled on the risks of dilation OS | boolean | True |  |  |  |
| tropicamide_1_phenylephrine_2_5_od | Tropicamide 1%/Phenylephrine 2.5% OD | boolean | True |  |  |  |
| tropicamide_1_phenylephrine_2_5_os | Tropicamide 1%/Phenylephrine 2.5% OS | boolean | True |  |  |  |
| atropine_1_od | Atropine 1% OD | boolean | True |  |  |  |
| atropine_1_os | Atropine 1% OS | boolean | True |  |  |  |
| cyclopentolate_0_5_od | Cyclopentolate 0.5% OD | boolean | True |  |  |  |
| cyclopentolate_0_5_os | Cyclopentolate 0.5% OS | boolean | True |  |  |  |
| cyclopentolate_1_od | Cyclopentolate 1% OD | boolean | True |  |  |  |
| cyclopentolate_1_os | Cyclopentolate 1% OS | boolean | True |  |  |  |
| cyclopentolate_2_od | Cyclopentolate 2% OD | boolean | True |  |  |  |
| cyclopentolate_2_os | Cyclopentolate 2% OS | boolean | True |  |  |  |
| homatropine_5_od | Homatropine 5% OD | boolean | True |  |  |  |
| homatropine_5_os | Homatropine 5% OS | boolean | True |  |  |  |
| apraclonidine_1_od | Apraclonidine 1% OD | boolean | True |  |  |  |
| apraclonidine_1_os | Apraclonidine 1% OS | boolean | True |  |  |  |
| isopto_hyoscine_0_25_od | Isopto Hyoscine 0.25% OD | boolean | True |  |  |  |
| isopto_hyoscine_0_25_os | Isopto Hyoscine 0.25% OS | boolean | True |  |  |  |
| phenylephrine_10_od | Phenylephrine 10% OD | boolean | True |  |  |  |
| phenylephrine_10_os | Phenylephrine 10% OS | boolean | True |  |  |  |
| phenylephrine_2_5_od | Phenylephrine 2.5% OD | boolean | True |  |  |  |
| phenylephrine_2_5_os | Phenylephrine 2.5% OS | boolean | True |  |  |  |
| scopolamine_0_25_od | Scopolamine 0.25% OD | boolean | True |  |  |  |
| scopolamine_0_25_os | Scopolamine 0.25% OS | boolean | True |  |  |  |
| tropicamide_0_5_od | Tropicamide 0.5% OD | boolean | True |  |  |  |
| tropicamide_0_5_os | Tropicamide 0.5% OS | boolean | True |  |  |  |
| tropicamide_1_od | Tropicamide 1% OD | boolean | True |  |  |  |
| tropicamide_1_os | Tropicamide 1% OS | boolean | True |  |  |  |
| cyclomydril_od | Cyclomydril OD | boolean | True |  |  |  |
| cyclomydril_os | Cyclomydril OS | boolean | True |  |  |  |
| tropicamide_0_5_phenylephrine_2_5_od | Tropicamide 0.5%/Phenylephrine 2.5% OD | boolean | True |  |  |  |
| tropicamide_0_5_phenylephrine_2_5_os | Tropicamide 0.5%/Phenylephrine 2.5% OS | boolean | True |  |  |  |
| tropicamide_1_phenylephrine_10_od | Tropicamide 1%/Phenylephrine 10% OD | boolean | True |  |  |  |
| tropicamide_1_phenylephrine_10_os | Tropicamide 1%/Phenylephrine 10% OS | boolean | True |  |  |  |
| mydriacyl_neosynephrine_od | Mydriacyl / NeoSynephrine OD | boolean | True |  |  |  |
| mydriacyl_neosynephrine_os | Mydriacyl / NeoSynephrine OS | boolean | True |  |  |  |
| mydriacyl_od | Mydriacyl OD | boolean | True |  |  |  |
| mydriacyl_os | Mydriacyl OS | boolean | True |  |  |  |
| paremyd_od | Paremyd OD | boolean | True |  |  |  |
| paremyd_os | Paremyd OS | boolean | True |  |  |  |
| fluress_od | fluress OD | boolean | True |  |  |  |
| fluress_os | fluress OS | boolean | True |  |  |  |
| pilocarpine_1_od | Pilocarpine 1% OD | boolean | True |  |  |  |
| pilocarpine_1_os | Pilocarpine 1% OS | boolean | True |  |  |  |
| pilocarpine_2_od | Pilocarpine 2% OD | boolean | True |  |  |  |
| pilocarpine_2_os | Pilocarpine 2% OS | boolean | True |  |  |  |
| pilocarpine_4_od | Pilocarpine 4% OD | boolean | True |  |  |  |
| pilocarpine_4_os | Pilocarpine 4% OS | boolean | True |  |  |  |
| proparacaine_0_5_od | Proparacaine 0.5% OD | boolean | True |  |  |  |
| proparacaine_0_5_os | Proparacaine 0.5% OS | boolean | True |  |  |  |
| sodium_fluorescein_od | Sodium Fluorescein OD | boolean | True |  |  |  |
| sodium_fluorescein_os | Sodium Fluorescein OS | boolean | True |  |  |  |
| tetracaine_0_5_od | Sodium Fluorescein OD | boolean | True |  |  |  |
| tetracaine_0_5_os | Sodium Fluorescein OS | boolean | True |  |  |  |
| other_od | Other value OD | string | True | 255 |  |  |
| other_os | Other value OS | string | True | 255 |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## central_retinal_thickness

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| central_retinal_thickness_id | central_retinal_thickness table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| central_retinal_thickness_od | Central Retinal Thickness (µm) OD. | double | True |  |  |  |
| central_retinal_thickness_os | Central Retinal Thickness (µm) OS. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## rnfl_thickness

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| rnfl_thickness_id | rnfl_thickness table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| rnfl_thickness_od | RNFL Thickness (µm) OD | double | True |  |  |  |
| rnfl_thickness_os | RNFL Thickness (µm) OS. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## pachymetry

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| pachymetry_id | pachymetry table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| central_cornea_od | Central Cornea OD | double | True |  |  |  |
| central_cornea_os | Central Cornea OS. | double | True |  |  |  |
| superior_cornea_od | Superior Cornea OD. | double | True |  |  |  |
| superior_cornea_os | Superior Cornea OS. | double | True |  |  |  |
| nasal_cornea_od | Nasal Cornea OD. | double | True |  |  |  |
| nasal_cornea_os | Nasal Cornea OS. | double | True |  |  |  |
| inferior_cornea_od | Inferior Cornea OD. | double | True |  |  |  |
| inferior_cornea_os | Inferior Cornea OD. | double | True |  |  |  |
| temporal_cornea_od | Temporal Cornea OD. | double | True |  |  |  |
| temporal_cornea_os | Temporal Cornea OS. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## endothelial_counts

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| endothelial_counts_id | endothelial_counts table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| count_od | Endothelial Cell Counts OD. | double | True |  |  |  |
| count_os | Endothelial Cell Counts OS. | double | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## amsler_grid

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| amsler_grid_id | amsler_grid table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| result | Result | string | True | 20 | NORMAL ABNORMAL UNSPECIFIED |  |
| top_left_od | Top left sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| top_left_os | Top left sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| top_right_od | Top right sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| top_right_os | Top right sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| middle_center_od | Middle center sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| middle_center_os | Middle center sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| bottom_left_od | Bottom left sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| bottom_left_os | Bottom left sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| bottom_right_od | Bottom right sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| bottom_right_os | Bottom right sector Amsler result | string | True | 20 | NORMAL FADED SCOTOMA METAMORPHOPSIA |  |
| firm_global_id | ModMed internal firm global identifier | string | False | 10 |  |  |

## color_vision

| Column | Description | Type | Nullable | Len | Values/Coding | Deprecated |
|---|---|---|---|---|---|---|
| color_vision_id | color_vision table id | string | False | 20 |  |  |
| visit_id | Visit table id | string | False | 20 |  |  |
| patient_id | patient table id | string | False | 20 |  |  |
| result | Color Vision Result | string | True | 30 | NORMAL ABNORMAL UNSPECIFIED |  |
| test_type | (Pseudoisochromatic Plates) Test Type | string | True | 20 | ISHIHARA: Ishihara plates HRR: Hardy-Rand_Rittler Plates OTHER: Other NONE: null |  |
| additional_notes | Color Vision Test Additional Notes. | string | True | 400 |  |  |
| farnsworth_od | Farnsworth Results OD. | string | True | 20 | NORMAL DEUTAN PROTAN TRITAN |  |
| farnsworth_os | Farnsworth Results OS. | string | True | 20 | NORMAL DEUTAN PROTAN TRITAN |  |
| correct_od | (Pseudoisochromatic Plates) Results | int | True |  |  |  |
| correct_os | (Pseudoisochromatic Plates) Results | int | True |  |  |  |
| plates_od | (Pseudoisochromatic Plates) Results | int | True |  |  |  |
| plates_os | (Pseudoisochromatic Plates) Results | int | True |  |  |  |
| od_1 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_2 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_3 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_4 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_5 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_6 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_7 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_8 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_9 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_10 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_11 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_12 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_13 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_14 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_15 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_16 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_17 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_18 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_19 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_20 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_21 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_22 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_23 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_24 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_25 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_26 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_27 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_28 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_29 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_30 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_31 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_32 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_33 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_34 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_35 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_36 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_37 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| od_38 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_1 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_2 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_3 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_4 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_5 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_6 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_7 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_8 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_9 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_10 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_11 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_12 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_13 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_14 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_15 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_16 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_17 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_18 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_19 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_20 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_21 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_22 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_23 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_24 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_25 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_26 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_27 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_28 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_29 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_30 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_31 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_32 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_33 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_34 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_35 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_36 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_37 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| os_38 | (Pseudoisochromatic Plates) If plate number is selected for the given eye | boolean | True |  |  |  |
| firm_global_id | ModMed internal firm global identifier | string | True | 10 |  |  |
