# NYC Yellow Taxi Trip Analytics
**Python Analytics Portfolio | Data Cleaning · EDA · Statistics · Regression**

Sahil Changotra • The Hague, Netherlands • April 2026

---

## 📋 Project Overview

| Field | Detail |
|---|---|
| Dataset | NYC Yellow Taxi Trip Records — Jan to Aug 2023 |
| Source | Kaggle — nagasai524/nyc-taxi-trip-records-from-jan-2023-to-jun-2023 |
| Rows | ~8 million trips |
| Stack | Python (Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, Scipy) |
| Environment | VS Code + Jupyter Notebooks |
| Target Roles | Data Analyst — JET SODA Amsterdam \| BOL Retail Media Netherlands \| DLL Eindhoven |

> 📦 **Note on Data:** Raw data file is not tracked in this repository (2.1GB — exceeds GitHub limit).
> Download from: https://www.kaggle.com/datasets/nagasai524/nyc-taxi-trip-records-from-jan-2023-to-jun-2023
> Place in `data/raw/` before running notebooks.

---

## 📁 Repository Structure

```
nyc-taxi-analytics/
├── notebooks/
│   ├── nb1_data_cleaning.ipynb       ← Phase 1: Loading, cleaning, validation
│   ├── nb2_eda_visualization.ipynb   ← Phase 2: Exploratory analysis & visualisation
│   ├── nb3_statistics_ab_testing.ipynb ← Phase 3: Hypothesis testing & A/B testing
│   └── nb4_regression_analysis.ipynb ← Phase 4: Linear & multiple regression
├── data/
│   ├── raw/                          ← Original CSV (not tracked — see note above)
│   ├── clean/                        ← Cleaned CSV exported from NB1 (not tracked)
│   └── README.md                     ← Data source and download instructions
├── outputs/                          ← Charts and figures exported from notebooks
├── .gitignore
└── README.md
```

---

## 🔬 PHASE 1 — Data Cleaning (NB1) 🔜 In Progress

**Objective:** Transform raw 8M row taxi dataset into a clean, analysis-ready DataFrame.

### Known Data Quality Issues
| Issue | Description | Fix Applied |
|---|---|---|
| Negative fare amounts | Trips with fare_amount < 0 | Drop rows |
| Zero trip distance | Trips where trip_distance = 0 | Drop rows |
| Zero passengers | passenger_count = 0 or NULL | Drop rows |
| Impossible passenger count | passenger_count > 6 | Drop rows |
| Invalid coordinates | Pickup/dropoff outside NYC bounding box | Drop rows |
| Timestamp anomalies | Dropoff before pickup time | Drop rows |
| Extreme fare outliers | Fares > 99th percentile | Cap or drop |
| Extreme distance outliers | Distance > 99th percentile | Cap or drop |
| Duplicate trips | Identical trip records | Drop duplicates |

### Features Engineered
| Feature | Description |
|---|---|
| trip_duration_mins | dropoff - pickup timestamp in minutes |
| pickup_hour | Hour of day (0–23) extracted from pickup timestamp |
| pickup_day_of_week | Day name (Monday–Sunday) |
| pickup_month | Month number |
| is_weekend | Boolean flag for Saturday/Sunday |
| speed_mph | trip_distance / (trip_duration_mins / 60) |
| tip_pct | tip_amount / fare_amount × 100 |

---

## 📊 PHASE 2 — EDA & Visualisation (NB2) 🔜 Pending

**Objective:** Understand patterns in NYC taxi demand, pricing, tipping and geography.

### Planned Analysis
- Trip distance and fare distributions (right-skewed — log transform)
- Peak hour and day-of-week demand patterns
- Monthly revenue trend Jan–Aug 2023
- Tip percentage by payment type and hour
- Speed analysis by time of day
- Borough-level pickup/dropoff heatmap
- Correlation matrix — which variables drive fare amount

---

## 🧪 PHASE 3 — Statistics & A/B Testing (NB3) 🔜 Pending

**Objective:** Apply statistical tests to validate business hypotheses.

### Planned Hypotheses
| # | Hypothesis | Test |
|---|---|---|
| H1 | Credit card trips have higher tip % than cash trips | Mann-Whitney U (one-tailed) |
| H2 | Weekend trips are longer (distance) than weekday trips | Two-sample t-test |
| H3 | Peak hour (7–9am, 5–7pm) trips have higher fares | Mann-Whitney U |
| H4 | Tip rate is independent of pickup hour | Chi-square test |
| H5 | A/B test — JFK airport trips vs non-airport trips: fare difference significant? | Two-sample t-test + Cohen's d |

### Statistical Methods
- Descriptive statistics (mean, median, std, IQR)
- Normality check (Shapiro-Wilk, Q-Q plots)
- Confidence intervals (95% CI for mean fare and tip)
- Two-sample t-test (parametric)
- Mann-Whitney U test (non-parametric)
- Chi-square test (categorical independence)
- Effect size (Cohen's d)
- A/B test framework with p-value interpretation

---

## 📈 PHASE 4 — Regression Analysis (NB4) 🔜 Pending

**Objective:** Build OLS regression models to predict fare amount (statsmodels — certification style).

### Models
| Model | Features | Expected R² |
|---|---|---|
| Simple OLS | trip_distance only | ~0.7 |
| Multiple OLS | distance + duration + passengers + hour | ~0.85 |
| Full OLS | + payment type + day of week + month | TBD |

### Assumption Checks
- Normality of residuals (histogram + Q-Q plot)
- Homoscedasticity (residuals vs fitted plot)
- Multicollinearity (VIF < 5 for all features)
- Independence (Durbin-Watson test)

---

## 🛠️ Tech Stack

| Tool | Usage |
|---|---|
| pandas | Data loading, cleaning, transformation |
| numpy | Numerical operations, array handling |
| matplotlib | Base visualisations |
| seaborn | Statistical plots, heatmaps |
| scipy.stats | t-tests, Mann-Whitney U, Chi-square, Shapiro-Wilk |
| statsmodels | OLS regression (certification style) |
| sklearn | VIF calculation, train/test split |

---

## 👤 About

| Field | Detail |
|---|---|
| Name | Sahil Changotra |
| Location | The Hague, Netherlands |
| GitHub | [github.com/sahilmchangotra](https://github.com/sahilmchangotra) |
| Tableau Public | [public.tableau.com/app/profile/sahil.changotra](https://public.tableau.com/app/profile/sahil.changotra) |
| Certification | Google Data Analytics Certificate |
| Target Roles | Data Analyst — JET SODA Amsterdam \| BOL Retail Media Netherlands \| DLL Eindhoven |