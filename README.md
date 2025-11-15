🧠 Air Quality Time Series Forecasting Project
Predicting Hourly Pollutant Concentrations using ARIMA, SARIMAX, Prophet & XGBoost


📌 Project Overview
This project performs a complete time series analysis and 48-hour future forecasting of the “Air Quality UCI Dataset”.
Multiple models were applied and compared across 13 pollutants and environmental variables.

Models used:
ARIMA (Auto-Regressive Integrated Moving Average)
SARIMAX (Seasonal ARIMA with Exogenous Variables)
XGBoost Regressor
Prophet (optional)


The project includes:

✔ Data cleaning & preprocessing
✔ Exploratory analysis & missing value treatment
✔ Feature engineering (lag features, rolling windows, calendar features)
✔ Model training and evaluation using RMSE
✔ Residual analysis
✔ Feature importance (XGBoost)
✔ 48-hour forecasting for all pollutants
✔ Submission file generation

📂 Repository Structure
AirQuality-TimeSeries-Analysis/
│
├── timeseriesanalysisiitg(deepanshu).py   # Full analysis script
├── AirQualityUCI.xlsx                     # Input dataset (if uploaded)
├── 48_hour_forecast.csv                   # Final 48-hour model forecast
├── rmse_results.csv                       # RMSE comparison for all pollutants
├── submission.csv                         # Final formatted submission file
├── README.md                              # Project documentation


📊 Dataset Description

The dataset includes hourly measurements of:

Gaseous pollutants:
CO(GT), NMHC(GT), C6H6(GT), NOx(GT), NO2(GT)

Sensor responses:
PT08.S1(CO), PT08.S2(NMHC), PT08.S3(NOx), PT08.S4(NO2), PT08.S5(O3)

Environmental features:
Temperature, Relative Humidity, Absolute Humidity

Missing values (-200) were replaced using:

Forward Fill  → Backward Fill

🛠️ Feature Engineering
Time-based features: Hour, Day, Month, Day of week, Weekend indicator

Lag features:

Lags: 1, 2, 3, 6, 12, 24 hours

Rolling statistics:

Rolling Mean (3, 6, 12, 24)

Rolling Standard Deviation (6, 12, 24)

🤖 Models Applied
🔹 ARIMA

Simple (2,1,2) model.

🔹 SARIMAX

Seasonal parameters with daily hourly seasonality (24 hours).

🔹 XGBoost Regressor

Used engineered features, with reduced complexity:

max_depth = 4
n_estimators = 100
learning_rate = 0.1
subsample = 0.7

🏆 Model Comparison Results

For each pollutant, the best model was selected using RMSE:

Model	Uses Seasonality	Handles Nonlinear Patterns	Speed
ARIMA	❌	❌	Fast
SARIMAX	✅	❌	Medium
XGBoost	❌	✅	Fast
Prophet	Limited	Some	Medium

Each pollutant may have a different best model.

📈 Residual Analysis

Residual diagnostics include:

Time-series residual plot

Histogram

ACF plot

Ljung-Box test (autocorrelation)

Shapiro-Wilk test (normality)

This ensures model reliability.

🔮 48-Hour Forecast

A 48-hour future forecast is generated for:

All pollutant concentrations

All environmental parameters

Saved as:

48_hour_forecast.csv

📤 Submission File

A final formatted submission file including:

Date

Time

All pollutants

Saved as:

submission.csv

🚀 How to Run the Project
Option 1 — Google Colab

Upload your notebook or script and dataset, then run.

Option 2 — Local Python

Install dependencies:

pip install numpy pandas matplotlib seaborn statsmodels prophet xgboost scikit-learn


Run the script:

python timeseriesanalysisiitg(deepanshu).py

