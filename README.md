# Trading vs. Weather Analysis &emsp;![Status](https://img.shields.io/badge/Status-Exploratory-blue) ![License](https://img.shields.io/badge/License-MIT-green)

> **Exploring whether weather conditions (temperature, humidity, precipitation) and time-based factors (weekdays, quarters, trade duration) influence trading outcomes.**

## Table of Contents
1. [Overview](#overview)  
2. [Data Sources](#data-sources)  
3. [Objectives](#objectives)  
4. [Methodology](#methodology)  
5. [Key Findings](#key-findings)  
6. [Limitations](#limitations)  
7. [Future Work](#future-work)  
8. [How to Run](#how-to-run)

---

<a name="overview"></a>
## 1. Overview

This project investigates how **personal trading performance** may be influenced by **local Istanbul weather data**. Specifically, we look at:

- Temperature (min/max/avg)  
- Precipitation (rainy vs. non-rainy days)  
- Humidity  
- Time-based elements (day of week, quarter, trading hours, trade duration)

**Goal**: Understand if these **external factors** can correlate with or even predict **daily profit/loss** and overall trading behavior.

> *Are sunny Fridays more profitable?*  
> *Does rain reduce trading volume?*  
> *Do mid-morning trades outperform late-afternoon trades?*

All these questions and more are explored through **visualizations**, **statistical tests**, and **predictive modeling**.

---

<a name="data-sources"></a>
## 2. Data Sources

1. **Trading Data**  
   - Files: `trading_results.csv` and `trading_results_summary.csv`  
   - Columns:  
     - `Date` (daily or intraday granularity)  
     - `P/L` (profit or loss)  
     - `Volume` (total volume per day if available)  
     - *Optional*: Execution times, trade duration, etc.

2. **Weather Data**  
   - File: `Istanbul,Turkey.csv`  
   - Columns:  
     - `Date`  
     - `Temperature` (min, max, avg)  
     - `Precipitation` (in mm)  
     - `Humidity` (%)  
     - `Conditions` (e.g., Sunny, Rainy, Cloudy)

Both datasets are **merged** on `Date` to align trading outcomes with daily weather conditions.

---

<a name="objectives"></a>
## 3. Objectives

1. **Exploratory Data Analysis (EDA)**  
   - Visualize profit distributions and volumes  
   - Investigate weather trends on high-profit vs. low-profit days  
   - Examine weekdays, quarters, trade hours, and trade durations

2. **Correlation Analysis**  
   - Check whether weather variables (temp, precipitation, humidity) align with P/L  
   - Assess significance of weekdays, quarters, or specific trading hours on performance

3. **Predictive Modeling**  
   - Build regression models (predict daily P/L)  
   - Explore classification (profitable vs. non-profitable)  
   - Evaluate impact of weather/time features on model accuracy

---

<a name="methodology"></a>
## 4. Methodology

1. **Data Preprocessing**  
   - Clean missing data in both trading and weather logs  
   - Convert dates to consistent datetime formats  
   - Derive features (e.g., `Temperature Range = TempMax - TempMin`, `Rain Indicator`, `Day of Week`, `Quarter`, etc.)

2. **Analysis Steps**  
   - **Time-Series Plots**: Daily P/L vs. temperature  
   - **Scatter/Box Plots**: P/L vs. weather features  
   - **Day-of-Week & Quarter** comparisons (bar charts, line charts)  
   - **Trade Hour/Duration** analysis (if time-based logs exist)

3. **Statistical Testing**  
   - **Pearson & Spearman** correlations for P/L with weather metrics  
   - **T-tests** for rainy vs. non-rainy day performance  
   - **ANOVA/Kruskal–Wallis** for weekday or quarter comparisons  
   - **Regression** to test how durations/trade hours might relate to P/L

4. **Modeling**  
   - **Linear Regression**: Evaluate predictive power of weather/time features on daily P/L  
   - **Decision Trees / Random Forest**: Classify days as profitable vs. non-profitable

---

<a name="key-findings"></a>
## 5. Key Findings

1. **Weather Factors**  
   - A mild correlation emerged between average temperature and daily profit, though results depend on sample size.  
   - Rain showed minor reductions in trading volume but no strong impact on P/L.  
   - Humidity did not significantly correlate with trading outcomes.

2. **Time-Based Patterns**  
   - Certain weekdays suggested higher average P/L (e.g., Tuesday, Thursday), but lacked strong statistical significance.  
   - One quarter (e.g., Q2) sometimes had higher average returns, potentially reflecting broader market trends.  
   - Mid-morning trade executions occasionally indicated improved performance, though further data might be needed.

3. **Predictive Modeling**  
   - **Regression**: Weather features alone had moderate R² (~0.3), improved to ~0.45 when combining volume and time-based factors  
   - **Classification**: Adding weather/time-based features helped identify profitable vs. non-profitable days, but still limited accuracy.

---

<a name="limitations"></a>
## 6. Limitations

- **Data Gaps**: Missing weather data for some trading days can affect correlations  
- **Sample Size**: Fewer observations reduce statistical power  
- **Confounding Variables**: Market conditions, personal schedules, or macro events are not accounted for  
- **Time Data Availability**: If trade execution times/durations are incomplete, certain analyses are constrained  

---

<a name="future-work"></a>
## 7. Future Work

1. **Longer Data Series**  
   - Expand trading logs to multiple years for robust seasonal analysis  
2. **Enhanced Market Features**  
   - Include volatility indices or macroeconomic indicators for context  
3. **Intraday Analysis**  
   - Break down trades into intraday intervals (e.g., 30 min) to capture micro-trends  
4. **Advanced Models**  
   - Test ARIMA, LSTM, or ensemble methods incorporating weather/time as external regressors

---

<a name="how-to-run"></a>
## 8. How to Run

1. **Clone** this repository or download the ZIP  
2. **Place** CSV files (`trading_results.csv`, `trading_results_summary.csv`, `Istanbul,Turkey.csv`) in the `data/` folder  
3. **Install** dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy scikit-learn
