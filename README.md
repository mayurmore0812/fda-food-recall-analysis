# FDA Food Recall Analysis
Historical food-enforcement analysis with distinct product-record and recall-event measures.

**Author:** Mayur More · **Context:** Academic project; not FDA-commissioned or endorsed.

[Python Notebook and Code](FDA_Food_Recall_Analysis.ipynb) · [Results](docs/RESULTS.md) · [Data & citations](docs/DATA.md) · [Methods](docs/METHODS.md)

## Project question
How do recorded workload, supplied issue categories, recalling-firm locations, initial notification and historical statuses vary?

The snapshot has **22,840 records** and **5,875 events**, with report dates **20 June 2012–31 August 2022**. Complete-year comparisons use 2013–2021.

![Annual recorded workload](docs/assets/annual-workload.png)

Preview generated from the same historical master CSV; grey bars mark partial reporting years.

## Contributions
Reconciliation of labelled tables with master records, explicit units, ten analytical questions, chart presentation and qualified interpretation. Supplied labels and inherited cleaning come from the cited dataset/case study; see [contributions](docs/CONTRIBUTIONS.md).

## Selected historical findings
| Measure | Result |
|---|---:|
| Product-record peak, complete years | 3,203 in 2017 |
| Event peak, complete years | 782 in 2016 |
| Class II records | 11,681 (51.1%) |
| Single-record events | 3,760 (64.0%) |

## Ten questions, charts and answers

These static PNGs render the notebook’s existing saved Plotly figures. The interactive notebook plots remain unchanged. Scrolling rankings are expanded to show every entry; these images do not support hover or filtering. Results describe the historical snapshot, not current recall activity.

### 1. How does workload vary by year?

![Chart for question 1: How does workload vary by year?](docs/assets/insight-01-annual-workload.png)

**Answer:** Product records peaked in 2017 with 3,203 records; distinct events peaked in 2016 with 782. These measure different aspects of recorded workload.

*Evidence: notebook cells 13 (saved chart) and 14 (interpretation); positions include Markdown cells.*

### 2. Which months were busiest on average?

![Chart for question 2: Which months were busiest on average?](docs/assets/insight-02-monthly-events.png)

**Answer:** April averages 56.9 distinct events, followed by December at 55.4, March at 53.8 and January at 36.9 across complete years 2013–2021. This does not establish that April was busiest every year or forecast future activity.

*Evidence: notebook cells 16 (saved chart) and 17 (interpretation); positions include Markdown cells.*

### 3. How broad is each recall event?

![Chart for question 3: How broad is each recall event?](docs/assets/insight-03-event-breadth.png)

**Answer:** 3,760 events (64.0%) contain one product record; another 24.1% contain two to five. In total, 88.1% contain at most five records. Record breadth does not measure physical units, severity or staff hours.

*Evidence: notebook cells 19 (saved chart) and 20 (interpretation); positions include Markdown cells.*

### 4. Which FDA class is most frequent?

![Chart for question 4: Which FDA class is most frequent?](docs/assets/insight-04-fda-classes.png)

**Answer:** Class II has 11,681 records (51.1%), Class I 9,916 (43.4%), and Class III 1,243 (5.4%). Classes I and II together comprise about 94.6%. Class I remains the highest hazard classification despite Class II being more frequent.

*Evidence: notebook cells 22 (saved chart) and 23 (interpretation); positions include Markdown cells.*

### 5. Which categories recur most?

![Chart for question 5: Which categories recur most?](docs/assets/insight-05-issue-categories.png)

**Answer:** Materials, allergens and labelling is associated with 3,172 events; Biological issues with 1,716. These are supplied categories. Their counts overlap and do not estimate consumer risk.

*Evidence: notebook cells 25 (saved chart) and 26 (interpretation); positions include Markdown cells.*

### 6. Which reasons recur most?

![Chart for question 6: Which reasons recur most?](docs/assets/insight-06-recall-reasons.png)

**Answer:** Undeclared or mislabeled products is associated with 1,881 events; other frequent supplied reasons include Allergen issues (738), L. monocytogenes (703), Salmonella (702) and Foreign Material (576). Labels are inherited from the cited source; counts can overlap.

*Evidence: notebook cells 28 (saved chart) and 29 (interpretation); positions include Markdown cells.*

### 7. Where are US firms located?

![Chart for question 7: Where are US firms located?](docs/assets/insight-07-us-firm-locations.png)

**Answer:** California is associated with 973 events, New York 483, Texas 359, New Jersey 337 and Illinois 280. These concern recalling-firm locations, not consumer exposure. Events may span multiple locations.

*Evidence: notebook cells 31 (saved chart) and 32 (interpretation); positions include Markdown cells.*

### 8. Which non-US countries lead?

![Chart for question 8: Which non-US countries lead?](docs/assets/insight-08-non-us-firm-locations.png)

**Answer:** Canada leads non-US firm locations with 48 events, followed by France. Firm-location counts do not measure country risk.

*Evidence: notebook cells 34 (saved chart) and 35 (interpretation); positions include Markdown cells.*

### 9. How do methods differ by class?

![Chart for question 9: How do methods differ by class?](docs/assets/insight-09-initial-notification.png)

**Answer:** Multiple methods is the most frequent initial-notification label: 45.3% of Class I, 31.9% of Class II and 35.2% of Class III records. This does not establish communication effectiveness or the full communication history.

*Evidence: notebook cells 37 (saved chart) and 38 (interpretation); positions include Markdown cells.*

### 10. What statuses were recorded?

![Chart for question 10: What statuses were recorded?](docs/assets/insight-10-historical-status.png)

**Answer:** Historical labels are Terminated 21,261 (93.1%), Ongoing 1,285 (5.6%) and Completed 294 (1.3%). They do not establish current status or effectiveness. The [openFDA overview](https://open.fda.gov/apis/food/enforcement/) warns against using this endpoint to track recall lifecycle.

*Evidence: notebook cells 40 (saved chart) and 41 (interpretation); positions include Markdown cells.*

## Run locally
Use Python 3.12. Start from this repository folder:
1. Create an environment: `python -m venv .venv`
2. Activate: Windows PowerShell `.\.venv\Scripts\Activate.ps1`; macOS/Linux `source .venv/bin/activate`
3. Install the checked environment: `python -m pip install -r requirements.txt`.
4. Obtain the compatible dataset using [DATA.md](docs/DATA.md); place archive.zip beside the notebook.
5. Launch `python -m jupyterlab`; open the notebook and Restart Kernel / Run All.

Six required CSVs must be at the archive root. The notebook does not require an API key. A current API extract alone will not reconstruct the supplied category/reason files.

## Viewing charts
The ten PNG charts above display directly in GitHub’s README. GitHub notebook previews may not display the saved Plotly/iframe outputs. [Download the HTML report](reports/FDA_Food_Recall_Analysis.html) and open the downloaded file in a browser for Plotly hover and scrolling charts. No separate dashboard edition or hosted live demo is included.

## Interpretation
This historical snapshot is not a live recall tracker. Firm location is not consumer-exposure geography. Counts do not establish risk, causality, staff hours, inspection need or communication effectiveness. Categories and event subtotals across periods/locations may overlap. Status is historical; openFDA warns against tracking recall lifecycle with its endpoint.

## Sources and reuse
- [Kaggle dataset](https://www.kaggle.com/datasets/chiyucheng/fda-food-enforcement-20082022).
- [Case study](https://www.kaggle.com/code/chiyucheng/fda-food-recall-case-study).
- [FDA definitions](https://www.fda.gov/safety/enforcement-reports/enforcement-report-information-and-definitions).
- [openFDA overview](https://open.fda.gov/apis/food/enforcement/).

Raw data is excluded. Kaggle metadata lists the dataset as CC0. The inherited case-study code-licence scope still needs confirmation.  No blanket open-source licence is asserted.
