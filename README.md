# Morocco Electricity Consumption and Environmental Factors Analysis

**Track 2: Data Science | AnalystLab Africa Experience Lab Internship (Week 5)**

This project analyzes electricity consumption patterns across three geographical zones in Morocco alongside environmental variables using 10-minute interval data recorded from January 1, 2017 to December 30, 2017.

---

## Dataset Overview

* **Main Dataset:** `powerconsumption.csv` (52,416 records, 9 columns, recorded every 10 minutes across three zones).
* **Data Dictionary:** `powerconsumption_datadictionary.csv`
* **Key Fields:**
  * `Datetime` — Date and time of each 10-minute recording.
  * `Temperature` — Temperature in Celsius (°C).
  * `Humidity` — Concentration of water vapor in the air.
  * `WindSpeed` — Wind speed in kilometers per hour (km/h).
  * `GeneralDiffuseFlows` — Measurement of how much emission gases diffuse into the broader atmosphere.
  * `DiffuseFlows` — Measurement of how much emission gases diffuse into the local atmosphere.
  * `PowerConsumption_Zone1`, `PowerConsumption_Zone2`, `PowerConsumption_Zone3` — Power consumption in Kilowatt-Hours (kWh) for each zone.

---

## Repository Structure

```text
Week 5-Charity Nduati-Data Science/
├── README.md
├── Week5_Morocco_Power_Consumption_DataScience.ipynb
├── powerconsumption.csv
├── powerconsumption_datadictionary.csv
└── report.pdf