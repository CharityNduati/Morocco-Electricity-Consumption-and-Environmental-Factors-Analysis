# Morocco Electricity Consumption and Environmental Factors Analysis

**Track 2: Data Science | AnalystLab Africa Experience Lab Internship (Week 5)**

This project applies statistical analysis and time-series techniques to examine electricity consumption across three geographical zones in Morocco alongside environmental variables, using 10-minute observations collected from **January 1, 2017 to December 30, 2017**. The workflow follows the **CRISP-DM** methodology with clear, plain-language explanations and interpretations after every visual and statistical test.

---

## Methodology (CRISP-DM Framework)

1. **Business Understanding:** Frame grid and load-management questions across three consumption zones for an energy management organization in Morocco.
2. **Data Understanding:** Inspect `powerconsumption.csv` (52,416 rows, 9 columns) and `powerconsumption_datadictionary.csv`, verifying zero missing values and zero duplicates.
3. **Data Preparation:** Parse `Datetime`, confirm consistent 10-minute intervals, create calendar features (`Hour`, `DayOfWeek`, `Month`), and aggregate into hourly and daily averages.
4. **Modeling & Statistical Analysis:** Compute descriptive statistics (mean, median, min, max, standard deviation, variance, quartiles, IQR, skewness), perform additive time-series decomposition, test Pearson and Spearman correlations with weather variables, and compare zones using ANOVA and Kruskal-Wallis tests.
5. **Evaluation & Limitations:** Account for large-sample $p$-values, time-series autocorrelation, correlation versus causation, and single-year (2017) dataset scope.
6. **Deployment & Recommendations:** Translate insights into practical evening peak, summer readiness, and zone-level planning recommendations.

---

## Dataset & Data Dictionary Notes

* **`powerconsumption.csv`:** 52,416 records at 10-minute intervals (`2017-01-01 00:00:00` to `2017-12-30 23:50:00`).
* **`powerconsumption_datadictionary.csv`:**
  * `Datetime` — Date and time of each recording.
  * `Temperature` — Temperature in Celsius ($^\circ\text{C}$).
  * `Humidity` — Concentration of water vapor in the air.
  * `WindSpeed` — Wind speed in kilometers per hour ($\text{km/h}$).
  * `GeneralDiffuseFlows` — Measurement of how much emission gases diffuse into the broader atmosphere.
  * `DiffuseFlows` — Measurement of how much emission gases diffuse into the local atmosphere.
  * `PowerConsumption_Zone1`, `PowerConsumption_Zone2`, `PowerConsumption_Zone3` — Power consumption in Kilowatt-Hours ($\text{kWh}$) per zone.
* **Aggregation Rule:** Because readings are recorded at 10-minute intervals in $\text{kWh}$, **averages (means)** are used to summarize typical hourly, daily, and monthly demand rather than summing every 10-minute row into an inflated total.

---

## Repository / Submission Folder Structure

```text
Week 5-Charity Nduati-Data Science/
├── README.md
├── Week5_Morocco_Power_Consumption_DataScience.ipynb
├── powerconsumption.csv
├── powerconsumption_datadictionary.csv
└── Week5_Morocco_Power_Consumption_Report.pdf
```

---

## Key Findings & Recommendations

* **Zone Comparison:** **Zone 1** has the highest average consumption (**32,344.97 kWh**) and widest spread (**Std = 7,130.56 kWh**, **IQR = 10,998.35 kWh**), followed by **Zone 2** (**21,042.51 kWh**) and **Zone 3** (**17,835.41 kWh**, right-skewed at **1.02** with a July surge to **28,194.1 kWh**). ANOVA ($F = 75029.00, p < 0.001$) and Kruskal-Wallis ($H = 76069.59, p < 0.001$) confirm significant differences across zones.
* **Time-Series Cycles:** Consumption is lowest in early morning hours (**5:00–7:00**), peaks in the evening (**19:00–21:00**, with Zone 1 peaking at hour 20 at **43,822.6 kWh**), dips slightly on Sundays, and rises during **July–August**.
* **Environmental Associations:** Temperature shows a moderate positive correlation with consumption (e.g., Zone 1 Pearson $r = 0.444$, Spearman $\rho = 0.435$), humidity shows a mild negative correlation, and wind speed shows a weak positive correlation.
* **Recommendations:** Prioritize evening peak capacity (**19:00–21:00**), prepare grid maintenance and cooling load readiness ahead of **July–August**, and tailor zone-level planning while noting single-year (2017) data limits and correlation versus causation.

---

## How to Run Locally

1. **Clone the repository and enter the folder:**
   ```bash
   git clone https://github.com/CharityNduati/Morocco-Electricity-Consumption-and-Environmental-Factors-Analysis
   cd "Week 5-Charity Nduati-Data Science"
   ```
2. **Install required libraries:**
   ```bash
   pip install pandas numpy scipy statsmodels matplotlib seaborn plotly jupyter
   ```
3. **Run the notebook:**
   ```bash
   jupyter notebook
   ```
   Open `Week5_Morocco_Power_Consumption_DataScience.ipynb` and run all cells from top to bottom.

---

## Author

**Charity Nduati**  
Data Science & Analytics | AnalystLab Africa Experience Lab Internship
