# Optimising NYC Taxi Operations | Exploratory Data Analysis

**Python · Pandas · NumPy · Matplotlib · Seaborn · Geospatial Analysis**

An exploratory data analysis of **2023 New York City Yellow Taxi trips**, examining demand patterns, operational inefficiencies, geographic demand, fares, and payment behaviour. The objective is to turn trip-level data into practical recommendations for taxi dispatching, vehicle positioning, and pricing.

> **Project context:** Completed as an individual exploratory data analysis assignment for upGrad. This repository presents an educational case study, not work commissioned by the NYC Taxi & Limousine Commission or a taxi operator.

## Project overview

New York City's taxi demand changes by location, hour, weekday, and season. This project explores how a taxi operator could use historical trip data to:

- Anticipate peak demand and allocate vehicles more effectively.
- Identify high-demand pickup zones and pickup/drop-off imbalances.
- Examine slow routes and differences between weekday and weekend travel.
- Compare fare-per-mile patterns, payment methods, tips, and surcharges.
- Translate analytical findings into actionable operational recommendations.

## Dataset and approach

The analysis uses the **12 monthly NYC Yellow Taxi trip-record files for 2023** and NYC taxi-zone geographic data. To keep processing manageable, the notebook samples **0.75% of trips within each date-and-pickup-hour group** and combines the monthly samples.

The working sample contains approximately **284,000 trips**. The analysis includes:

1. **Data preparation:** Hourly stratified sampling and consolidation of monthly files.
2. **Data cleaning:** Consolidation of duplicate airport-fee columns; examination of missing values, unusual records, and trip-reporting categories.
3. **General EDA:** Pickup distributions by time, monthly and quarterly revenue, relationships between trip distance and fares, payment types, and zone-level pickup maps.
4. **Detailed EDA:** Route speeds, peak-hour demand, weekday/weekend patterns, zone imbalances, nighttime activity, vendor fare comparisons, tips, passenger counts, and surcharge patterns.
5. **Recommendations:** Dispatch scheduling, strategic cab positioning, and data-informed pricing considerations.

### Data-quality decisions

The notebook documents assumptions and cleaning choices rather than automatically discarding all unusual records. For example, **payment type 0 (Flex Fare)** is retained as a distinct category. Implausible combinations of near-zero distances and extreme fares, among other flagged records, are investigated and filtered according to documented rules.

## Selected findings

| Area | Observation | Operational implication |
|---|---|---|
| Peak demand | **6 PM** was the busiest pickup hour in the analysed sample. | Increase vehicle availability ahead of the evening peak. |
| Weekly patterns | Weekday demand has stronger commute-related peaks; weekend demand is more gradual. | Use separate weekday and weekend dispatch schedules. |
| Geographic demand | **JFK Airport** and several **Midtown/Upper East Side** zones feature prominently among pickup hotspots. | Position vehicles according to both zone and time of day. |
| Nighttime demand | Nighttime hotspots include **East Village, JFK Airport, and West Village**. | Adjust overnight vehicle distribution. |
| Fare patterns | Fare amount rises strongly with trip distance; fare per mile varies across distance tiers and vendors. | Benchmark pricing by trip length and market segment. |
| Payment behaviour | Credit cards dominate the recorded payment methods, followed by cash. | Interpret recorded tip data with awareness that cash tips are not captured. |

These are **descriptive findings from the sampled records**, not causal estimates. Extremely low calculated route speeds may reflect waiting or idle time as well as congestion.

## Tools and techniques

- **Python:** Data preparation and analysis
- **Pandas and NumPy:** Sampling, cleaning, aggregation, and derived metrics
- **Matplotlib and Seaborn:** Statistical and operational visualisations
- **GeoPandas:** NYC taxi-zone joins and geographic visualisation
- **Jupyter Notebook / Google Colab:** Reproducible analytical workflow

Derived measures include trip duration, hourly trip volume, average route speed, pickup/drop-off ratios, fare per mile, tip percentage, and day-versus-night revenue share.

## Repository contents

```text
.
├── README.md
├── EDA_Optimising_NYC_Taxis_Ayesha_Siddiqha.ipynb
└── EDA_Optimising_NYC_Taxis_Ayesha_Siddiqha.pdf
```

- **Notebook:** Complete analysis, code, visualisations, and explanatory comments. It retains the original assignment prompts and marking annotations.
- **PDF report:** Methodology, assumptions, visualisations, results, and business recommendations.

## How to explore the project

1. Read the **PDF report** for the analytical narrative and recommendations.
2. Open the **Jupyter notebook** on GitHub for the code and saved outputs.
3. To rerun the notebook, obtain the 2023 monthly Yellow Taxi trip files and taxi-zone shapefile, then update the notebook's **Google Drive/data paths** to match your environment. Run the cells in order.

**Data source and attribution:** [NYC Taxi & Limousine Commission — Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). The raw Parquet files and taxi-zone shapefile are **not redistributed** in this repository. Follow the dataset provider's terms when obtaining data.

## Limitations

- The analysis uses a stratified **sample**, so scaled trip totals are estimates.
- Missing fields and different trip-reporting categories can affect comparisons.
- Recorded tips do not include cash tips.
- Route speed estimates may be influenced by unusual trip durations and idle time.
- Recommendations are analytical proposals, not experimentally validated operational changes.

## Author

**Ayesha Siddiqha**  
AI/ML Engineer | Computer Vision | Machine Learning | Python

---

*Educational portfolio project based on an upGrad assignment and publicly documented NYC TLC trip-record data.*
