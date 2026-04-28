# Embedded_Intelligence (Time Series Analysis of a Univariate Sensor Signal)
## Overview

This repository contains the complete submission for the time series analysis assignment. The analysis focuses on a univariate sensor time series (heart rate data), covering stationarity assessment, transformation, correlation structure inspection, model fitting, and a reflection on classical time series methods in the context of embedded intelligence systems.

---

## Repository Contents

| File | Description |
|------|-------------|
| `hr_time_series_analysis.ipynb` | Jupyter Notebook with full analysis, code, visualizations, and written interpretations |
| `Darshan_report.pdf` | 3-page written report summarizing all findings and analytical decisions |
| `heart_rate_data.csv` | Dataset used for the analysis |
| `README.md` | This file |

---

## Analysis Summary

The raw sensor time series was first visualized and described in terms of its visible structure, including trends, repeating patterns, fluctuations, and potential artifacts. Stationarity was then assessed both visually and statistically using the Augmented Dickey-Fuller (ADF) and KPSS tests, with results interpreted in technically precise terms.

Where the original series was found to be non-stationary, an appropriate transformation (first-order differencing) was applied and justified. The transformed series was then examined through ACF and PACF plots to identify the correlation structure and derive a plausible initial model candidate. A simple ARIMA-class model was subsequently fitted to the series, and the residuals were inspected to evaluate whether meaningful structure remained.

The notebook closes with a reflection on what classical time series models handle well in embedded intelligence contexts — such as interpretability and low computational overhead — and where their limitations become apparent, for example in the presence of non-linear dynamics or irregular sampling.

---

## How to Run

1. Clone this repository
2. Install dependencies: `pip install pandas numpy matplotlib statsmodels`
3. Open `time_series_analysis.ipynb` in Jupyter and run all cells

---

## Learning Objectives Addressed

The assignment targets the following competencies: describing the structure of a time series in precise technical language, assessing stationarity visually and with statistical tests, justifying a suitable transformation when the original series is non-stationary, using ACF and PACF plots to derive a first model candidate, and reflecting on the strengths and limits of classical time series models in an embedded intelligence context.

---

*Individual submission -- Darshan*
