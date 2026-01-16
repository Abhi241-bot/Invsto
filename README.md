📈 Stock Price Prediction using ARIMA & Gradient Boosting

Data Science / Machine Learning Internship Assessment

This repository presents an end-to-end stock price prediction pipeline developed as part of a data science internship assessment. The project compares a classical time-series approach (ARIMA) with a machine learning model (Gradient Boosting Regressor) across multiple large-cap technology stocks.

The focus is on model comparison, data quality, time-series awareness, and practical trading relevance, rather than solely maximizing predictive accuracy.

🧠 Problem Statement

The objective is to build a robust, reproducible, and interpretable data science pipeline that:

📊 Processes historical OHLCV stock data

🔍 Performs exploratory data analysis (EDA)

🧮 Engineers meaningful time-series & technical features

🤖 Trains and evaluates ARIMA and Gradient Boosting models

📉 Compares model performance using appropriate error metrics

💡 Interprets results in the context of trading and risk management

📊 Dataset

Source: Yahoo Finance (via yfinance)

Frequency: Daily

Time Horizon: Rolling 2-year window (~500 trading days per stock)

Stocks Analyzed

🍎 AAPL

🔎 GOOGL

🪟 MSFT

📦 AMZN

🚗 TSLA

🔧 Methodology Overview
1️⃣ Data Preparation

Missing value handling (forward/backward fill)

Removal of duplicate timestamps

Outlier filtering using statistical thresholds

Validation of price and volume integrity

2️⃣ Exploratory Data Analysis (EDA)

Price and volume trends

Return distributions

Volatility analysis

Moving averages and regime behavior

3️⃣ Feature Engineering

Over 50 engineered features, including:

Lagged prices and volumes

Rolling means and standard deviations

Technical indicators:

RSI

MACD

Bollinger Bands

Price and volume change metrics

4️⃣ Modeling
📉 ARIMA

Parameter selection guided by ACF/PACF and AIC

Evaluated using an out-of-sample holdout

🌲 Gradient Boosting Regressor

Tree-based non-linear regression model

Hyperparameter experimentation via controlled grid search

Feature importance analysis for interpretability

5️⃣ Evaluation

Models are compared using:

RMSE (Root Mean Squared Error)

MAE (Mean Absolute Error)

MAPE (Mean Absolute Percentage Error)

Results are analyzed per stock to highlight regime-dependent behavior.

📈 Key Results (Summary)

✅ Gradient Boosting outperformed ARIMA in 4 out of 5 stocks

📊 ARIMA performed better during strong trend regimes (e.g., GOOGL)

🧠 Feature importance analysis showed strong autoregressive persistence

🔄 Model performance varied significantly with volatility and trend characteristics

⚠️ Metrics should be interpreted as signal quality indicators, not realized trading returns.

💡 Trading Interpretation (Conceptual)

This project does not execute trades. However, predictions may be used as decision-support signals:

🤖 Gradient Boosting for short-horizon adaptive forecasting

📉 ARIMA as a stable baseline during persistent trends

🛑 Stop-loss levels derived from model error (e.g., 2 × RMSE)

🔁 Monthly retraining using a rolling window

⚠️ Limitations & Assumptions

No transaction costs, slippage, or portfolio backtesting

Models predict price levels, not returns

Time-series cross-validation is approximated
(expanding-window validation recommended for production)

Calendar days are used instead of exchange-specific trading calendars

These design choices keep the project focused, interpretable, and aligned with internship scope.

🛠 Technologies Used
Core Stack

Python 3.x

pandas, numpy

statsmodels (ARIMA)

scikit-learn (Gradient Boosting)

matplotlib, seaborn

Data

Yahoo Finance (yfinance)

🚀 Extensibility

The pipeline is designed to be scalable and extensible, with potential future support for:

Larger datasets (e.g., Dask)

Cloud-based storage and execution

Trading calendar-aware forecasting

Return-based modeling and backtesting
