SQL Analysis – Global Economic & ETF Data
This section showcases SQL-driven exploration of the final trade and ETF dataset using SQLite in Python.

Table: trade_etf_data
Data loaded from final_trade_etf_data.csv
Columns include:

Month (date)

Import_Value

Export_Value

Trade_Balance

XLK_Avg_Close

Trade_Balance_%_Change

XLK_Change_%

Key SQL Insights:
Average Trade Balance across 2024

Best ETF Month (peak XLK performance)

Worst Trade Balance Month (deepest deficit)

Count of Deficit Months

Months with >5% ETF Growth

All queries were executed using SQLite via Python's sqlite3 library.