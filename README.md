# Mortgage Rate Forecasting: Benchmarking AI Models and Lock-or-Wait Decisions

**Author:** Dyamond Bryant | CSI 4130/5130 Course Project

## Problem statement
Mortgage rates are among the most important numbers in personal finance, but they are
hard to predict. This is important for when people are in the buying process but they don't know if they should buy now or wait for rates to go down but can also risk rates going up. This project asks: *how much can modern AI beat a naive baseline at
forecasting the 30-year mortgage rate, and does any improvement translate into better
lock-or-wait decisions?* A negative result is an acceptable finding if it is tested rigorously.

## Proposed method
1. **Data pipeline:** download public weekly/daily/monthly series from FRED and align
   them to a weekly time series.
2. **Evaluation framework:** walk-forward validation (train on the past, test on the
   future) with no lookahead leakage, covered by unit tests.
3. **Models:** naive baseline (next week = this week), ARIMA, gradient boosting, and a
   pretrained time-series foundation model
4. **Statistics:** error vs. the naive baseline at several horizons, confidence
   intervals, and a Diebold-Mariano significance test.
5. **Lock-or-wait backtest:** compare the average rate paid under model-guided decisions
   against always locking immediately.
6. **Demo:** an interactive lock or wait test OR a rate predictor 

## Data sources (all public, from FRED)
- MORTGAGE30US: 30-Year Fixed Rate Mortgage Average (Freddie Mac), weekly
- DGS10: 10-Year Treasury Constant Maturity Rate, daily
- FEDFUNDS: Effective Federal Funds Rate, monthly
- CPIAUCSL: Consumer Price Index, monthly
- UNRATE: Unemployment Rate, monthly

