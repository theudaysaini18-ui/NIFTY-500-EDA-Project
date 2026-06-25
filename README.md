# Nifty 500 Five-Year EDA

Exploratory Data Analysis of 5 years of daily OHLCV data for Nifty 500 companies, focused on returns, volatility, drawdowns, and price behavior across Indian equities.

## Overview

This project analyzes historical stock market data for Nifty 500 companies over the last five years. The notebook covers data cleaning, feature engineering, univariate and multivariate analysis, and market behavior exploration using price, return, and volatility-based metrics.

The goal is to understand:
- How daily and monthly returns behave across stocks.
- How volatility changes over time.
- Which stocks experience the largest drawdowns.
- How core market variables such as price, volume, and rolling statistics relate to each other.

## Dataset

- **Source:** Kaggle Nifty 500 companies 5-year stock market dataset.
- **Coverage:** Daily OHLCV data from June 2021 to June 2026.
- **Size:** 551,643 rows and 8 original columns.
- **Original columns:** `Date`, `Ticker`, `Open`, `High`, `Low`, `Close`, `Volume`, `Notes`.[cite:834]

## Project workflow

### 1. Data cleaning
- Converted column names to snake_case.
- Converted `date` to datetime format.
- Sorted values by date.
- Checked null values and duplicates.
- Dropped the `notes` column because it was mostly empty and not useful for analysis.[cite:834]

### 2. Feature engineering
The following features were created to support time-series and risk analysis:
- `dailyreturns`: percentage change in close price by ticker.
- `logreturn`: log difference of close price by ticker.
- `rollingmean20`: 20-day moving average of close.
- `rollingvol20`: 20-day rolling standard deviation of daily returns.
- `year` and `month` from the date column.
- `running_max` and `drawdown` for peak-to-trough decline analysis.[cite:834]

### 3. Exploratory analysis
The notebook includes:
- Basic inspection and descriptive statistics.
- Missing value and duplicate checks.
- Distribution analysis of price and volume.
- Return and volatility analysis.
- Correlation heatmaps for numerical columns.
- Boxplots, histograms, line plots, and other comparative visualizations.[cite:834]

## Key questions answered

- What does the distribution of stock prices and volumes look like?
- How do daily and log returns behave?
- Which features are strongly correlated?
- How volatile are stocks over time?
- Which stocks have the highest prices, biggest drawdowns, or strongest movement patterns?

## Tech stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## File structure

```bash
.
├── nifty_500_5yr_eda.ipynb
├── data/
│   └── nifty500_5yr_data.csv
└── README.md
```

## Sample insights

- Price-based columns such as open, high, low, and close are strongly correlated, which is expected in OHLC market data.
- Return-based features help separate price level from price movement.
- Rolling mean and rolling volatility add trend and risk context that raw price alone cannot provide.
- Drawdown analysis helps identify stocks with deeper downside risk during the period.

## Why this project is portfolio-worthy

This project demonstrates:
- Real-world financial data cleaning.
- Time-series feature engineering.
- Exploratory data analysis at scale.
- Use of visualization to explain market behavior.
- Ability to turn raw stock data into interpretable insights.

## Possible improvements

To make this project even stronger, the next version can include:
- Sector-wise analysis.
- Risk-return comparison of stocks.
- Portfolio simulation or simple allocation strategies.
- Interactive dashboard using Plotly or Streamlit.
- Executive summary with top findings for non-technical readers.

## How to run

1. Clone the repository.
2. Place the dataset inside the `data/` folder.
3. Open the notebook in Jupyter.
4. Run all cells in order.

## Author

Created as a portfolio project to showcase EDA, financial analysis, and feature engineering skills using Nifty 500 stock market data.
