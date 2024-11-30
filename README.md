# Motherbar-on-EURUSD
Inside Bar Trading Strategy: EUR/USD FX Pair
Project Overview
This project evaluates the profitability of a trading strategy based on inside bars in the EUR/USD forex pair. The analysis uses historical 5-minute candlestick data to identify and test the strategy under varying conditions. The objective is to determine whether the strategy is profitable and identify the optimal parameters for implementation.

Motivation
The inside bar trading strategy is widely used in technical analysis as a pattern for market consolidation and potential breakouts. I aim to validate this strategy based on my current trading style and explore whether it can be optimized for better profitability.

Data Source
Historical Data: 5-minute candlestick data for EUR/USD from the past year.


Trading Strategy
Key Definitions
Inside Bar: A candlestick whose high and low are entirely within the preceding mother bar.
Mother Bar: The larger candlestick preceding an inside bar.
Trade Execution Rules
Entry: Enter the trade somewhere inside the mother bar (e.g., beginning, midpoint, or other percentages).
Stop Loss: Place the stop loss at the opposite extreme of the mother bar.
Take Profit: Set the target at the breakout candle’s highest or lowest position, depending on the breakout direction.
Methodology
Exploratory Data Analysis (EDA):

Visualize the distribution and frequency of inside bars.
Analyze market conditions during inside bar formations.
Backtesting:

Programmatically identify mother and inside bars.
Simulate trades based on configurable entry points and risk-reward setups.
Measure performance using metrics like:
Cumulative profit.
Win rate.
Risk-reward ratios.
Optimization:

Test different entry points and stop-loss levels to maximize profitability.
Assess the strategy under varying market trends and conditions.
Project Objectives
Validate the profitability of the inside bar trading strategy.
Identify the optimal configuration for trade entry, stop-loss, and take-profit levels.
Provide insights into the conditions where the strategy performs best.
