# Mobile Sales Analytics Dashboard | Power BI
## Project Overview
The Mobile Sales Analytics Dashboard is an interactive Power BI project designed to analyze mobile sales performance across cities, brands, mobile models, payment methods, customer ratings, and time periods. It helps identify sales trends, evaluate business performance, and generate actionable insights through interactive visualizations and DAX measures.
## Business Problem
Mobile businesses need a clear view of their sales performance to understand which cities and brands contribute the most revenue, how customer purchasing behavior changes over time, and where improvements may be required. This project uses data analytics and visualization to support data-driven business decisions.
## Business Questions
- What are the total sales, transactions, and units sold?
- Which cities contribute the most to total sales?
- Which mobile brands and models generate the highest revenue?
- Which payment methods are most frequently used?
- How are sales distributed across customer rating categories?
- Which months and days show higher sales activity?
- How do monthly sales compare with the same period last year?
- How can Month-to-Date (MTD) sales help monitor current performance?
## Tools and Technologies
| Tool | Purpose |
|---|---|
| Power BI | Dashboard development and visualization |
| Power Query | Data cleaning and transformation |
| DAX | Measures and time-based calculations |
| Microsoft Excel | Dataset storage and initial inspection |
## Dataset Information
- **Dataset:** Mobile Sales Data.xlsx
- **Records:** 3,835 rows
- **Date Coverage:** October 2021 to October 8, 2024
- **Key Columns:** Units Sold, Price Per Unit, Day, Month, Year, Day Name, City, Brand, Mobile Model, Customer Ratings, Payment Method
- **Sales Calculation:** Units Sold × Price Per Unit
## Dashboard Features
### 1. Overall Sales Performance
- Total Sales
- Total Transactions
- Total Quantity Sold
- Average Price
- Sales by City
- Sales by Brand and Mobile Model
- Payment Method Analysis
- Customer Rating Analysis
### 2. Month-to-Date (MTD) Analysis
- Tracks cumulative sales from the beginning of the selected month through the selected date.
- Helps monitor current-month performance.
- Supports comparisons across dates and months when the date model is configured correctly.
### 3. Same Period Last Year (SPLY) Analysis
- Compares sales with the equivalent period in the previous year.
- Helps identify growth and decline patterns.
- Supports year-over-year performance evaluation.
## Key Insights
- Total sales were approximately **₹769 million** across 3,835 transactions.
- Total quantity sold was approximately **19,000 units**.
- Average price per unit was approximately **₹40,000**.
- Delhi contributed approximately **₹204 million** in sales, while Mumbai contributed approximately **₹127 million**.
- Apple generated approximately **₹162 million** in sales.
- The iPhone SE generated approximately **₹60 million** in sales.
- Around 61% of transactions were classified as Good customer ratings, 17% as Average, and 22% as Poor under the project's rating classification.
- July recorded relatively high monthly sales quantity, while February was comparatively lower.
- Annual sales were approximately ₹262 million in 2022 and ₹253 million in 2023, representing a decline of about 3.3%.
**Note:** These figures are approximate and should be checked against the final Power BI dashboard before publication. The 2021 and 2024 periods are partial years, so direct annual comparisons require caution.
## Important DAX Measures
### Total Sales
```dax
Total Sales =
SUMX(
    Sales_data,
    Sales_data[Units Sold] * Sales_data[Price Per Unit]
)
```
### Total Transactions
```dax
Transactions =
COUNTROWS(Sales_data)
```
### Total Quantity Sold
```dax
Total Quantity =
SUM(Sales_data[Units Sold])
```
### Average Price
```dax
Average Price =
AVERAGE(Sales_data[Price Per Unit])
```
### Rating Percentage
```dax
Rating % =
DIVIDE(
    [Transactions],
    CALCULATE(
        [Transactions],
        ALL(Sales_data[Rating_status])
    )
)
```
### Month-to-Date Sales
```dax
MTD Sales =
TOTALMTD(
    [Total Sales],
    'DateTable'[Date]
)
```
**Note:** The MTD measure requires a valid date table related to the sales data. Update table and column names to match your Power BI model.
## Data Preparation
- Imported the mobile sales dataset from Excel into Power BI.
- Checked column names, data types, and missing or inconsistent values.
- Calculated sales using quantity multiplied by price per unit.
- Created DAX measures for key performance indicators.
- Created a customer rating classification for analysis.
- Used time intelligence calculations for MTD and SPLY analysis.
- Reviewed date fields and day-name values for consistency.
## Business Recommendations
- Investigate the factors contributing to strong sales in cities such as Delhi and Mumbai.
- Review the performance of brands and models with high sales and evaluate opportunities for other products.
- Use monthly sales trends to plan inventory and promotional activities.
- Monitor customer rating categories to identify areas where customer experience may need improvement.
- Review payment method usage when planning checkout and payment options.
- Use MTD and SPLY metrics to monitor performance and identify periods that need further investigation.
**These recommendations identify opportunities for further analysis. The dashboard alone does not establish the causes behind sales or customer behavior.**
## Future Improvements
- Add sales forecasting to estimate future performance.
- Include profit and margin analysis if cost data becomes available.
- Improve data validation and standardization.
- Add additional customer and product segmentation.
- Enhance the dashboard with more time-based comparisons.
## What I Learned
- Building interactive dashboards in Power BI.
- Writing DAX measures for sales KPIs.
- Using Power Query for data preparation.
- Applying time intelligence functions such as TOTALMTD.
- Analyzing sales trends and customer behavior.
- Translating business questions into measurable insights.
## Acknowledgment
This project was developed as a learning exercise in Power BI and data analytics, following a guided mobile sales dashboard project by Satish Dhawale.
## Author
**Rutik Tetare**
