# Calgary-Traffic-Risk-Analysis
Predictive modeling and spatial analysis of traffic risks in Calgary.
# Machine Learning Models for Calgary’s Traffic Risks

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)
![Location](https://img.shields.io/badge/Focus-Calgary%2C%20AB-orange)

## Project Overview
As Calgary grows, traffic safety becomes a critical urban challenge. This project utilizes machine learning and spatial data science to analyze approximately **55,000 traffic incident records (2018–2024)**. By integrating weather patterns and traffic volume (AAWT), we developed a framework to identify high-risk road segments and predict the likelihood of pedestrian-involved incidents.

The project is divided into two core analytical tracks:
* **Part A:** Predictive Modeling for Pedestrian Involvement.
* **Part B:** Spatial Hotspot Identification & Risk Scoring.
  
---
## Data Sources
The analysis integrates multiple datasets from the **City of Calgary Open Data Portal**. Due to file size constraints, raw datasets are linked below:
### City of Calgary Open Data
* **[Traffic Incidents](https://data.calgary.ca/Transportation-Transit/Traffic-Incidents/35ra-9556/about_data)**: ~55,000 records (July 2022 – July 2025).
* **[Street Centreline](https://data.calgary.ca/Transportation-Transit/Street-Centreline/4dx8-rtm5/about_data)**: Detailed road segment geometry and classifications.
* **[Traffic Counts (AAWT)](https://data.calgary.ca/Transportation-Transit/Traffic-Counts-at-Permanent-stations/vuyp-sbjp/about_data)**: Volume data used for risk normalization.
* **[Permanent Station Locations](https://data.calgary.ca/Transportation-Transit/Permanent-station-locations-for-Traffic-counts/sqwx-tjsy/about_data)**: Geographic details for traffic sensors.
* **[Major Road Network](https://data.calgary.ca/Transportation-Transit/Major-Road-Network/tqjs-vnhy/about_data)**: Primary transportation corridors.

### External APIs
* **[Open-Meteo Historical API](https://open-meteo.com/en/docs)**: Sourced hourly weather parameters (snowfall, temperature, visibility) for Calgary.

*All City of Calgary data is used under the [Open Data Terms of Use](https://data.calgary.ca/d/Open-Data-Terms/u45n-7awa).*

---

## Key Findings

### Part A: Pedestrian Involvement Prediction
We addressed the significant class imbalance (950 pedestrian incidents vs. 21,560 non-pedestrian) to determine if environmental factors can predict pedestrian risk.
* **Best Model:** Balanced Random Forest Classifier.
* **Performance:** Achieved a **Recall of 0.828**, ensuring the model identifies the vast majority of high-risk scenarios.
* **Top Predictors:** Snowfall, temperature, and specific time-of-day windows (Rush Hour).

### Part B: Spatial Hotspot Analysis
Using Calgary's Street Centreline data, we mapped collision density across the city.
* **Imputation:** Developed a 2-tier nearest-station propagation logic to assign traffic volumes to 45,298 road segments.
* **Visualization:** Identified critical intersections and road classes (Primary Arterials) that contribute disproportionately to incident rates.
* **Validation:** Compared Unsupervised KDE (Kernel Density Estimation) with Supervised Random Forest risk probabilities.

---

## Repository Structure

```text
├── notebooks/
│   ├── PartA_Pedestrian_Prediction.ipynb   # Model training & evaluation
│   ├── PartB_Spatial_Analysis.ipynb        # Data engineering & spatial joins
│   └── Support_Weather_API_Fetch.ipynb      # API integration logic
├── reports/
│   ├── Project_Report.pdf        # Detailed technical document
│   └── Project_Presentation.pdf         # Summary slide deck
└── README.md
```

---

## Contributors & Team
This project was a collaborative effort.

* **Jincy Thomas** – [[LinkedIn Profile Link](https://www.linkedin.com/in/jincymarythomas/)]
* **Joshua Quartey** – [[LinkedIn Profile Link](https://www.linkedin.com/in/joshua-quart/)]
* **Megha Radhakrishnan** – [[LinkedIn Profile Link](https://www.linkedin.com/in/megha-rs/)]
* **Deepika Gollamandala** – [[LinkedIn Profile Link](https://www.linkedin.com/in/deepika-gollamandala-248166270/)]

---
