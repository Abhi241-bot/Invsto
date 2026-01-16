📈 Stock Price Prediction using ARIMA & Gradient Boosting

Data Science / Machine Learning Internship Assessment

This repository contains an end-to-end stock price prediction pipeline developed as part of an internship assessment. The project compares a classical time-series model (ARIMA) with a machine learning model (Gradient Boosting Regressor) across multiple large-cap technology stocks.

The emphasis is on model comparison, data quality, time-series awareness, and practical trading relevance, rather than purely maximizing predictive accuracy.

🧠 Problem Statement

The objective is to build a robust and reproducible data science pipeline that:

Processes historical OHLCV stock data

Performs exploratory data analysis (EDA)

Engineers time-series and technical features

Trains and evaluates ARIMA and Gradient Boosting models

Compares model performance using appropriate error metrics

Interprets results in the context of trading and risk management

📊 Dataset

Source: Yahoo Finance (via yfinance)

Frequency: Daily

Period: Rolling 2-year window (~500 trading days per stock)

Stocks analyzed:

AAPL

GOOGL

MSFT

AMZN

TSLA

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

Over 50 features including:

Lagged prices and volumes

Rolling means and standard deviations

Technical indicators (RSI, MACD, Bollinger Bands)

Price and volume change metrics

4️⃣ Modeling

ARIMA

Parameter selection guided by ACF/PACF and AIC

Evaluated using an out-of-sample holdout

Gradient Boosting Regressor

Tree-based non-linear model

Hyperparameter experimentation via controlled grid search

Feature importance analysis for interpretability

5️⃣ Evaluation

Models are compared using:

RMSE

MAE

MAPE

Results are analyzed per stock to highlight regime-dependent behavior.

📈 Key Results (Summary)

Gradient Boosting outperformed ARIMA in 4 out of 5 stocks

ARIMA performed better during strong trend regimes (e.g., GOOGL)

Feature importance analysis showed strong autoregressive persistence, with lagged price levels dominating predictions

Model performance varied by volatility and trend characteristics

Important: Metrics should be interpreted as signal quality indicators, not realized trading returns.

💡 Trading Interpretation (Conceptual)

This project does not execute trades. However, predictions can be used as decision-support signals:

Gradient Boosting for short-horizon adaptive forecasting

ARIMA as a stable baseline during persistent trends

Stop-loss levels derived from model error (e.g., 2 × RMSE)

Monthly retraining using a rolling window

⚠️ Limitations & Assumptions

No transaction costs, slippage, or portfolio backtesting included

Models predict price levels, not returns

Time-series cross-validation is approximated; expanding-window validation is recommended for production

Calendar days are used for forecasting instead of exchange-specific trading calendars

These choices were made to keep the assessment focused, interpretable, and aligned with internship scope.

🛠 Technologies Used

Core Stack

Python 3.x

pandas, numpy

statsmodels (ARIMA)

scikit-learn (Gradient Boosting)

matplotlib, seaborn

Data

Yahoo Finance (yfinance)

The pipeline is designed to be extensible to large datasets (e.g., Dask) and cloud storage if required.
