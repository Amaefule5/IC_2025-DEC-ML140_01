# Weather Forecasting with Historical Time Series Data

## Project Overview

This repository presents a complete weather forecasting workflow using historical hourly and daily weather observations. It focuses on predicting next day temperature while benchmarking statistical and deep learning models on the same forecasting task. The goal is to show how different modeling approaches perform under real sequential data conditions and to highlight tradeoffs between accuracy, complexity, and interpretability.

---

## Problem Statement

The project aims to predict next day temperature for a selected location using historical weather data. Input features include temperature, humidity, rainfall, wind speed, and other atmospheric variables. All experiments preserve temporal order during training and evaluation to reflect real forecasting scenarios and prevent data leakage.

This approach addresses:

* Realistic time series forecasting
* Comparison of model families (linear, statistical, deep learning)
* Assessment of tradeoffs between interpretability, speed, and predictive power

---

## Dataset Description

The dataset includes the following columns:

* **Formatted Date** – Timestamp of observation
* **Summary** – Hourly weather description (text)
* **Daily Summary** – Daily summary description (text)
* **Precip Type** – Categorical: rain, snow, none
* **Temperature C** – Measured temperature (target for regression)
* **Apparent Temperature C** – Feels-like temperature
* **Humidity** – Relative humidity
* **Wind Speed km/h** – Wind velocity
* **Wind Bearing degrees** – Wind direction
* **Visibility km** – Visibility distance
* **Loud Cover** – Typically constant, may be dropped
* **Pressure millibars** – Atmospheric pressure

#### Dataset Source
This project uses the Weather History Dataset on [Kaggle](https://www.kaggle.com/datasets/muthuj7/weather-dataset).
It contains hourly and daily weather observations across multiple years, including temperature, humidity, wind speed, and precipitation.

---
## Tools and Technologies

* **Python** – Core programming language for data manipulation and modeling
* **Pandas & NumPy** – Data cleaning, exploration, and numeric operations
* **Matplotlib & Seaborn** – Data visualization and trend analysis
* **scikit-learn** – Regression, classification, feature engineering, preprocessing
* **statsmodels** – Classical time series models (ARIMA, SARIMA)
* **TensorFlow & Keras** – Deep learning sequence models (RNN, LSTM)

**Contributions to the Project:**

* Data cleaning and preprocessing
* Feature engineering for regression, classification, and time series
* Model building and benchmarking
* Visualization of trends, errors, and feature importance

---

## Project Workflow

### 1. Data Preparation and Exploration

* Parse timestamps and extract time features (year, month, day, hour, day-of-week)
* Handle missing values and drop constant features (e.g., Loud Cover)
* Visualize trends, seasonality, and correlations

### 2. Baseline Modeling with Linear Regression

* Train baseline regression with lag-based temperature features
* Provides interpretable reference for performance gains from complex models

### 3. Classical Time Series Modeling with ARIMA

* Capture trend and seasonality directly from the sequence
* Apply time-based train/test split
* Compare predictive performance to baseline

### 4. Deep Learning with LSTM and RNN

* Transform data into sequences using sliding windows
* Train LSTM/RNN models to capture long-term dependencies
* Evaluate improvements over classical models

---

## Evaluation Strategy

* Metrics: MAE (Mean Absolute Error), RMSE (Root Mean Squared Error)
* Compare predicted vs actual temperature values over time
* Assess model accuracy, stability, and error distribution

---

## Key Insights

* Linear Regression is fast and interpretable
* ARIMA captures temporal structure with fewer features
* LSTM handles longer-term dependencies with higher complexity

---

## Why This Project Matters

This project demonstrates a structured, realistic forecasting workflow using real-world data. It highlights:

* Model selection tradeoffs between interpretability, speed, and accuracy
* Importance of proper feature engineering and temporal validation
* Practical applications in climate analysis, energy planning, and operational decision-making
* A reference workflow for students and professionals learning time series, regression, and deep learning

---

## Future Extensions

* Extend forecasting to rainfall, humidity, and other weather features
* Apply multivariate sequence models
* Test different historical window sizes
* Scale workflow across multiple locations

---
