# Mumbai Peak Power Demand Forecasting (SARIMA)

## 📌 Overview

This project forecasts peak electricity demand in Mumbai using advanced time series model (SARIMA). The forecasting is performed separately for morning, daytime, and evening peak demand using historical data.

---

## 🎯 Objectives

* Forecast peak electricity demand in Mumbai
* Predict demand for the next 30 days
* Model demand patterns separately for:

  * Morning peak
  * Day peak
  * Evening peak

---

## 🗂️ Dataset

The dataset contains daily peak demand values for different time periods:

* Date
* Morning Peak Demand
* Day Peak Demand
* Evening Peak Demand

Time span: ~1.5 years

---

## 🧩 Project Structure

```text id="0hp5bo"
project/
│
├── data.csv
├── morning_model.py
├── day_model.py
├── evening_model.py
└── README.md
```

Each script builds an independent time series model for its respective demand column.

---

## ⚙️ Methodology

### 1. Data Preprocessing

* Date parsing and time indexing
* Handling missing values
* Train-test split

---

### 2. Stationarity Check

* **ADF Test (Augmented Dickey-Fuller)**
* Differencing applied to achieve stationarity

---

### 3. Model Identification

* **ACF (Auto-Correlation Function)** → helps identify MA(q)
* **PACF (Partial Auto-Correlation Function)** → helps identify AR(p)

---

### 4. Model Specification

* **SARIMA (p, d, q)(P, D, Q, s)**

  * p, d, q → non-seasonal components
  * P, D, Q → seasonal components
  * s → seasonal period

* **SARIMAX** used when incorporating external variables

---

### 5. Diagnostic Checks

* **Ljung-Box Test** → residual independence
* **Heteroskedasticity Test** → constant variance check
* Residual analysis to validate assumptions

---

### 6. Model Selection & Evaluation

* **AIC (Akaike Information Criterion)** → best model selection
* **MASE (Mean Absolute Scaled Error)** → forecast accuracy

---

### 7. Forecasting

* 30-day forecasts generated separately for:

  * Morning peak demand
  * Day peak demand
  * Evening peak demand

---

## ▶️ Usage

Run individual models:

```bash id="3w80gi"
python morning.ipynb
python day.ipynb
python evening.ipynb
```

---

## 📊 Output

* Forecasted peak demand (30 days)
* Model diagnostics
* Evaluation metrics (AIC, MASE)

---

## 👥 Authors

* Anfas Ahammed
* Muhammed Salman

---

## 🚀 Future Improvements

* Integrate all models into a unified pipeline
* Include exogenous variables (weather, holidays)
* Automate SARIMA parameter tuning

---
