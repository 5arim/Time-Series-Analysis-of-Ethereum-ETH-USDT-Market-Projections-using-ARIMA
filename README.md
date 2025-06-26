# Time-Series-Analysis-of-Ethereum-ETH-USDT-Market-Projections-using-ARIMA
Ethereum Price Analysis and Forecasting with ARIMA
Project Overview
This project fulfills Task 01: Time Series Analysis of Ethereum (ETH/USDT) Market Projections using ARIMA for the ARCH Technologies Machine Learning Internship. It analyzes historical Ethereum (ETH/USDT) price data and forecasts prices from July 7, 2021, to June 26, 2025, using the ARIMA model.
Data Source

Dataset: coin_Ethereum.csv from Kaggle (https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory)
Date Range: August 8, 2015, to July 6, 2021
Attributes: Date, Open, High, Low, Close, Volume, Marketcap
Limitation: The manual required data from January 1, 2020, to June 26, 2025. However, fetching recent data (July 7, 2021, to June 26, 2025) via the CoinGecko API failed due to rate limits on the free tier (5–15 calls/minute). Alternative free sources (e.g., CryptoDataDownload, Yahoo Finance) lacked the full timeframe or required attributes. Paid APIs (e.g., CoinGecko Pro, CoinMarketCap) were cost-prohibitive (e.g., $29–$129/month). Thus, the full Kaggle dataset (2015–2021) was used, with ARIMA forecasting to extend to June 26, 2025.

Project Steps

Preprocessing:
Loaded coin_Ethereum.csv, selected relevant columns, removed timestamps, set daily frequency, and saved as eth_kaggle_processed.csv.


Exploratory Data Analysis (EDA):
Visualized Close price trend and 30-day moving average (eth_price_trend.png, eth_price_30d_ma.png).
Computed statistical summaries, highlighting high volatility.


ARIMA Modeling:
Applied ARIMA(5,1,0) to Close price after confirming non-stationarity (ADF test) and differencing.
Forecasted 1,450 days (July 7, 2021, to June 26, 2025), saved as eth_arima_forecast_final.csv.


Evaluation:
Split data into 80% training and 20% testing, calculated RMSE, and analyzed residuals for randomness (eth_arima_test_forecast.png, eth_arima_residuals.png, eth_arima_residuals_acf.png).



Files

Data:
coin_Ethereum.csv: Original Kaggle dataset.
eth_kaggle_processed.csv: Processed dataset (daily frequency, 2015–2021).
eth_arima_forecast_final.csv: ARIMA forecast (July 7, 2021, to June 26, 2025).


Visualizations:
eth_price_trend.png: Closing price trend.
eth_price_30d_ma.png: Closing price with 30-day moving average.
eth_arima_test_forecast.png: Actual vs. predicted test set prices.
eth_arima_residuals.png: Residuals of test set predictions.
eth_arima_residuals_acf.png: Autocorrelation of residuals.
eth_arima_forecast_final.png: Historical prices and forecast to 2025.


Code (suggested names, save scripts from previous steps):
preprocess.py: Data preprocessing.
eda_ethereum.py: EDA visualizations and statistics.
arima_ethereum.py: ARIMA model and forecasting.
arima_evaluation_ethereum.py: Model evaluation and final forecast.



Usage

Install dependencies: pip install pandas statsmodels matplotlib scikit-learn

Place coin_Ethereum.csv in the working directory.

Run scripts in order:
python preprocess.py
python eda_ethereum.py
python arima_ethereum.py
python arima_evaluation_ethereum.py


Outputs are saved in the eth_arima_submission folder.


Notes

The long-term forecast (1,450 days) has high uncertainty due to Ethereum’s volatility.
The report (ETH_ARIMA_Report.pdf) summarizes all steps, results, and limitations, including the use of forecasting to address the data gap.

