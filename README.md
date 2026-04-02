# 🏥 Predictive Analysis of Chronic Disease Morbidity — PEMEX

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-Gradient%20Boosting-9cf)
![Prophet](https://img.shields.io/badge/Prophet-Time%20Series-blueviolet)
![PowerBI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

A dual-pronged analytical framework applied to **official PEMEX morbidity data (2016–Q1 2025)** to identify the key drivers of chronic disease incidence and forecast case volumes for the next two years — broken down by 8 demographic groups.

Results are consolidated in a **3-page interactive Power BI dashboard**.

---

## 🎯 Objectives

1. **Explanatory Analysis** — Identify which pathological conditions most significantly drive chronic disease incidence using LightGBM + SHAP
2. **Predictive Forecasting** — Forecast chronic disease cases for the next 8 quarters (2025-Q2 to 2027-Q1) using Prophet

---

## 🔬 Methodology

### Part 1 — Explanatory Modeling (LightGBM + SHAP)

| Step | Detail |
|---|---|
| Data Source | Annual PEMEX morbidity records, 2016–2022 |
| Feature Engineering | Age-based demographic groups (e.g., `0-15_F`, `60+_M`), chronic disease target variable |
| Model | LightGBM Regressor, tuned with `RandomizedSearchCV` |
| Validation | Learning curves, validation curves, residual analysis |
| Interpretability | SHAP values — revealed that malnutrition and pneumonia are strong predictors of chronic disease |

### Part 2 — Time Series Forecasting (Prophet)

| Step | Detail |
|---|---|
| Data Source | Quarterly PEMEX data, 2023–Q1 2025 |
| Challenge | Mixed granularity: annual (2016–2022) + quarterly (2023–2025) |
| Solution | Temporal disaggregation using real seasonal patterns as reference |
| Model Selection | Prophet outperformed SARIMA on this dataset |
| Tuning | Grid search over `changepoint_prior_scale`, `seasonality_prior_scale`, `seasonality_mode` |
| Output | 8-quarter forecast per demographic group with prediction intervals |

---

## 📊 Deliverables

| Deliverable | Description |
|---|---|
| Explanatory Insights | SHAP feature importance ranking for chronic disease predictors |
| Time Series Forecast | 2-year forecast for 8 demographic groups with uncertainty intervals |
| Power BI Dashboard | 3-page interactive dashboard (historical, drivers, forecast) |
| Exported Data | `importancias_lightgbm.csv`, `pronostico_prophet.csv` |

---

## 📁 Project Structure

```
Predictive_Analysis_of_Chronic_Disease_Morbidity_PEMEX/
├── Databases/              # Raw and processed datasets
├── Notebook/               # Jupyter notebooks (EDA, modeling, forecasting)
├── PowerBi Dashboard/      # .pbix file and screenshots
└── README.md
```

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.10+ |
| ML / Explainability | LightGBM, SHAP, Scikit-learn |
| Time Series | Prophet, SARIMA (statsmodels) |
| Data | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, Power BI |
| Notebook | Jupyter / Google Colab |

---

## 🚀 Getting Started

```bash
git clone https://github.com/Pavel-Aguilar/Predictive_Analysis_of_Chronic_Disease_Morbidity_PEMEX.git
cd Predictive_Analysis_of_Chronic_Disease_Morbidity_PEMEX
pip install lightgbm shap prophet scikit-learn pandas matplotlib seaborn
```

Open the notebooks in `Notebook/` sequentially — EDA first, then modeling, then forecasting.

---

## 👤 About

Built as part of the Master's in AI & Data Analytics at UACJ. This project applies ML and time series forecasting to real public health data from one of Mexico's largest state-owned enterprises.

[![GitHub](https://img.shields.io/badge/GitHub-Pavel--Aguilar-181717?logo=github)](https://github.com/Pavel-Aguilar)

---

## 📄 License

[MIT License](LICENSE)
