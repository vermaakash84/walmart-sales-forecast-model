# 🛒 Walmart Sales Forecasting Model

## 📌 Project Overview
This repository contains the **machine learning pipeline for forecasting weekly Walmart sales** using historical data, store features, and external economic indicators.  
The goal is to build a **global forecasting model** that can predict sales across multiple stores and departments for future weeks.

---
## Dataset
The dataset used is the [Walmart Sales Forecasting dataset](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting).  
Please download it from Kaggle and place the CSV files (`train.csv`, `features.csv`, `stores.csv`) in the `data/` folder before running the scripts.

## 📂 Dataset
The dataset is based on the **Walmart Recruiting - Store Sales Forecasting** dataset from Kaggle.  
It contains the following key columns:

- `Store` – Store ID  
- `Dept` – Department ID  
- `Date` – Weekly date  
- `Weekly_Sales` – Target variable (weekly sales per store-dept)  
- `IsHoliday` – Whether the week includes a holiday  
- `Temperature`, `Fuel_Price`, `CPI`, `Unemployment` – External features  
- `MarkDown1–5` – Promotional markdowns  
- `Size`, `Type` – Store-level metadata  

---

## 🛠️ Methodology
1. **Data Preprocessing**
   - Handling missing values  
   - Feature engineering (lags, rolling averages, date-based features)  
   - Encoding categorical variables (store type, dept, etc.)

2. **Model Training**
   - Trained a **global XGBoost model** across all Store–Dept combinations  
   - Used **early stopping** for optimal boosting rounds  
   - Evaluated using RMSE, MAE, and MAPE

3. **Forecasting**
   - Implemented **recursive multi-step forecasting** for predicting **next 12 weeks** per Store–Dept  
   - Forecast results are stored in `future_forecasts.csv`

---

## 📊 Results
- Achieved strong performance across stores & departments with **XGBoost**.  
- Metrics (sample, for validation set):
  - RMSE ≈ *2,500*  
  - MAE ≈ *1,700*  
  - MAPE ≈ *12–15%*  

*(Exact results vary by store-dept combination.)*

---


