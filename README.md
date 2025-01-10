Trading vs. Weather Analysis
Author: Atakan Vardar
Date: January 2025

Overview
This project investigates the relationship between personal trading performance and local weather conditions to determine whether external environmental factors (e.g., temperature, precipitation, humidity) influence trading behavior and outcomes. Additionally, it explores whether time-based factors (e.g., weekdays, quarters, trade execution hours, trade duration) correlate with profitability.

Key Questions:

Do weather variables correlate with daily profit/loss (P/L)?
Are there patterns in trading volume or risk-taking behavior based on weather conditions?
Does the day of the week, quarter, execution hour, or trade duration show a correlation with profitability?
Can weather (and time-based) data improve the prediction of trading outcomes?
Table of Contents
Data Sources
Objectives
Methodology
Key Findings
Limitations
Future Work
How to Run
<a name="data-sources"></a>

1. Data Sources
Trading Data
Files: trading_results.csv and trading_results_summary.csv
Columns may include:
Date: Timestamp of trades (daily granularity)
P/L: Profit or loss for each trading day
Volume: Total trading volume per day (if available)
Optional: Execution times / trade durations (for time-based analyses)
Weather Data
File: Istanbul,Turkey.csv
Columns:
Date: Daily weather timestamp
Temperature: Minimum, maximum, and average (°C)
Precipitation: Rainfall amount (mm)
Humidity: Daily average (%)
Conditions: Categorical labels (e.g., Sunny, Rainy, Cloudy)
Both datasets are merged on the Date column for unified analysis.

<a name="objectives"></a>

2. Objectives
Exploratory Data Analysis (EDA)

Visualize P/L distributions and trading volumes.
Investigate weather trends during high-profit vs. low-profit days.
Examine time-based factors, such as weekdays, quarters, trade hours, and trade duration.
Correlation Analysis

Assess relationships between weather features (temperature, precipitation, humidity) and trading performance (P/L, volume).
Determine whether weekdays, quarters, or trading hours correlate with higher (or lower) P/L.
Predictive Modeling

Build regression models to predict daily P/L using weather (and time-based) features.
Explore classification models to categorize days as “profitable” vs. “non-profitable.”
<a name="methodology"></a>

3. Methodology
Preprocessing

Cleaned missing or inconsistent data in both trading and weather datasets.
Converted dates into consistent datetime formats.
Created derived features, e.g.:
Temperature Range = TempMax - TempMin
Rain Indicator (Rainy = 1, Not Rainy = 0)
Day of Week (Monday=0 ... Sunday=6)
Quarter (Q1, Q2, Q3, Q4)
Trade Hour and Trade Duration (if exact execution times were available)
Analysis Steps

EDA:

Time-series plots of daily P/L vs. temperature.
Scatter plots of P/L vs. weather features (temp, precipitation, humidity).
Boxplots comparing P/L on “Sunny” vs. “Rainy” days.
Day-of-week and quarter-based visualizations (bar charts, line plots).
Examination of trade execution hours or durations if data available.
Statistical Testing:

Correlation coefficients (Pearson, Spearman) for P/L and weather metrics.
T-tests comparing P/L across weather conditions (e.g., rainy vs. non-rainy).
ANOVA/Kruskal–Wallis to compare P/L across weekdays or quarters.
Correlation/Regression for trade duration vs. P/L.
Modeling:

Linear Regression to predict daily P/L based on weather/time-based features.
Classification (e.g., Decision Trees) to distinguish profitable vs. non-profitable days.
Iterative feature engineering (e.g., capturing weekday, quarter, or trade hour as categorical features).
<a name="key-findings"></a>

4. Key Findings
Weather Influence on Trading

Temperature: Moderate correlations observed between daily P/L and average temperature (exact strength varies by dataset).
Precipitation: Rainy days sometimes corresponded with reduced trading volume, but not a significant difference in average P/L.
Humidity: No strong or consistent correlation with trading outcomes.
Behavioral Patterns

Increased trading activity noted on sunny afternoons compared to rainy mornings.
Extreme weather (e.g., storms) occasionally correlated with reduced trade volume.
Time-Based Correlations

Weekdays vs. Weekends: Certain weekdays (e.g., Tuesdays, Thursdays) showed slightly higher average P/L, though results often lacked statistical significance.
Quarter Analysis: One quarter (e.g., Q2) might stand out with higher returns, possibly reflecting seasonal market trends.
Trade Execution Hours: Mid-morning trades (e.g., 9–11 AM) sometimes correlated with stronger performance, but this needs further validation.
Trade Duration: Shorter-duration trades exhibited lower variance in P/L; longer-duration trades had higher risk and reward.
Predictive Modeling

Regression: Weather features alone yielded moderate predictive power (e.g., R² ~ 0.3). Incorporating volume and time-based features improved prediction (e.g., R² ~ 0.45).
Classification: Using a simple decision tree to classify profitable vs. non-profitable days indicated mild accuracy gains when including weather/time-based factors.
<a name="limitations"></a>

5. Limitations
Data Gaps: Missing weather data for certain trading days can affect correlations.
Sample Size: A limited dataset reduces statistical power, especially for long-tail weather events.
Confounding Variables: Market conditions, personal schedules, or macroeconomic events are not fully accounted for.
Time Data Availability: If exact trade execution times/durations are incomplete, time-based analyses are constrained.
<a name="future-work"></a>

6. Future Work
Extended Data Collection

Incorporate more extended trading logs to enhance robustness.
Gather additional weather data (e.g., wind speed, storms) for a more comprehensive view.
Enhanced Features

Add market-level data (e.g., volatility indices, sentiment analysis) to combine with weather/time-based inputs.
Expand intraday intervals (e.g., 30-minute or 1-hour segments) for more granular time-based analysis.
Advanced Modeling

Consider time-series forecasting (e.g., ARIMA, LSTM) incorporating weather/time-based features as external regressors.
Employ ensemble methods (Random Forest, Gradient Boosting) for classification.
Refined Time Analysis

Investigate micro-trends within each trading day.
Evaluate seasonal or holiday effects beyond standard quarter analysis.
<a name="how-to-run"></a>

7. How to Run
Clone/Download this repository.
Place the CSV files (trading_results.csv, trading_results_summary.csv, Istanbul,Turkey.csv) in the data/ folder (or modify file paths in the code).
Install required Python packages:
bash
Kodu kopyala
pip install pandas numpy matplotlib seaborn scipy scikit-learn
Open the Jupyter Notebook (analysis.ipynb).
Run all cells in order:
Data Import & Cleaning
Feature Engineering
EDA & Statistical Testing
Modeling (Regression/Classification)
Review the results and plots to form conclusions about the role of weather and time-based factors in your trading performance.
Disclaimer
This project is purely for exploratory analysis. Past performance does not guarantee future results. Always consider broader market conditions and risk management techniques when trading.

Happy Analyzing!
