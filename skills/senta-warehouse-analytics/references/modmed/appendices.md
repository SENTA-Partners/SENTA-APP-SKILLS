# Appendices: Value Codings


## Appendix A - Immunization Publ

| Code | Description |
|---|---|
| PC01 | No reminder/recall |
| PC12 | Only recall to provider no reminder |
| PC10 | Only reminder to provider no recall |
| PC06 | Recall only - any method |
| PC07 | Recall only - no calls |
| PC11 | Recall to provider |
| PC04 | Reminder only - any method |
| PC05 | Reminder only - no calls |
| PC09 | Reminder to provider |
| PC02 | Reminder/recall - any method |
| PC03 | Reminder/recall - no calls |
| PC08 | Reminder/recall - to provider |

## Appendix B - Patient History

| Unnamed: 0 | Unnamed: 1 |
|---|---|
| Patient history lists all have the following columns: value, snomed, secondary_snomed |  |
| RECOMMENDATION: use snomed column to identify conditions. Descriptions for each snomed code can be looked up in the snomed table. |  |
| Before EMA 5.16, the patient clipboard contained hard-coded list of conditions for users to select (the "value" field) |  |
| With the 5.16 custom clipboard feature, the clipboard items were converted to SNOMED values, and practices can add their own SNOMED codes |  |
| For backwards compatibility, if a SNOMED code can be mapped to a enum value, that is stored in the "value" field |  |
| For historical data that was entered using the enum, those values are mapped to a snomed code in the "snomed" and "secondary_snomed" columns |  |
| The social history table has the following values: |  |
| SEX_NONE | Are you sexually active? - No |
| SEX_ONE | Are you sexually active? - Yes, one partner |
| SEX_MULTIPLE | Are you sexually active? - Yes, multiple partners |
| SEX_SAME | Is your partner the same gender as yourself? |
| DRUG_USE | Illicit drug use? |
| DRUG_USE_IV | IV drug use |
| DRUG_USE_IV_WITHIN_PAST_12_MONTHS | IV drug use within the past 12 months |
| ETOH_NONE | Do you consume alcohol (EtOH or grain alcohol)? - EtOH none |
| ETOH_ONE | Do you consume alcohol (EtOH or grain alcohol)? - EtOH less than 1 drink per day |
| ETOH_TWO | Do you consume alcohol (EtOH or grain alcohol)? - EtOH 1-2 drinks per day |
| ETOH_THREE | Do you consume alcohol (EtOH or grain alcohol)? - EtOH 3 or more drinks per day |
| HOME_SAFE | Do you feel safe at home? - Yes |
| HOME_UNSAFE | Do you feel safe at home? - No |
| OTHER | Other |
| NONE | None |
| DRIVE_DAYTIME | Drive in the Daytime |
| DRIVE_NIGHT | Drive at Night |

## Appendix C - Fax Status

| Status Code | Description |
|---|---|
| -1 | Pre-processing |
| -2 | Ready |
| -3 | Sending (or pending retry) |
| -11 | Pre-processing |
| -22 | Out of credit, awaiting topup |
| 0 | OK (Fax successfully sent) |
| 256 | Internal error |
| 263 | Busy |
| 403 | Fax manually canceled |
| 3072 | Telephony error |
| 3080 | Telephony error |
| 3211 | Fax machine incompatibility |
| 3220 | Fax machine incompatibility |
| 3223 | An unexpected disconnect command was sent |
| 3224 | The remote fax machine failed to respond |
| 3225 | Fax machine incompatibility |
| 3230 | A disconnect message was received while attempting to negotiate transmission |
| 3231 | Fax machine incompatibility |
| 3233 | Fax machine incompatibility |
| 3264 | Fax machine incompatibility |
| 3267 | Fax machine incompatibility |
| 3268 | Transmission error (after page break) |
| 3269 | Fax machine incompatibility** |
| 3300 | Telephony error |
| 3510 | Telephony error |
| 3830 | Telephony error |
| 3912 | Phone number not operational |
| 3931 | Busy |
| 3932 | Phone number not operational |
| 3933 | Busy |
| 3935 | No answer (might be out of paper) |
| 3936 | Human voice answer |
| 3937 | Ring busy |
| 3938 | Phone number not operational |
| 6001 | Phone number not operational |
| 6003 | Telephony error |
| 6004 | Telephony error |
| 6016 | Telephony error |
| 6017 | Busy |
| 6018 | No answer (Might be out of paper) |
| 6019 | Telephony error |
| 6021 | Call rejected |
| 6022 | Number changed |
| 6027 | Phone number not operational |
| 6028 | Phone number not operational |
| 6029 | Call rejected |
| 6031 | Telephony error |
| 6034 | Telephony error |
| 6038 | Telephony error |
| 6041 | Telephony error |
| 6042 | Telephony error |
| 6043 | Telephony error |
| 6044 | Telephony error |
| 6047 | Telephony error |
| 6050 | Telephony error |
| 6054 | Telephony error |
| 6057 | Telephony error |
| 6058 | Telephony error |
| 6063 | Telephony error |
| 6065 | Telephony error |
| 6069 | Telephony error |
| 6079 | Telephony error |
| 6088 | Incompatible destination |
| 6095 | Incompatible destination |
| 6097 | Incompatible destination |
| 6099 | Incompatible destination |
| 6100 | Incompatible destination |
| 6102 | Telephony error |
| 6111 | Telephony error |
| 6127 | Telephony error |
| 7004 | Telephony error |
| 7012 | Telephony error |
| 7013 | Telephony error |
| 8021 | No answer |
| 8025 | Busy |
| 204000 | Rendering error |
| 204001 | Rendering error |
| 205000 | Quota exceeded (Prepaid card depleted) |
| 205001 | Internal System error (FindRoute) |
| 206001 | Internal System Error (LocalSender) |
| -4 | Fax is being handled |
| -99 | Fax is being handled |
| -1062 | Fax is being handled |
| -1004 | Fax is being handled |
| 7200 | Unspecified fax failure |
| 8010 | The remote fax machine hung up before receiving fax |
| 6002 | No route available |

## Appendix D - Cancer Log Values

| Table | Column | Values (or Value: Description) |
|---|---|---|
| cancer_log | behavior | BENIGN: Benign UNCERTAIN: Uncertain whether benign or malignant IN_SITU: In Situ, non-invasive MALIGNANT: Malignant, primary site MALIGNANT_METASTATIC: Malignant, metastatic MALIGNANT_UNCERTAIN: Malignant, uncertain whether primary or metastatic |
| cancer_log | clinical_metastasis | CLINICAL_M0, CLINICAL_M1, CLINICAL_M1A, CLINICAL_M1B, CLINICAL_M1C, CLINICAL_M1D, CLINICAL_M1E, CLINICAL_MX, NOT_APPLICABLE |
| cancer_log | clinical_node | CLINICAL_N0, CLINICAL_N1, CLINICAL_N1MI, CLINICAL_N1A, CLINICAL_N1B, CLINICAL_N1B1, CLINICAL_N1B2, CLINICAL_N1B3, CLINICAL_N1B4, CLINICAL_N1C, CLINICAL_N2, CLINICAL_N2A, CLINICAL_N2B, CLINICAL_N2C, CLINICAL_N3, CLINICAL_N3A, CLINICAL_N3B, CLINICAL_N3C, CLINICAL_NX, NOT_APPLICABLE |
| cancer_log | clinical_stage | STAGE_0, STAGE_0A, STAGE_0IS, STAGE_I, STAGE_IA, STAGE_IA1, STAGE_IA2, STAGE_IB, STAGE_IB1, STAGE_IB2, STAGE_IC, STAGE_II, STAGE_IIA, STAGE_IIA1, STAGE_IIA2, STAGE_IIB, STAGE_IIC, STAGE_III, STAGE_IIIA, STAGE_IIIB, STAGE_IIIC, STAGE_IS, STAGE_IV, STAGE_IVA, STAGE_IVB, STAGE_IVC |
| cancer_log | clinical_stage_descriptor | EXTRANODAL_SPLEEN: E & S (Extranodal and spleen, lymphomas only) EXTRANODAL: E (Extranodal, lymphomas only) MULTIPLE: M (Multiple primary tumors in a single site) NONE: None SPLEEN: S (Spleen, lymphomas only) UNKNOWN: Unknown, not stated in patient record |
| cancer_log | clinical_staged_by | PHYSICIAN: Managing physician PATHOLOGIST: Pathologist PATHOLOGIST_AND_PHYSICIAN: Pathologist and managing physician COMMITTEE_LIAISON_ADVISOR: Cancer Committee chair, cancer liaison physician, or registry physician advisor REGISTRAR: Cancer registrar REGISTRAR_AND_PHYSICIAN: Cancer registrar and physician ANOTHER_FACILITY: Staging assigned at another facility |
| cancer_log | clinical_tumor | CLINICAL_TA, CLINICAL_TIS, CLINICAL_T0, CLINICAL_T1, CLINICAL_T1MIC, CLINICAL_T1A, CLINICAL_T1A1, CLINICAL_T1A2, CLINICAL_T1B, CLINICAL_T1B1, CLINICAL_T1B2, CLINICAL_T1C, CLINICAL_T1D, CLINICAL_T2, CLINICAL_T2A, CLINICAL_T2A1, CLINICAL_T2A2, CLINICAL_T2B, CLINICAL_T2C, CLINICAL_T2D, CLINICAL_T3, CLINICAL_T3A, CLINICAL_T3B, CLINICAL_T3C, CLINICAL_T3D, CLINICAL_T4, CLINICAL_T4A, CLINICAL_T4B, CLINICAL_T4C, CLINICAL_T4D, CLINICAL_T4E, CLINICAL_TX, NOT_APPLICABLE |
| cancer_log | diagnostic_confirmation | POSITIVE_HISTOLOGY: Positive histology POSITIVE_CYTOLOGY: Positive cytology, no positive histology POSITIVE_HISTOLOGY_PLUS: Positive histology Plus positive immunophenotyping and/or positive genetic studies POSITIVE_MICROSCOPIC: Positive microscopic confirmation, method not specified POSITIVE_LABORATORY_TEST: Positive laboratory test/marker study DIRECT_VISUALIZATION: Direct visualization without microscopic confirmation RADIOGRAPHY_AND_OTHER: Radiography and imaging techniques without microscopic confirmation CLINICAL_DIAGNOSIS: Clinical diagnosis only (other than 5, 6, or 7) UNKNOWN: Unknown; not stated in patient's record |
| cancer_log | laterality | NOT_PAIRED: Not a paired site RIGHT: Right: origin of primary LEFT: Left: origin of primary ONE_SIDE: Only one side involved, right or left origin unspecified BILATERAL: Bilateral involvement, lateral origin unknown MIDLINE: Midline of Tumor PAIRED: Paired site |
| cancer_log | mitotic_index | ZERO_PER_HPF, ONE_PER_HPF, TWO_PER_HPF, THREE_PER_HPF, FOUR_PER_HPF, FIVE_PER_HPF, SIX_PER_HPF, SEVEN_PER_HPF, EIGHT_PER_HPF, NINE_PER_HPF, TEN_PER_HPF, TOO_MANY_TO_COUNT |
| cancer_log | tnm_edition | EDITION_UNKNOWN: Edition Unknown FIFTH_EDITION: Fifth Edition (1997), cases diagnosed 1998-2002 FIRST_EDITION: First Edition FOURTH_EDITION: Fourth Edition (1992), cases diagnosed 1993-1997 NOT_APPLICABLE: Not applicable NOT_STAGED: Not staged SECOND_EDITION: Second Edition (1983) SEVENTH_EDITION: Seventh Edition (2009), cases diagnosed 2010+ SIXTH_EDITION: Sixth Edition (2002), cases diagnosed 2003-2009 THIRD_EDITION: Third Edition (1988) |
| cancer_log_visit | history_status | DENY_RECUR: denying any recurrence DENY_WL: denying weight loss, headaches, new lumps or bumps CONCERN_RECUR: now concerned about recurrence to the treated area CONCERN_NEW_MOLE: now concerned about new mole CONCERN_CHANING_RECUR: now concerned about new changing mole CONCERN_BLEED_LESION: now concerned about new bleeding lesion CONCERN_SCAR_PAINFUL: now concerned about scar being painful CONCERN_SCAR_ITCHY: now concerned about scar being itchy CONCERN_SCAR_BUMPY: now concerned about scar being bumpy NEW_LESION_FROM_SCAR: now noting new lesion coming back from prior scar EDU_AND_COUNSELING: now here for education and counseling about skin cancer recurrences SKIN_CNCER_SURV: now here for skin cancer surveillance DENY_ALL_UPPER: denying any GERD, dysphagia, anorexia, weight loss (default) COMPLAIN_GERD: now complaining GERD COMPLAIN_DYSPHAGIA: now complaining of dysphagia COMPLAIN_ANOREXIA: now complaining of anorexia COMPLAIN_WEIGHT_LOSS: now complaining of weight loss DENY_ALL_LOWER: denying any abdominal pain, change in bowel habits, GI bleeding, weight loss (default) COMPLAIN_ABDOMINAL_PAIN: now complaining of abdominal pain COMPLAIN_BOWEL_HABITS: now complaining of a change in bowel habits COMPLAIN_GI_BLEEDING: now complaining of gastrointestinal bleeding COMPLAIN_UNENTENTIONAL_WEIGHT_LOSS: now complaining of unintentional weight loss COLON_CANCER_SURVEILLANCE: now here for colon cancer surveillance DENY_ALL_PROSTATE: denying weight loss, bone pain, hematuria COMPLAIN_BONE_PAIN: complaining of bone pain COMPLAIN_HEMATURIA: complaining of hematuria COMPLAIN_URO_WEIGHT_LOSS_PROSTATE: complaining of weight loss PRESENT_PROSTATE_CANCER_EDUCATION: presenting for education and counseling about prostate cancer PRESENT_ACTIVE_SURVEILLANCE: presenting for active surveillance PRESENT_POST_TX_SURVEILLANCE: presenting for post-treatment surveillance DENY_ALL_BLADDER: denying gross hematuria, dysuria or irritative voiding symptoms COMPLAIN_GROSS_HEMATURIA: complaining of gross hematuria COMPLAIN_DYSURIA: complaining of dysuria COMPLAIN_IRRITATIVE_VOIDING_SYMPTOMS: complaining of irritative voiding symptoms COMPLAIN_URO_WEIGHT_LOSS_BLADDER: complaining of weight loss PRESENT_BLADDER_CANCER_EDUCATION: presenting for education and counseling about bladder cancer PRESENT_SURVEILLANCE: presenting for surveillance PRESENT_URETHRAL_CANCER_EDUCATION: presenting for education and counseling about urethral cancer PRESENT_UTERAL_CANCER_EDUCATION: presenting for education and counseling about uteral cancer PRESENT_PENILE_CANCER_EDUCATION: presenting for education and counseling about penile cancer PRESENT_KIDNEY_CANCER_EDUCATION: presenting for education and counseling about kidney cancer PRESENT_TESTIS_CANCER_EDUCATION: presenting for education and counseling about testis cancer PRESENT_ADRENAL_CANCER_EDUCATION: presenting for education and counseling about adrenal cancer PRESENT_FOLLOW_UP: presenting for follow-up PRESENT_EDUCATION_COUNSELING: presents for education and counseling ENT_NO_NEW_CONCERN: Has no new concerning symptoms. He/she denies: ENT_FOLLOWING_SYMPTOMS: Has the following symptoms: |
| cancer_log_visit | plan_morphology | NO_CLINICAL_SIGNS: no clinical signs of recurrence RESIDUAL_EROSION: residual erosion with crusting RESIDUAL_PIGMENTED_MAC: residual pigmented macule RESIDUAL_PIGMENTED_NODULE: residual pigmented nodule RESIDUAL_PIGMENTED_PAPULE: residual pigmented papule RESIDUAL_ERYTHEMATOUS: residual scaly erythematous papule RESIDUAL_ULCER: residual ulcer with crusting WELL_HEALED_NER: well healed scar with NER WELL_HEALED_NO_SIGNS: well healed scar with no clinical signs of recurrence WELL_HEALED_RECUR: well healed scar with recurrence WELL_HEALED_REGIONAL_LYMPH: well healed scar with regional lymphadenopathy WELL_HEALED_TRANSIT_METASASES: well healed scar with in transit metastases NO_EVIDENCE_OF_DISEASE: no evidence of disease SUSPICION_FOR_RECURRENCE: suspicion for recurrence STABLE_DISEASE: stable disease DISEASE_PROGRESSION: disease progression RECURRENT_DISEASE: recurrent disease ELEVATED_PSA: elevated PSA HEMATURIA: hematuria ABNORMAL_URINE_TEST: abnormal urine test ABNORMAL_EXAM: abnormal exam ABNORMAL_TEST_RESULTS: abnormal test results OTHER: other |
| cancer_log_visit | plan_plan | RECOMMEND_EXAM: Recommend continued skin exams to observe for any changes. Patient to contact the office should any changes occur. EDU_REGULAR: Educated patient to observe for any changes, will continue to monitor with regular skin exams. EDU_Q3: Educated patient to observe for any changes, will continue to monitor with q3 month skin exams. EDU_Q6: Educated patient to observe for any changes, will continue to monitor with q6 month skin exams. EDU_Y1: Educated patient to observe for any changes, will continue to monitor with q1 year skin exams. FURTHER_EVAL: Further Evaluation OBSERVE: Observation for any new changes and education REASSURANCE: Reassurance REVIEW_REGULAR: Reviewed with patient signs and symptoms of clinical recurrence, will continue to monitor with regular skin exams. REVIEW_Q3: Reviewed with patient signs and symptoms of clinical recurrence,will continue to monitor with q3 month skin exams. REVIEW_Q6: Reviewed with patient signs and symptoms of clinical recurrence, will continue to monitor with q6 month skin exams. REVIEW_Y1: Reviewed with patient signs and symptoms of clinical recurrence, will continue to monitor with q1 year skin exams. OTHER: other |

## Appendix E - Ophth Usage

| Value | Description |
|---|---|
| G_BIFOCAL | (Glasses) Bifocal |
| G_COMPUTER_MULTIFOCAL | (Glasses) Computer multifocal |
| G_COMPUTER_OVER_CONTACTS | (Glasses) Computer over contacts |
| G_COMPUTER_SINGLE_VISION | (Glasses) Computer single vision |
| G_DISTANCE_SINGLE_VISION | (Glasses) Distance single vision |
| G_DRIVING | (Glasses) Driving |
| G_DRIVING_OVER_CONTACTS | (Glasses) Driving over contacts |
| G_FULL_TIME | (Glasses) Full time wear |
| G_MULTIFOCAL | (Glasses) Multifocal |
| G_MULTIFOCAL_OVER_CONTACTS | (Glasses) Multifocal over contacts |
| G_OCCUPATIONAL | (Glasses) Occupational |
| G_OTC_READERS | (Glasses) OTC readers |
| G_PROGRESSIVE | (Glasses) Progressive |
| G_READING_OVER_CONTACTS | (Glasses) Reading over contacts |
| G_READING_SINGLE_VISION | (Glasses) Reading single vision |
| G_SAFETY | (Glasses) Safety |
| G_SPORTS_HOBBY | (Glasses) Sports/hobby |
| G_SUNGLASSES_MULTIFOCAL | (Glasses) Sunglasses multifocal |
| G_SNGLASSES_SINGLE_VISION | (Glasses) Sunglasses single vision |
| G_TRIFOCAL | (Glasses) Trifocal |
| CL_DISTANCE | (Contacts) Distance |
| CL_MONOVISION | (Contacts) Monovision |
| CL_MONOVISION_OD_DISTANCE | (Contacts) Monovision OD distance |
| CL_MONOVISION_OS_DISTANCE | (Contacts) Monovision OS distance |
| CL_MONOVISION_OD_NEAR | (Contacts) Monovision OD near |
| CL_MONOVISION_OS_NEAR | (Contacts) Monovision OS near |
| CL_MULTIFOCAL | (Contacts) Multifocal |
| CL_OCCUPATIONAL | (Contacts) Occupational |
| CL_SPORTS_HOBBY | (Contacts) Sports/hobby |
| MULTIFOCAL | (Both -old data) Multifocal |
| DISTANCE | (Both -old data) Distance |
| READING | (Both -old data) Reading |
| DRIVING | (Both -old data) Driving |
| SPORTS | (Both -old data) Sports |
| READING_SINGLE_VISION | (Both -old data) Reading Single Vision |
| COMPUTER_SINGLE_VISION | (Both -old data) Computer Single Vision |
| DISTANCE_SINGLE_VISION | (Both -old data) Distance Single Vision |
| BIFOCAL_WITH_FAR_CONTACTS | (Both -old data) Bifocal with Far Contacts |
| BIFOCAL_WITH_NEAR_CONTACTS | (Both -old data) Bifocal with Near Contacts |
| COMPUTER_OVER_CONTACTS | (Both -old data) Computer over Contacts |
| DRIVING_OVER_CONTACTS | (Both -old data) Driving over Contacts |
| OCCUPATIONAL | (Both -old data) Occupational |
| SUNGLASSES | (Both -old data) Sunglasses |
| FINAL_REFRACTION_RX | (Both -old data) Final Refraction Rx |
| OVER_REFRACTION | (Both -old data) Over-refraction |

## Appendix F - Visual Acuity

| Unnamed: 0 | Unnamed: 1 | Unnamed: 2 | Unnamed: 3 | Unnamed: 4 | Unnamed: 5 | Unnamed: 6 | Unnamed: 7 | Unnamed: 8 |
|---|---|---|---|---|---|---|---|---|
| Column Names |  |  |  |  |  |  |  |  |
| All visual acuity fields have a 6-character suffix (including underscore) indicating the nature of the visual acuity test |  |  |  |  |  |  |  |  |
| Character | 1 | 2 | 3 | 4 | 5 | 6 |  |  |
|  | N: near D: distance | s: uncorrected c: corrected | c | _ | O | D: right eye S: left eye U: both eyes |  |  |
| For example, a column named: visual_acuity_dcc_od reads "Visual Acuity - Distance, Corrected, Right eye" |  |  |  |  |  |  |  |  |
| All combinations: |  |  |  |  |  |  |  |  |
| Column suffix | Description |  |  |  |  |  |  |  |
| _dcc_od | Distance, Corrected, Right eye |  |  |  |  |  |  |  |
| _dcc_os | Distance, Corrected, Left eye |  |  |  |  |  |  |  |
| _dcc_ou | Distance, Corrected, Both eyes |  |  |  |  |  |  |  |
| _ncc_od | Near, Corrected, Right eye |  |  |  |  |  |  |  |
| _ncc_os | Near, Corrected, Left eye |  |  |  |  |  |  |  |
| _ncc_ou | Near, Corrected, Both eyes |  |  |  |  |  |  |  |
| _dsc_od | Distance, Uncorrected, Right eye |  |  |  |  |  |  |  |
| _dsc_os | Distance, Uncorrected, Left eye |  |  |  |  |  |  |  |
| _dsc_ou | Distance, Uncorrected, Both eyes |  |  |  |  |  |  |  |
| _nsc_od | Near, Uncorrected, Right eye |  |  |  |  |  |  |  |
| _nsc_os | Near, Uncorrected, Left eye |  |  |  |  |  |  |  |
| _nsc_ou | Near, Uncorrected, Both eyes |  |  |  |  |  |  |  |
| Distance Values |  |  |  |  |  |  |  |  |
| All values can have a plus or minus value appended to it (i.e. +1, -3, etc.) |  |  |  |  |  |  |  |  |
| Value | Chart Value | Description | Abbreviation | Metre | Decimal | LogMAR | SNOMED |  |
| V20_10 | 10 | 20/10 | 20/10 | 6/3 | 2 | -0.3 | 423862000 |  |
| V20_12_5 | 12.5 | 20/12.5 | 20/12.5 | 6/3.8 | 1.6 | -0.2 | 423862000 |  |
| V20_15 | 15 | 20/15 | 20/15 | 6/4.5 | 1.33 | -0.12 | 423862000 |  |
| V20_16 | 16 | 20/16 | 20/16 | 6/4.8 | 1.25 | -0.1 | 422497000 |  |
| V20_20 | 20 | 20/20 | 20/20 | 6/6 | 1 | 0 | 422497000 |  |
| V20_25 | 25 | 20/25 | 20/25 | 6/7.5 | 0.8 | 0.1 | 424703005 |  |
| V20_30 | 30 | 20/30 | 20/30 | 6/9 | 0.67 | 0.18 | 424703005 |  |
| V20_32 | 32 | 20/32 | 20/32 | 6/9.6 | 0.63 | 0.2 | 423059004 |  |
| V20_40 | 40 | 20/40 | 20/40 | 6/12 | 0.5 | 0.3 | 423059004 |  |
| V20_50 | 50 | 20/50 | 20/50 | 6/15 | 0.4 | 0.4 |  |  |
| V20_60 | 60 | 20/60 | 20/60 | 6/18 | 0.33 | 0.48 |  |  |
| V20_63 | 63 | 20/63 | 20/63 | 6/18.9 | 0.32 | 0.5 |  |  |
| V20_70 | 70 | 20/70 | 20/70 | 6/21 | 0.29 | 0.54 |  |  |
| V20_80 | 80 | 20/80 | 20/80 | 6/24 | 0.25 | 0.6 |  |  |
| V20_100 | 100 | 20/100 | 20/100 | 6/30 | 0.2 | 0.7 |  |  |
| V20_125 | 125 | 20/125 | 20/125 | 6/38 | 0.16 | 0.8 |  |  |
| V20_150 | 150 | 20/150 | 20/150 | 6/45 | 0.13 | 0.88 |  |  |
| V20_160 | 160 | 20/160 | 20/160 | 6/48 | 0.125 | 0.9 |  |  |
| V20_200 | 200 | 20/200 | 20/200 | 6/80 | 0.1 | 1 |  |  |
| V20_250 | 250 | 20/250 | 20/250 | 6/75 | 0.08 | 1.1 |  |  |
| V20_300 | 300 | 20/300 | 20/300 | 6/90 | 0.07 | 1.18 |  |  |
| V20_320 | 320 | 20/320 | 20/320 | 6/96 | 0.063 | 1.2 |  |  |
| V20_400 | 400 | 20/400 | 20/400 | 6/120 | 0.05 | 1.3 |  |  |
| V20_500 | 500 | 20/500 | 20/500 | 6/150 | 0.04 | 1.4 |  |  |
| V20_630 | 630 | 20/630 | 20/630 | 6/190 | 0.032 | 1.5 |  |  |
| V20_800 | 800 | 20/800 | 20/800 | 6/240 | 0.025 | 1.6 |  |  |
| COUNTING_FINGERS_10 | 1000 | Counting Fingers 10ft | CF@10ft | CF@10ft | CF@10ft | CF@10ft |  |  |
| COUNTING_FINGERS_9 | 1000 | Counting Fingers 9ft | CF@9ft | CF@9ft | CF@9ft | CF@9ft |  |  |
| COUNTING_FINGERS_8 | 1000 | Counting Fingers 8ft | CF@8ft | CF@8ft | CF@8ft | CF@8ft |  |  |
| COUNTING_FINGERS_7 | 1000 | Counting Fingers 7ft | CF@7ft | CF@7ft | CF@7ft | CF@7ft |  |  |
| COUNTING_FINGERS_6 | 1000 | Counting Fingers 6ft | CF@6ft | CF@6ft | CF@6ft | CF@6ft |  |  |
| COUNTING_FINGERS_5 | 1000 | Counting Fingers 5ft | CF@5ft | CF@5ft | CF@5ft | CF@5ft |  |  |
| COUNTING_FINGERS_4 | 1000 | Counting Fingers 4ft | CF@4ft | CF@4ft | CF@4ft | CF@4ft |  |  |
| COUNTING_FINGERS_3 | 1000 | Counting Fingers 3ft | CF@3ft | CF@3ft | CF@3ft | CF@3ft |  |  |
| COUNTING_FINGERS_2 | 1000 | Counting Fingers 2ft | CF@2ft | CF@2ft | CF@2ft | CF@2ft |  |  |
| COUNTING_FINGERS_1 | 1000 | Counting Fingers 1ft | CF@1ft | CF@1ft | CF@1ft | CF@1ft |  |  |
| HAND_MOTION | 1000 | Hand Motion | HM | HM | HM | HM |  |  |
| LIGHT_PERCEIVE | 1000 | Light Perception | LP | LP | LP | LP |  |  |
| NO_LIGHT_PERCEIVE | 1000 | No Light Perception | NLP | NLP | NLP | NLP |  |  |
| NI | 0 | No Improvement | NI |  |  |  |  |  |
| NONE | 0 | Not Available |  |  |  |  |  |  |
| OTHER | 0 | Other |  |  |  |  |  |  |
| Near Values |  |  |  |  |  |  |  |  |
| All values can have a plus or minus value appended to it (i.e. +1, -3, etc.) |  |  |  |  |  |  |  |  |
| Value | Description | Jaeger | Abbrev | Points | Mnote | Metre | Decimal | LogMAR |
| J1_PLUS | 20/20 | J1+ | J1+ | 3 | 0.4 | 6/6 | 1 | 0 |
| J1 | 20/25 | J1 | J1 | 4 | 0.5 | 6/7.5 | 0.8 | 0.1 |
| J2 | 20/30 | J2 | J2 | 5 | 0.6 | 6/9.0 | 0.67 | 0.18 |
| J3 | 20/32 | J3 | J3 | 6 | 0.64 | 6/9.6 | 0.63 | 0.2 |
| J4 | 20/40 | J4 | J4 | 7 | 0.8 | 6/12 | 0.5 | 0.3 |
| J5 | 20/50 | J5 | J5 | 8 | 1 | 6/15 | 0.4 | 0.4 |
| J6 | 20/60 | J6 | J6 | 9 | 1.2 | 6/18 | 0.33 | 0.48 |
| J7 | 20/63 | J7 | J7 | 10 | 1.3 | 6/18.9 | 0.32 | 0.5 |
| J8 | 20/80 | J8 | J8 | 11 | 1.6 | 6/24 | 0.25 | 0.6 |
| J9 | 20/100 | J9 | J9 | 12 | 2 | 6/30 | 0.2 | 0.7 |
| J10 | 20/114 | J10 | J10 | 13 | 2.3 | 6/34.2 | 0.18 | 0.76 |
| J11 | 20/125 | J11 | J11 | 14 | 2.5 | 6/37.5 | 0.16 | 0.8 |
| J12 | 20/160 | J12 | J12 | 21 | 3.2 | 6/48 | 0.13 | 0.9 |
| J13 | 20/200 | J13 | J13 | 23 | 4 | 6/80 | 0.1 | 1 |
| J14 | 20/250 | J14 | J14 | 24 | 5 | 6/96 | 0.08 | 1.1 |
| NI | No Improvement | No Improvement | NI |  |  |  |  |  |
| NONE | None | None | None |  |  |  |  |  |
| OTHER |  | Other | Other |  |  |  |  | ; |

## Appendix G - Visit Bill As

| Code | Description |
|---|---|
| NEW_PATIENT | New Patient |
| ESTABLISHED_PATIENT | Established Patient |
| OUTPATIENT_CONSULTATION | Outpatient Consultation - Non-Medicare Only |
| INPATIENT_CONSULTATION | Inpatient Consultation - Non-Medicare Only |
| NURSING_HOME_NEW_PATIENT | Nursing Home - New Patient |
| ASSISTED_LIVING_NEW_PATIENT | Assisted Living - New Patient |
| PRIVATE_HOME_VISIT_NEW_PATIENT | Private Home Visit - New Patient |
| NURSING_HOME_ESTABLISHED_PATIENT | Nursing Home - Established Patient |
| ASSISTED_LIVING_ESTABLISHED_PATIENT | Assisted Living - Established Patient |
| PRIVATE_HOME_VISIT_ESTABLISHED_PATIENT | Private Home Visit - Established Patient |

## Appendix H - Hpi Follow Up

| Value | Description |
|---|---|
| CRYOTHERAPY | Cryotherapy |
| ED_C | Electrodesiccation and Curettage |
| EXCISION | Excision |
| FOCUSED_VISIT | Focused Visit |
| FURTHER_EVALUATION_AND_MANAGEMENT | Further evaluation and Management |
| MOHS | Mohs |
| SKIN_CHECK | Skin Check |
| MELANOMA_CHECK | Melanoma Check |
| SKIN_CANCER_SURVEILLANCE | Skin Cancer Surveillance |
| SUTURE_REMOVAL | Suture Removal |
| TREATMENT | Treatment |
| WOUND_CHECK | Wound Check |
| BOTOX | Botulinum Toxin Injection |
| BIOLOGIC_THERAPY | Biologic Therapy |
| BIOPSY | Biopsy |
| BLOODWORK | Bloodwork |
| CHEMICAL_PEEL | Chemical Peel |
| CONFIRMATION_SITE | Confirmation of Site Prior to Surgery |
| COUNSELING | Counseling |
| COSMETIC_CONSULT | Cosmetic Consultation |
| DISCUSS_TEST | Discussion of Test Results |
| FILLERS | Fillers Injection |
| FOLLOW_UP_EVAL | Follow Up Evaluation |
| HIGHRISK_MONITOR | High Risk Medication Monitoring |
| LASER | Laser Treatment |
| INTRALESIONAL_KENALOG | Intralesional Kenalog |
| MEDICAL_PHOTO | Medical Photography |
| PATCH_TEST | Patch Testing |
| PATCH_TEST_RD | Patch Test Reading |
| PDT | Photodynamic Therapy |
| PHOTOTHERAPY | Phototherapy |
| RX_REFILL | Prescription Refill |
| UNNABOOT | Unna Boot |
| VISIT_RECHECK | Visit to recheck site and discuss options |
| OTHER | Other |
