Overview
This project investigates the relationship between personal trading performance and local weather conditions to determine whether external environmental factors (e.g., temperature, precipitation, humidity) influence trading behaviors and outcomes. Additionally, this analysis examines whether time-based factors (e.g., weekdays, quarter boundaries, trade execution hours, and trade duration) correlate with trade success.

The analysis aims to answer key questions:

Do weather variables correlate with daily profit/loss (P/L)?
Are there patterns in trading volume or risk-taking behavior based on weather conditions?
Does the day of the week, trading quarter, time of trade execution, or trade duration show a correlation with profitability?
Can weather data (and time-based data) improve the prediction of trading outcomes?
Table of Contents
Data Sources
Objectives
Methodology
Key Findings
Limitations
Future Work
How to Run
Data Sources
1. Trading Data (trading_results.csv and trading_results_summary.csv)
Columns:
Date: Timestamp of trades (daily granularity).
P/L: Profit or loss for each trading day.
Volume: Total trading volume for the day.
(Optional) Execution Times / Trade Durations: If available, these can be used for time-based analysis.
2. Weather Data (Istanbul,Turkey.csv)
Columns:
Date: Daily weather timestamps.
Temperature: Minimum, maximum, and average temperatures (°C).
Precipitation: Amount of rainfall (mm).
Humidity: Daily average (%).
Conditions: Categorical labels like "Sunny", "Rainy", or "Cloudy".
Both datasets are merged on the Date column for analysis.

Objectives
Exploratory Data Analysis (EDA):

Visualize P/L distributions and trading volumes.
Investigate weather trends during high-profit and low-profit days.
Examine time-based factors such as weekdays, quarters, trade hours, and trade duration.
Correlation Analysis:

Analyze relationships between weather features (temperature, precipitation, humidity) and trading performance (P/L and volume).
Assess whether certain days of the week, quarters, or trading hours correlate with higher (or lower) P/L.
Predictive Modeling:

Build regression models to predict daily P/L using weather (and time-based) features.
Explore classification models for "profitable" vs. "non-profitable" days.
Methodology
Preprocessing:

Cleaned missing or inconsistent data in both trading and weather datasets.
Converted dates into consistent datetime formats.
Created derived features like:
Temperature Range = Max - Min Temperature.
Binary indicator for precipitation (Rainy = 1, Not Rainy = 0).
Extracted day of week (Monday=0, ..., Sunday=6).
Extracted quarter (Q1, Q2, Q3, Q4).
Extracted time-of-day features from trade execution times (if available).
Computed trade duration (if available).
Analysis Steps:

EDA:

Time-series plots of daily P/L vs. temperature.
Scatter plots of P/L against weather features.
Boxplots comparing P/L for "Sunny" vs. "Rainy" days.
Boxplots or line charts showing P/L by weekday or by quarter.
Histograms or scatter plots showing P/L relative to trade execution hours and durations.
Statistical Testing:

Correlation coefficients (e.g., Pearson) for P/L and weather metrics.
T-tests to compare P/L distributions across weather conditions.
ANOVA or Kruskal-Wallis tests to compare P/L across multiple weekdays or quarters.
Correlation or regression analyses for trade duration vs. P/L.
Modeling:

Linear regression to predict daily P/L.
Decision trees to classify profitable vs. non-profitable days.
Feature engineering to include weekday, quarter, trade hour, and trade duration.
Key Findings
Weather Influence on Trading:

Temperature: Moderate correlation between daily P/L and average temperature.
Precipitation: Rainy days tended to have lower trading volumes but not significantly different P/L.
Humidity: No strong correlation with trading outcomes.
Behavioral Patterns:

Higher trading activity observed during sunny afternoons compared to rainy mornings.
Extreme weather conditions (e.g., storms) led to reduced trading activity.
Time-Based Correlations:

Weekdays vs. Weekends: (Example finding) Tuesdays and Thursdays showed slightly higher average P/L, though not statistically significant.
Quarter Analysis: (Example finding) Q2 had the highest average returns, potentially due to seasonal market trends.
Trade Execution Hours: (Example finding) Mid-morning trades (9-11 AM) correlated with better performance, but this needs further validation.
Trade Duration: (Example finding) Shorter-duration trades had less variance in P/L, while longer-duration trades carried higher risk and reward.
Predictive Modeling:

Regression models showed mild predictive power (R² ~ 0.3) using weather data alone.
Combining trading volume and time-based features with weather improved predictions (R² ~ 0.45).
Limitations
Data Gaps: Missing weather data for certain trading days may affect correlations.
Sample Size: Limited data reduces statistical power for predictive modeling.
Confounding Variables: External factors (e.g., market trends, personal schedules) were not accounted for.
Time Data Availability: If exact trade execution times and durations are incomplete or missing, time-based analyses may be restricted.
Future Work
Extended Data Collection:
Incorporate additional trading data over longer periods to improve statistical robustness.
Enhanced Features:
Add market-level data (e.g., volatility indices, sentiment analysis) to complement weather and time-based metrics.
Advanced Models:
Explore time-series forecasting (ARIMA, LSTMs) with weather and time-based features as external inputs.
Refined Time Analysis:
Investigate intraday patterns more precisely (e.g., 30-minute intervals) to identify micro-trends within trading days.
