# 🧠 Retail Sales Forecasting with Prophet

This project uses **Facebook Prophet** to forecast retail sales trends using historical transaction data. The model is designed to support retail businesses in making data-driven decisions about future demand, inventory planning, and sales strategy.

---

## 📈 Project Objective

> **Build a predictive analytics model that helps retail businesses forecast their future sales.**  
Using monthly sales data, we train a time series forecasting model and visualize trends, seasonality, and forecasted values. The insights are intended for consulting, analytics, and retail SaaS use cases.

---

## 📂 Dataset

The dataset used is [`https://github.com/sinaaa-aaam/FUTURE_ML_01/Task 1/sales_data_sample.csv`](sales_data_sample.csv), which includes:
- Sales transactions
- Order dates
- Product and customer information

We aggregate data monthly to forecast future trends.

---

## 🔧 Process Overview

### 1. **Data Cleaning & Preprocessing**
- Removed irrelevant columns
- Parsed and standardized dates
- Handled missing data
- Aggregated sales to monthly totals

### 2. **Feature Engineering**
- Created `HOLIDAY_SEASON` flag for November and December
- Applied **log transformation** to stabilize variance
- Removed extreme outliers via clipping

### 3. **Modeling**
- Used Facebook Prophet with:
  - `seasonality_mode = 'multiplicative'`
  - Custom holiday indicators
- Added external regressor: `HOLIDAY_SEASON`
- Forecast for 6 months in advance

### 4. **Evaluation Metrics**
| Metric | Value | Description |
|--------|--------|-------------|
| **MAE**  | 97,561.35 | Avg absolute error between prediction and actual |
| **RMSE** | 271,810.21 | Penalizes large errors more than MAE |
| **MAPE** | 25.04% | Avg % error, interpretable for business users |

> 🧠 **Insight**: MAE dropped by ~55% and MAPE by ~61% compared to the baseline model. The model now offers meaningful business value.

---

## 📊 Key Insights

- **Strong seasonality** around November and December, likely driven by holiday shopping.
- Sales growth or dips are better modeled using **multiplicative seasonality**, as real-world retail performance fluctuates in percentages.
- Adding holiday features significantly improves model interpretability.

---

## 📌 Business Recommendations

- **Stock up ahead of November–December**, as data shows repeatable high sales in these months.
- **Use forecasted data for staffing and inventory planning** to reduce shortages or overstock.
- Incorporate more regressors (e.g., promotions, weather, campaigns) for even better predictions.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python | Data processing & modeling |
| Pandas / NumPy | Data cleaning & transformation |
| Facebook Prophet | Time series forecasting |
| Matplotlib | Data visualization |
| Scikit-learn | Model evaluation metrics |

---

## 🚀 Future Improvements

- Segment sales by region or product category for more granular forecasts.
- Consider using alternate models like **XGBoost**, **LSTM**, or **SARIMA** for comparison.

---
