# Power-Bi-mobile-sales-dashboard
**Mobile Sales Dashboard Project**
**STAR Method Explanation**

**S – Situation**

- Mobile companies generate large amounts of sales data, making it difficult to track sales performance, customer behavior, and yearly growth manually.

**T – Task**

– My task was to build an interactive Power BI dashboard that could analyze mobile sales performance, track MTD sales, compare same last year data, and provide business insights.

**A – Action**

1. Data Modeling
– Used two main tables:
1) Sales_Data
2) Custom_Calendar
– Created one-to-many relationship between Date columns for time intelligence analysis.
– Created a Custom Calendar table because cumulative totals, MTD, and Same Last Year calculations require continuous date records.
– Normal sales dates may contain zero-sale days, which can affect time intelligence calculations.

2. DAX Measures
– Created important DAX measures such as:

– Total Quantity = SUM(Sales_Data[Units Sold])

– Total Sales = 
SUMX(
    Sales_Data,
    Sales_Data[Units Sold] * Sales_Data[Price Per Unit]
)

– Transaction = COUNTROWS(Sales_Data)

– Average_Price = AVERAGE(Sales_Data[Price Per Unit])

– MTD = 
TOTALMTD(
    [Total Sales],
    Custom_calendar[Date].[Date]
)

– Same Last Year Data =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(Custom_calendar[Date].[Date])
)

– DAX Usage Explanation
1) SUM() → calculated total quantity
2) SUMX() → calculated total sales
3) COUNTROWS() → counted total transactions
4) AVERAGE() → calculated average price
5) TOTALMTD() → performed Month-To-Date analysis
6) SAMEPERIODLASTYEAR() → compared sales with previous year data

3. Dashboard Development

Created an interactive Power BI dashboard with:

KPI Cards
Line Charts
Bar Charts
Column Charts
Pie / Donut Charts
Funnel Charts
Map Visualizations
Tables and Filters

Dashboard analysis included:
– Total Sales Analysis
– City-wise Sales
– Brand Performance
– Mobile Model Analysis
– Payment Method Analysis
– Customer Ratings
– Sales Trend by Month and Day

Charts Usage & Insights
– KPI Cards → displayed Total Sales, Total Quantity, Transactions, and Average Price for quick business monitoring.
– Line Chart → analyzed monthly sales trends and identified sales growth patterns over time.
– Bar Chart → compared sales performance across different mobile models.
– Column Chart → analyzed transaction count across different mobile brands.
– Pie / Donut Chart → visualized transaction distribution by payment methods.
– Funnel Chart → analyzed customer rating distribution across Good, Average, and Poor categories.
– Map Visualization → showed city-wise sales distribution and identified top-performing cities.
– MTD Chart → monitored cumulative Month-To-Date sales growth.
– Same Last Year Comparison Chart → compared current year sales with previous year performance using time intelligence analysis.

4. MTD Report
– Created Month-To-Date sales analysis dashboard to monitor daily sales growth and sales trends throughout the month.

5. Same Last Year Analysis
– Compared current sales with previous year data using:
Year-wise comparison
Quarter-wise comparison
Month-wise comparison

Used time intelligence functions for year-over-year analysis.

6. Navigation & User Experience
– Implemented page navigation buttons
– Added slicers and filters for interactive dashboard analysis
– Improved dashboard usability and report flow

**R – Result**

– The dashboard successfully provided interactive sales insights, trend analysis, and year-over-year comparisons.
– The project helped in understanding customer behavior, sales performance, top-performing brands, and business growth trends using Power BI.
