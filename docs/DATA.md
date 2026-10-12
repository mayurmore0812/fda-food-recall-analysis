# Data provenance, acquisition and dictionary
## Citation and lineage
Cheng (Kaggle username chiyucheng). *FDA Food Enforcement 2008–2022* [Dataset]. [Kaggle](https://www.kaggle.com/datasets/chiyucheng/fda-food-enforcement-20082022).

Cheng / chiyucheng. *FDA Food Recall Case Study*. [Kaggle](https://www.kaggle.com/code/chiyucheng/fda-food-recall-case-study): supplied labels and inherited cleaning. The original project cites Cheng (2022); publication/version and original acquisition dates still need confirmation.

Original source: U.S. Food and Drug Administration, [food enforcement overview](https://open.fda.gov/apis/food/enforcement/) and [definitions](https://www.fda.gov/safety/enforcement-reports/enforcement-report-information-and-definitions). References checked 12 October 2026.

Kaggle's public dataset API, checked 12 October 2026, lists this dataset as CC0: Public Domain, current version 3, last updated 27 October 2022. See [recorded metadata](source-metadata.json). This does not establish which version the historical local archive came from, or the licence of case-study code. Raw data remains excluded for a small, focused release. Confirm inherited-code terms before assigning a code licence.

## Obtain compatible data
Download through the Kaggle dataset page; login or acceptance of source terms may be required. Name the ZIP archive.zip and place it beside the notebook. Required root-level entries:
- food_enforcement.csv: master product records.
- bio_contamination.csv, chemical_contamination.csv, material_contamination.csv, admin_failure.csv: supplied labelled subsets.
- combined.csv: their union.


The September 2022 snapshot is described in original project prose; it is not a verified acquisition timestamp. The Kaggle title is broader than actual local report dates. Current API data is not a drop-in replacement for enriched category files.

## Dictionary
| Fields | Meaning |
|---|---|
| event_id | Recall-event count key. |
| recall_number | Product recall identifier, distinct from event ID. |
| report_date | Reporting date used for year/month measures. |
| recall_initiation_date, center_classification_date, termination_date | Other source dates, not reporting-date substitutes. |
| classification | Product hazard class; category-file codes decode as 3→I, 2→II, 1→III. |
| status | Historical label, not verified current status. |
| recalling_firm | Recalling firm. |
| city, state, country, address_1, address_2, postal_code | Firm geography, not consumer exposure. |
| initial_firm_notification | Initial method, not full communication history. |
| voluntary_mandated | Source initiation type. |
| distribution_pattern | Described distribution, not exposure denominator. |
| product_description, product_quantity, code_info | Product/quantity/code text; rows are not physical units. |
| reason_for_recall | Source reason text. |
| reason_for_recall_simplified | Extra supplied field in labelled files, not original annotation by this project's author. |

Empty, NA and N/A strings are treated as missing. Master rows are retained, including unlabelled records. Deduplicated category/reason membership prevents duplicate annotation counting.
