# FUTURE_DS-A_01
#📊 E-Commerce Sales Dashboard – Power BI
A complete end-to-end data analysis project using Power BI, DAX, and business storytelling.
This dashboard helps stakeholders understand sales performance, top-selling products, customer demographics, and payment behavior.

#🚀 Project Overview
This project analyzes an e-commerce dataset to uncover actionable business insights such as:
Best-selling products
Revenue-generating categories
Monthly sales trends
Demographic contribution
Region-wise performance
Payment method preferences
The final output is a fully interactive Power BI Dashboard with slicers, KPIs, and drill-down insights.

#📁 Files in This Repository
File	Description
orders.csv	Order-level transaction data
customers.csv	Customer demographic profile
products.csv	Product catalog with categories
categories.csv	Product category mapping
PowerBI_Ecommerce_Dashboard.pbix	Final Power BI dashboard
README.md	Project documentation

#🛠️ Tools & Technologies
Power BI Desktop
Power Query (M)
DAX
Data Modeling (Star Schema)

#📊 Dashboard Features
1. KPI Cards
Total Sales
Total Profit
Total Orders
Average Order Value (AOV)

2. Visualizations
Monthly Sales Trend (Line Chart)
Sales by Category (Treemap)
Top Products (Bar Chart)
Sales by Region (Column Chart)
Sales by Payment Method (Donut Chart)
Sales by Gender (Bar Chart)
Sales by Age Group (Bar Chart)

3. Slicers
Date Range
Category
Region
Order Status
Year

#🔢 Essential DAX Measures
Below are all the core DAX measures used to build the dashboard.
1. Total Sales
Total Sales = SUM(Orders[SalesAmount])

2. Total Quantity
Total Quantity = SUM(Orders[Quantity])

3. Total Profit
Total Profit =
SUMX(
    Orders,
    (Orders[UnitPrice] - RELATED(Products[CostPrice])) * Orders[Quantity]
)

4. Average Order Value (AOV)
AOV = DIVIDE([Total Sales], DISTINCTCOUNT(Orders[OrderID]))

5. Sales YoY %
Sales YoY % =
VAR Curr = [Total Sales]
VAR Prev = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DateTable[Date]))
RETURN IF(ISBLANK(Prev), BLANK(), DIVIDE(Curr - Prev, Prev))

6. Orders Count (Optional)
Orders Count = DISTINCTCOUNT(Orders[OrderID])

#🏗️ Data Modeling
The data model follows a Star Schema:
Fact Table: Orders
Dimensions: Products, Customers, Categories, Date
This ensures optimized relationships and faster calculations.

#🔍 Key Insights
Accessories is the top revenue-generating category.
West region contributes the highest sales.
Female customers drive a major portion of revenue.
Age group 36–50 purchases the most.
Card & NetBanking are the most preferred payment modes.

#📚 Learning Outcomes
Data Cleaning using Power Query
Creating DAX Measures
Designing KPIs
Building a Date Table
Interactive Dashboard Design
Business Storytelling with Data

#🧑‍💻 Author
Udit Prajapati
Power BI | Data Analytics | Python | SQL
