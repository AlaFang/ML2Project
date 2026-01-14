# ML2Project
Main repository for  ML2 project- Xinyue Fang&amp; Ting Wei

Group 12

Xinyue Fang - 446197
Ting Wei - 455848



# Volatility Forecasting with Boosting and Neural Networks

## Overview
This project forecasts **next-day realized volatility** for Citigroup (ticker: `C`) using daily OHLCV data.  
We compare four models from the course syllabus:

- Gradient Boosting Regressor (GB)
- XGBoost (with early stopping)
- RNN
- LSTM

The target is defined as next-day realized volatility proxy:
\[
r_t = \log\left(\frac{P_t}{P_{t-1}}\right), \quad \text{Volatility}_{t+1} = |r_{t+1}|
\]
A time-series split is used to avoid look-ahead bias.

## Key Results (Test Set, aligned window)
Models are evaluated with **MAE** and **RMSE** on a common overlapping test period (sequence models may produce shorter prediction series due to sliding windows).
In our experiment, **XGBoost and Gradient Boosting achieved the lowest RMSE**, while RNN had slightly lower MAE.

## Repository Structure
- `notebooks/` : main analysis notebooks (EDA, feature engineering, training, evaluation)
- `data/` : raw data (download from kaggle https://www.kaggle.com/datasets/isaaclopgu/citigroup-inc-stock-data-daily-updated)
- `model/` : saved models


```bash
pip install -r requirements.txt
