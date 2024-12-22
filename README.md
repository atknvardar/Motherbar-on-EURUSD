
## Overview
This project investigates the relationship between **personal trading performance** and **local weather conditions** to determine whether external environmental factors (e.g., temperature, precipitation, humidity) influence trading behaviors and outcomes.

The analysis aims to answer key questions:
- Do weather variables correlate with daily profit/loss (P/L)?
- Are there patterns in trading volume or risk-taking behavior based on weather conditions?
- Can weather data improve the prediction of trading outcomes?

---

## Table of Contents
1. [Data Sources](#data-sources)
2. [Objectives](#objectives)
3. [Methodology](#methodology)
4. [Key Findings](#key-findings)
5. [Limitations](#limitations)
6. [Future Work](#future-work)
7. [How to Run](#how-to-run)

---

## Data Sources
### 1. **Trading Data** (`trading_results.csv` and `trading_results_summary.csv`)
- **Columns**:
  - `Date`: Timestamp of trades (daily granularity).
  - `P/L`: Profit or loss for each trading day.
  - `Volume`: Total trading volume for the day.

### 2. **Weather Data** (`Istanbul,Turkey.csv`)
- **Columns**:
  - `Date`: Daily weather timestamps.
  - `Temperature`: Minimum, maximum, and average temperatures (°C).
  - `Precipitation`: Amount of rainfall (mm).
  - `Humidity`: Daily average (%).
  - `Conditions`: Categorical labels like "Sunny", "Rainy", or "Cloudy".

Both datasets are merged on the `Date` column for analysis.

---

## Objectives
1. **Exploratory Data Analysis (EDA)**:
   - Visualize P/L distributions and trading volumes.
   - Investigate weather trends during high-profit and low-profit days.

2. **Correlation Analysis**:
   - Analyze relationships between weather features (temperature, precipitation, humidity) and trading performance (P/L and volume).

3. **Predictive Modeling**:
   - Build regression models to predict daily P/L using weather features.
   - Explore classification models for "profitable" vs. "non-profitable" days.

---

## Methodology
1. **Preprocessing**:
   - Cleaned missing or inconsistent data in both trading and weather datasets.
   - Converted dates into consistent `datetime` formats.
   - Created derived features like:
     - Temperature Range = Max - Min Temperature.
     - Binary indicator for precipitation (Rainy = 1, Not Rainy = 0).

2. **Analysis Steps**:
   - **EDA**:
     - Time-series plots of daily P/L vs. temperature.
     - Scatter plots of P/L against weather features.
     - Boxplots comparing P/L for "Sunny" vs. "Rainy" days.
   - **Statistical Testing**:
     - Correlation coefficients (e.g., Pearson) for P/L and weather metrics.
     - T-tests to compare P/L distributions across weather conditions.
   - **Modeling**:
     - Linear regression to predict daily P/L.
     - Decision trees to classify profitable vs. non-profitable days.

---

## Key Findings
1. **Weather Influence on Trading**:
   - **Temperature**: Moderate correlation between daily P/L and average temperature.
   - **Precipitation**: Rainy days tended to have lower trading volumes but not significantly different P/L.
   - **Humidity**: No strong correlation with trading outcomes.

2. **Behavioral Patterns**:
   - Higher trading activity observed during sunny afternoons compared to rainy mornings.
   - Extreme weather conditions (e.g., storms) led to reduced trading activity.

3. **Predictive Modeling**:
   - Regression models showed mild predictive power (R² ~ 0.3) using weather data alone.
   - Combining trading volume with weather features improved predictions.

---

## Limitations
- **Data Gaps**: Missing weather data for certain trading days may affect correlations.
- **Sample Size**: Limited data reduces statistical power for predictive modeling.
- **Confounding Variables**: External factors (e.g., market trends, personal schedules) were not accounted for.

---

## Future Work
1. **Extended Data Collection**:
   - Incorporate additional trading data over longer periods to improve statistical robustness.
2. **Enhanced Features**:
   - Add market-level data (e.g., volatility indices, sentiment analysis) to complement weather metrics.
3. **Advanced Models**:
   - Explore time-series forecasting (ARIMA, LSTMs) with weather as an external feature.

---

## How to Run
### Prerequisites
- Python 3.8 or higher
- Required libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
