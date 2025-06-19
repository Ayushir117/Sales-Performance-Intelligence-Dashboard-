# Sales-Performance-Intelligence-Dashboard

# Sales Analytics Dashboard 🍕

A comprehensive data analysis project examining pizza sales performance using SQL for data processing and Excel for visualization and dashboard creation.

## 📊 Project Overview

This project analyzes pizza sales data to provide actionable business insights through key performance indicators (KPIs) and interactive visualizations. The analysis focuses on understanding sales patterns, customer preferences, and operational efficiency to support data-driven decision making.

## 🎯 Business Objectives

The primary goal is to analyze key indicators for pizza sales data to gain insights into business performance, specifically focusing on:

- Revenue optimization and trend analysis
- Customer ordering behavior patterns
- Product performance evaluation
- Operational efficiency insights

## 📈 Key Performance Indicators (KPIs)

### Primary Metrics Analyzed:

1. **Total Revenue**: $817,860
   - Sum of total price of all pizza orders

2. **Average Order Value**: $38.31
   - Average amount spent per order (Total Revenue ÷ Total Orders)

3. **Total Pizzas Sold**: 49,574
   - Sum of quantities of all pizzas sold

4. **Total Orders**: 21,350
   - Total number of orders placed

5. **Average Pizzas Per Order**: 2.32
   - Average number of pizzas sold per order (Total Pizzas ÷ Total Orders)

## 📊 Dashboard Features

### Interactive Visualizations

1. **Daily Trend Analysis**
   - Bar chart displaying daily order patterns
   - Identifies peak and low-demand days
   - **Key Insight**: Highest orders on Friday/Saturday evenings

2. **Hourly Trend Analysis**
   - Line chart showing hourly order distribution
   - Identifies peak ordering hours (12-1pm and 5-8pm)
   - Supports staffing and inventory planning

3. **Sales Distribution by Category**
   - Pie chart showing percentage of sales by pizza category
   - Categories: Classic (26.91%), Supreme (25.46%), Chicken (23.96%), Veggie (23.68%)

4. **Sales Distribution by Size**
   - Pie chart representing sales percentage by pizza size
   - Large pizzas contribute to maximum sales (45.89%)

5. **Performance Analysis**
   - **Top 5 Best Sellers**: Classic Deluxe, Barbecue Chicken, Hawaiian, Pepperoni, Thai Chicken
   - **Bottom 5 Performers**: Brie Carre (lowest seller)
   - Funnel chart showing total pizzas sold by category

6. **Timeline Analysis**
   - Interactive date slicer for quarterly analysis (2015-2017)
   - Enables period-specific performance evaluation

## 🛠️ Tools & Technologies

- **SQL**: Data extraction, transformation, and analysis
- **Microsoft Excel**: Dashboard creation, data visualization, and KPI calculations
- **Data Visualization**: Interactive charts and graphs
- **Business Intelligence**: KPI development and trend analysis

## 🔍 Key Insights & Findings

### Operational Insights:
- **Peak Days**: Friday and Saturday evenings show highest order volumes
- **Peak Hours**: 12-1pm (lunch) and 5-8pm (dinner) are maximum order times
- **Size Preference**: Large pizzas dominate sales (45.89% of total sales)

### Product Performance:
- **Balanced Category Performance**: All pizza categories show relatively even distribution (23-27%)
- **Top Performers**: Classic and chicken-based pizzas lead in popularity
- **Underperformers**: Specialty items like Brie Carre need attention

### Business Recommendations:
- Optimize staffing during peak hours (12-1pm, 5-8pm)
- Focus inventory on large-size pizzas
- Promote underperforming specialty items
- Leverage weekend marketing for maximum impact

## 📊 Sample Queries

### Total Revenue Calculation
```sql
SELECT SUM(total_price) AS Total_Revenue
FROM pizza_sales;
```

### Average Order Value
```sql
SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS Avg_Order_Value
FROM pizza_sales;
```

### Daily Trend Analysis
```sql
SELECT TO_CAHR( order_date, HOUR) AS order_day, 
       COUNT(DISTINCT order_id) AS total_orders
FROM pizza_sales
GROUP BY TO_CAHR( order_date, HOUR);
```
