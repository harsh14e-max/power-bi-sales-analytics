# power-bi-sales-analytics
This project is an interactive Power BI sales analytics dashboard 
# 📊 GlobalTech Sales Analytics — Power BI

## 📌 Project Overview

This project is an interactive Power BI sales analytics dashboard developed to analyze business performance across sales, customers, products, employees, and suppliers.

The dashboard focuses on transforming raw business data into meaningful KPIs and interactive visualizations that can support data-driven decision-making.

### 🎯 Objectives

- Analyze overall sales performance
- Track sales trends over time
- Identify top-performing customers
- Analyze product performance
- Compare employee performance
- Evaluate supplier performance
- Monitor key business KPIs
- Perform period-over-period analysis
- Analyze recent sales performance using rolling calculations
- Create interactive business dashboards using Power BI and DAX


## 🗂️ Dataset

The project uses a relational business dataset containing information related to:

- Sales transactions
- Customers
- Products
- Employees
- Suppliers
- Dates
- Product categories
- Business performance metrics

The dataset was modeled in Power BI to enable analysis across multiple business dimensions.


## 🧹 Data Preparation

The data was prepared and modeled before creating the dashboards.

Key preparation activities included:

- Reviewing dataset structure
- Identifying relationships between tables
- Checking data types
- Preparing date fields for time intelligence
- Creating calculated measures
- Organizing fields into appropriate analytical categories
- Establishing relationships between transactional and dimensional data


## 🧠 Power BI Data Model

The report uses a relational data model connecting the sales fact data with supporting dimensions such as:

- Customers
- Products
- Employees
- Suppliers
- Dates

This structure allows users to analyze sales from different business perspectives while maintaining consistent filtering across the report.


## 📈 Dashboard Pages

### 1. Total Sales

Provides an overview of overall sales performance.

Key analysis:

- Total sales
- Sales distribution
- Business performance overview


### 2. Parallel Period Sales

Used to compare sales performance across different time periods.

This helps identify:

- Growth or decline
- Period-over-period changes
- Changes in business performance


### 3. Product Ranking

Ranks products based on sales performance.

This helps identify:

- High-performing products
- Lower-performing products
- Relative product contribution


### 4. Total Sales by Year

Analyzes sales trends across different years.

This visualization helps identify:

- Annual sales trends
- Growth patterns
- Changes in yearly performance


### 5. Rolling 30 Days Sales

Uses a rolling 30-day calculation to analyze recent sales performance.

This provides a smoother view of short-term trends and helps reduce the impact of individual daily fluctuations.


### 6. Top 10 Clients

Identifies the highest-value customers based on sales.

This analysis can be used to understand:

- Major customers
- Customer contribution
- Revenue concentration


### 7. Unique Clients

Tracks the number of unique customers represented in the dataset.

This provides insight into:

- Customer reach
- Customer base size
- Changes in customer activity


### 8. Product Performance

Provides a detailed analysis of product-level performance.

Analysis includes:

- Product sales
- Product contribution
- Product comparison
- Performance patterns


### 9. Employee Performance

Analyzes sales performance associated with employees.

This can help identify:

- Sales contribution
- Employee-level performance
- Performance differences


### 10. Supplier Performance

Analyzes business performance related to suppliers.

This provides a way to examine:

- Supplier contribution
- Product/supplier relationships
- Supplier-level performance


### 11. KPI Dashboard

The KPI page provides a consolidated view of important business metrics.

Key metrics include:

- Total Sales
- Total Cost
- Profit
- Profit Margin
- Customer metrics
- Other calculated business indicators


## 🧮 DAX & Analytical Techniques

Several analytical calculations were implemented using DAX.

Examples include:

- Total Sales
- Total Cost
- Profit
- Profit Margin
- Unique Customer Count
- Product Ranking
- Rolling 30-Day Sales
- Parallel Period Analysis
- Time-based calculations


### Example DAX

```DAX
Total Sales =
SUM(Sales[SalesAmount])

Profit =
[Total Sales] - [Total Cost]

Profit Margin =
DIVIDE([Profit], [Total Sales], 0)

Unique Clients =
DISTINCTCOUNT(Customer[CustomerID])

Rolling 30 Day Sales = 
CALCULATE(
    [Total Sales],
    FILTER(
        ALLSELECTED(Dates),
        Dates[Date] > MAX(Dates[Date]) - 30 &&
        Dates[Date] <= MAX(Dates[Date])
    )
)

