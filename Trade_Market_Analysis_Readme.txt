# Global Trade Market Analysis

This project explores the relationship between international trade performance and financial market trends, using U.S. Advanced Technology Products (ATP) trade data and the XLK Technology ETF performance over the year 2024.

## Objective

To analyze how fluctuations in monthly trade balances impact stock market behavior and to extract business insights using EDA, machine learning, KPIs, ad hoc SQL queries, and a Tableau dashboard.

---

## Data Sources

- **Trade Data**: Monthly import and export values for multiple countries in 2024 (filtered for ATP).
- **Finance Data**: Historical price data for global ETFs and indices (specifically the XLK ETF for this analysis).

---

## Data Pipeline

1. **ETL**:
   - Fetched trade data from government Excel files.
   - Pulled ETF data using the `yfinance` API.
   - Saved raw CSVs in organized folders.

2. **Data Cleaning**:
   - Filtered for 2024 data only.
   - Reshaped wide import/export columns to long format.
   - Calculated monthly trade balance.
   - Merged trade and finance data on the `Month` column.

3. **Feature Engineering**:
   - Created percentage change columns for trade balance and ETF.
   - Prepared final dataset for modeling and visualization.

---

## Exploratory Data Analysis (EDA)

- Trade balance remained negative throughout the year.
- ETF prices generally increased despite worsening trade balance.
- A dual-line plot and correlation matrix explored relationships between metrics.
- Correlation between `Import_Value` and `Trade_Balance`: **-0.85**
- Correlation between `Trade_Balance` and `XLK_Avg_Close`: **-0.42**
- Indicates market behavior is influenced by more than trade alone.

---

## Key Performance Indicators (KPIs)

| KPI                             | Value                            |
|----------------------------------|----------------------------------|
| Avg Monthly Trade Balance       | -27,154.77M USD (Deficit)        |
| Best ETF Month                  | June 2024                        |
| Highest Export Month            | August 2024                      |
| Worst Trade Balance Month       | September 2024 (-34,443.79M USD)|
| ETF Volatility                  | 3.51%                            |
| Months in Deficit               | 9                                |
| Months in Surplus               | 0                                |
| Total ETF Growth in 2024        | 18.27%                           |

---

## Ad Hoc Analysis

1. **ETF Gains Despite Deficit**  
   - XLK ETF rose in 7 months despite negative trade balance.
2. **ETF Drop in High Export Month**  
   - ETF declined in August even with highest export value.
3. **Correlation Analysis**  
   - Weak correlation (-0.03) between trade balance % change and ETF % change.

---

## Machine Learning

- Built a Linear Regression model to predict ETF prices based on trade data.
- Achieved R² Score of **0.57**, indicating moderate predictive power.
- Explored Ridge and Random Forest models, but Linear Regression performed best.

---

## Tableau Dashboard

A fully interactive dashboard was created to:
- Visualize KPI metrics.
- Track monthly trade and ETF trends.
- Provide visual insights from EDA and ad hoc results.

---

## SQL Insights

Used SQLite to:
- Load and query the final dataset.
- Validate KPIs and ad hoc patterns using SQL.
- Enable downstream integration with BI tools.

---

## Folder Structure

```
global_econ_intelligence_project/
│
├── Data/
│   ├── Raw/        <- All raw CSV and Excel files
│   └── Clean/      <- Final merged datasets for modeling and Tableau
│
├── Notebooks/
│   ├── fetch_market_data.ipynb
│   ├── trade_data.ipynb
│   ├── trade_vs_finance_analysis.ipynb
│   └── ML_trade_vs_etf_prediction.ipynb
│
├── Dashboard/
│   ├── Global_Economic_and_ETF_KPI_Dashboard_(2024).twbx
│   ├── Dashboard Screenshot.png
│   └── README.md
│
├── SQL/
│   ├── trade_etf_data.db
│   └── sql_queries.ipynb

└── README.md        <- This file
```

---

## Conclusion

This project demonstrates how trade metrics and financial indicators can be integrated into a unified data pipeline for insights, forecasting, and visualization. While trade balance alone doesn't explain ETF behavior, it provides meaningful context when analyzed alongside stock performance.

---

## Author

Shreya Kolte  
Master's in Data Science, University of Arizona  
GitHub: [shreyakolte](https://github.com/shreyakolte)

