



# 📊 Sales Forecasting & Visualization Project

This project focuses on analyzing and forecasting sales data using time series techniques and machine learning (XGBoost). The analysis includes exploratory visualizations, trend analysis, model training, future forecasting, and preparing outputs for integration with Power BI.

---

## 📁 Dataset

The dataset is loaded from:

```
/content/drive/MyDrive/mock_kaggle.csv
```

### Key Columns:

* `data`: Date of the record (YYYY-MM-DD format)
* `venda`: Sales value (target variable)
* `estoque`: Inventory or stock levels
* `preco`: Price of the product

---

## Project Overview

### 1. **Data Preprocessing**

* Convert `data` to datetime.
* Remove rows with `venda <= 0`.
* Create time-based features: `month`, `year`, `weekday`.
* Create a 7-day rolling average of sales as a new feature `rolling_avg`.

### 2. **Exploratory Data Analysis**

* Time-series plot of daily sales.
* Monthly and yearly sales trend plots using bar charts.

### 3. **Modeling with XGBoost**

* Train an `XGBoost Regressor` using:

  * Features: `month`, `year`, `weekday`, `estoque`, `preco`, `rolling_avg`
  * Target: `venda`
* Split data into train/test using a time-aware split (no shuffle).
* Standardize features using `StandardScaler`.

### 4. **Evaluation**

* Calculate **RMSE** and **MAE** on test data.
* Plot Actual vs Predicted sales.

### 5. **Forecasting**

* Predict sales for the next 30 days using the last known values for features.
* Save future predictions for visualization or reporting.

### 6. **Power BI Integration**

* Export data files for reporting:

  * Daily actual and predicted sales
  * Monthly sales summary
  * Yearly sales summary
  * KPI metrics (RMSE, MAE, total sales)

---

## 📈 Output Files

| File Name           | Description                                    |
| ------------------- | ---------------------------------------------- |
| `forecast_data.csv` | Daily actual vs predicted sales (for Power BI) |
| `monthly_sales.csv` | Monthly total sales                            |
| `yearly_sales.csv`  | Yearly total sales                             |
| `kpi_data.csv`      | Key performance indicators (RMSE, MAE, Total)  |

---

## Model Metrics

Evaluated using test data:

* **RMSE**: Root Mean Squared Error
* **MAE**: Mean Absolute Error
* **Total Sales**: Aggregate of all valid sales data

---

## Visualizations

1. **Sales Trend Over Time**
2. **Monthly and Yearly Bar Charts**
3. **Actual vs Predicted Sales Line Plot**

---

## 🛠 Dependencies

Make sure the following Python packages are installed:

```bash
pip install pandas matplotlib seaborn xgboost scikit-learn
```

---

## Notes

* Be sure your dataset includes the required columns and correct formats.
* This project assumes you are running in a Jupyter Notebook or Google Colab environment with access to files in `/content/`.

---

## Author & Usage

This project was developed for sales forecasting and business intelligence reporting. It can be easily extended with holidays, promotions, or external economic data to improve predictions.

Feel free to use, modify, and share!




