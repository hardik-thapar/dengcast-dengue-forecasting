# DengCast: Dengue Time Series Forecasting

A structured machine learning pipeline for forecasting weekly dengue cases using environmental variables and temporal features.

This repository implements **DengCast**, a forecasting pipeline evaluated on the **DrivenData DengAI dataset**, predicting weekly dengue cases for:

- **San Juan, Puerto Rico**
- **Iquitos, Peru**

The project emphasizes **disciplined time-series modeling**, **leak-free validation**, and **interpretable feature engineering**.

---

## Overview

Dengue outbreaks exhibit strong temporal autocorrelation.  
Instead of complex deep learning architectures, DengCast focuses on **structured feature engineering and robust validation**.

The pipeline combines:

- climate features
- autoregressive case lags
- rolling statistics
- gradient boosting regression

All experiments follow **strict chronological cross-validation** to avoid temporal leakage.

---

## Key Features

**Data Processing**
- Preprocessing pipeline tailored to the DengAI dataset
- Handling of missing values via forward-fill within training folds

**Exploratory Analysis**
- Seasonal trend analysis
- Outbreak spike visualization
- Feature distribution analysis

**Temporal Feature Engineering**
- Lag features (1–4 weeks)
- Rolling mean (4 and 8 weeks)
- Rolling standard deviation

**Modeling**
- Log transformation of target variable
- CatBoost gradient boosting regression
- MAE optimization objective

**Validation**
- Chronological `TimeSeriesSplit`
- Fold-level performance evaluation

**Reproducibility**
- Structured Jupyter notebooks
- Fixed random seeds
- Documented experiment workflow

---

## Results (Cross-Validated)

| City | Baseline MAE | DengCast MAE |
|-----|-----|-----|
| San Juan | ~30 | **11.87** |
| Iquitos | ~31 | **4.74** |

Performance improvements are primarily driven by **autoregressive lag features**, which capture short-term outbreak momentum.

---


