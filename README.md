# Time-Series-Forecasting-of-Atmospheric-CO₂-Concentration-Using-Seasonal-ARIMA-Models

## Overview

This project applies **Seasonal ARIMA (SARIMA)** models to analyze and forecast **monthly atmospheric CO₂ concentrations** measured at the **Mauna Loa Observatory**. The focus is on capturing the **long-term upward trend** and **annual seasonality** inherent in the data using classical time series techniques.

---

## Data

* **Source:** Mauna Loa Observatory (via `astsa` package in R)
* **Period:** 1958–2023
* **Frequency:** Monthly (seasonal period = 12)
* **Unit:** Parts per million (ppm)

The dataset was divided into **80% training data** for model estimation and **20% test data** for out-of-sample forecast evaluation.

---

## Methodology

* Exploratory analysis using **time series plots**, **ACF**, and **PACF**
* First-order non-seasonal differencing (d = 1) to remove trend
* First-order seasonal differencing (D = 1) to remove annual seasonality
* Multiple SARIMA models fitted using **maximum likelihood estimation**
* Model comparison based on:

  * **AIC** (model parsimony)
  * **RMSE** on the test set
  * **Ljung–Box test** for residual autocorrelation

---

## Final Model

**ARIMA(1,1,1)(0,1,1)[12]**

**Why this model?**

* Lowest AIC among candidate models
* Residuals consistent with white noise (Ljung–Box p > 0.05)
* Forecast accuracy comparable to more complex alternatives

---

## Conclusion

The analysis confirms that atmospheric CO₂ concentration exhibits strong **trend and seasonal behavior**. SARIMA models effectively capture these patterns when appropriate differencing and diagnostics are applied. The selected model provides a statistically adequate and interpretable framework for monthly CO₂ forecasting.
Future work may incorporate exogenous variables through SARIMAX models or apply rolling-origin validation to further assess forecasting performance.

---

## Tools & Libraries
- **Language:** R
- **Packages:** astsa, forecast

---

## Author

**Sohini Mandal**

M.Sc. Data Science

St. Xavier’s College (Autonomous), Kolkata

---
