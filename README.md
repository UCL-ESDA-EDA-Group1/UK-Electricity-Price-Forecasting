# UK-Electricity-Price-Forecasting
UK day-ahead electricity price prediction using weather-driven renewables forecasting + ML (XGBoost/SVR), including spike detection + battery arbitrage evaluation.

[![Run on Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/UCL-ESDA-EDA-Group1/UK-Electricity-Price-Forecasting/HEAD)

# UK Electricity Price Forecasting (Weather → Renewables → Price)

This repository contains the **final runnable pipeline (Sections 4–6)** of our group project on forecasting **UK day-ahead electricity prices** using machine learning, benchmarking against time-series baselines, and assessing decision value via a battery arbitrage simulation.

> **Note:** The full Stage 1 renewable generation modelling (weather → wind/PV training) is not included in this public repo.  
> This repo includes the **processed datasets + predicted wind/PV inputs** required to run the price modelling end-to-end from **Section 4 onward**.

---

## Key results (test set)
- **Price forecasting (XGBoost + SVR):** R² ≈ **0.88**, RMSE ≈ **12.43 EUR/MWh**, MAE ≈ **8.71 EUR/MWh**
- **Extreme price spike detection (95th percentile):** F1 ≈ **0.63**
- **Battery arbitrage backtest (100 MW / 200 MWh):** ~**€3.99M**, capturing ~**90%** of perfect-foresight upper bound

---

## Repository contents

### Main notebook
- `UK_Electricity_Price_Prediction_Complete.ipynb`  
  ✅ Runnable from: **SECTION 4: ELECTRICITY PRICE PREDICTION** onward.

### Included datasets (Sections 4–6)
Located in: `data/step2_prices/`

- `UK_WholesalePrices_Hourly.csv`
- `demanddata_2021-2025.csv`
- `SAP.xlsx` *(gas prices)*
- `Carbon Emissions Futures Historical Data UK.csv`
- `wind_100Locs_XGBoost_WalkForward_Clean_PREDICTED-weather-data.csv` *(predicted wind input)*
- `xgboost_cv_predictions.csv` *(predicted solar/PV input)*

---

## What the notebook does (Sections 4–6)
- Builds a supervised learning dataset combining **demand + fuel/carbon drivers + predicted renewables (wind/PV)**
- Trains and evaluates **XGBoost** and **SVR** models for day-ahead price prediction
- Benchmarks performance against an **ARIMA** baseline model
- Simulates **battery arbitrage** decisions using predicted prices to quantify decision value

---
