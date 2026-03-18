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
├── peak_demand.csv
├── morning.ipynb
├── day.ipynb
├── evening.ipynb
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


## 🌍 Real-World Applications

This project has direct applications in the energy and power sector:

### ⚡ Power Grid Management

Helps electricity providers forecast demand and ensure stable power supply, reducing the risk of outages.

### 🔌 Load Scheduling & Generation Planning

Enables efficient scheduling of power generation based on predicted demand across morning, day, and evening periods.

### 💰 Cost Optimization

Reduces operational costs by avoiding overproduction and minimizing reliance on expensive emergency power purchases.

### 🌞 Renewable Energy Integration

Supports better integration of renewable energy sources like solar and wind by aligning supply with demand patterns.

### 🏙️ Smart City Planning

Assists in infrastructure planning and long-term energy demand forecasting for urban development.

### 📊 Energy Market Decisions

Helps in electricity trading and pricing strategies by predicting demand fluctuations.

---

## 🚀 Future Improvements

* Integrate all models into a unified pipeline
* Include exogenous variables (weather, holidays)
* Automate SARIMA parameter tuning

---
