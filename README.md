# Real Estate Sales Analysis Dashboard

## 🏠 Project Overview

**Real Estate Sales Analysis Dashboard** is an interactive **Microsoft
Power BI** business intelligence project designed to analyze real-estate
sales performance across properties, cities, localities, categories,
stores, customers, and time.

The report combines transactional sales data with customer,
product/property, store, and calendar dimensions. It provides KPI cards,
interactive slicers, charts, and detailed analytical visuals to help
understand **sales, profit, sale price, transactions, customers,
discounts, property performance, and days on market**.

The dashboard uses a modern visual design with a city-night background
and is intended to provide an executive-friendly view of real-estate
business performance.

------------------------------------------------------------------------

## 🎯 Project Objectives

The main objectives of this project are to:

-   Monitor overall **real-estate sales performance**.
-   Track **total sales, total profit, transactions, customers, and
    average sale price**.
-   Analyze sales performance across **property categories**.
-   Compare profitability across **cities and localities**.
-   Analyze **average discount percentage** by category.
-   Examine **cost price, gross sales, and profit** by category.
-   Analyze the **average number of days properties remain on the
    market**.
-   Provide interactive filtering by **date, city, category, and
    locality**.
-   Demonstrate practical Power BI and DAX skills through an interactive
    analytical dashboard.

------------------------------------------------------------------------

## 🛠️ Tools & Technologies

  -----------------------------------------------------------------------
  Tool / Technology                   Purpose
  ----------------------------------- -----------------------------------
  **Microsoft Power BI**              Dashboard development and
                                      visualization

  **Power Query**                     Data preparation and transformation

  **DAX**                             Measures and analytical
                                      calculations

  **Power BI Data Model**             Relationships between fact and
                                      dimension tables

  **Power BI Visuals**                KPI cards, charts, slicers and
                                      tables
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 🗂️ Data Model

The project follows a dimensional / star-schema-style architecture with
a central sales fact table and supporting dimensions.

### Fact Table

### `Fact Sales`

The central transaction table contains the real-estate sales information
used for analysis.

Important analytical fields/measures include:

-   Sales
-   Profit
-   Cost Price
-   Gross Sales
-   Category
-   Average Sale Price
-   Transactions
-   Customers
-   Discount
-   Days on Market

------------------------------------------------------------------------

### Dimension Tables

### `Dim Customer`

Used for customer-related analysis.

The model contains customer information that can be used to analyze the
customer base and customer-related sales activity.

------------------------------------------------------------------------

### `Dim Product`

This dimension contains property/product attributes.

Important fields used in the dashboard include:

-   City
-   Locality
-   Category

These fields enable geographical and property-category analysis.

------------------------------------------------------------------------

### `Dim Store`

The store dimension contains location/store-related information.

An important field used by the dashboard is:

-   City

This supports city-level profitability analysis.

------------------------------------------------------------------------

### `DIM CALENDAR`

The calendar dimension supports date-based filtering and analysis.

The report uses:

-   Date

This enables users to filter the dashboard based on the selected date
range.

------------------------------------------------------------------------

## 🔗 Data Model Structure

``` text
                  ┌─────────────────┐
                  │  Dim Customer   │
                  └────────┬────────┘
                           │
                           │
┌─────────────────┐        │        ┌─────────────────┐
│   Dim Product   │────────┼────────│    Dim Store    │
│ City            │        │        │ City            │
│ Locality        │        │        └─────────────────┘
│ Category        │        │
└─────────────────┘        │
                           │
                    ┌──────▼──────┐
                    │  Fact Sales │
                    │ Sales       │
                    │ Profit      │
                    │ Cost Price  │
                    │ Gross Sales │
                    │ Discounts   │
                    └──────┬──────┘
                           │
                    ┌──────▼──────┐
                    │ DIM CALENDAR│
                    │ Date        │
                    └─────────────┘
```

> The diagram represents the high-level analytical model. The actual
> relationships are maintained inside the Power BI model.

------------------------------------------------------------------------

## 📑 Report Pages

The PBIX contains **two report pages**.

### 1. OverView

The **OverView** page is the KPI and high-level analytical page.

It contains:

-   Date slicer
-   City slicer
-   Category slicer
-   KPI card
-   Sales by category analysis
-   Profit by locality analysis
-   Average discount by category
-   Cost price, profit and gross sales comparison by category

### 2. Overview

The **Overview** page provides a more detailed view of the real-estate
data.

It contains:

-   Date slicer
-   City slicer
-   Category slicer
-   Locality slicer
-   Sales percentage by category
-   Profit by city
-   Average days on market by city
-   Total sales by locality
-   Detailed city-level table

------------------------------------------------------------------------

## 📌 Key Performance Indicators

The dashboard's primary KPI card contains the following measures:

### Average Sale Price

Represents the average sale price of the properties/transactions in the
selected filter context.

``` text
Avg Sale Price
```

### Total Sales

Represents the total sales generated.

``` text
Total Sales
```

### Total Transactions

Represents the total number of real-estate transactions.

``` text
Total Transactions
```

### Total Profit

Represents the overall profit generated.

``` text
Total Profit
```

### Total Customers

Represents the total number of customers in the selected analysis
context.

``` text
Total Customers
```

These KPIs provide a quick executive summary of the selected real-estate
data.

------------------------------------------------------------------------

## 🎛️ Interactive Filters

The dashboard uses multiple slicers to make the analysis interactive.

### Date

``` text
DIM CALENDAR → Date
```

Allows users to analyze performance for a selected date or date range.

### City

``` text
Dim Product → City
```

Filters the dashboard based on city.

### Category

``` text
Dim Product → Category
```

Allows users to analyze specific real-estate/property categories.

### Locality

``` text
Dim Product → Locality
```

Available on the detailed Overview page and allows locality-level
analysis.

------------------------------------------------------------------------

## 📊 Visualizations

The project contains several types of Power BI visualizations.

### Sales by Category

A line chart compares:

``` text
Category
        ↓
Total Sales
```

This allows users to identify which categories generate the highest
sales.

------------------------------------------------------------------------

### Profit by Locality

A bar chart compares:

``` text
Locality
        ↓
Total Profit
```

This helps identify profitable localities.

------------------------------------------------------------------------

### Average Discount by Category

A pie chart displays:

``` text
Category
        ↓
Average Discount %
```

This provides a category-level view of discount patterns.

------------------------------------------------------------------------

### Cost Price vs Profit vs Gross Sales

A multi-series line chart compares:

``` text
Category
   ├── Cost Price
   ├── Profit
   └── Gross Sales
```

This helps evaluate the relationship between acquisition/cost price,
gross sales and resulting profit.

------------------------------------------------------------------------

### Sales Percentage by Category

A column chart displays:

``` text
Category
        ↓
% Sales by Category
```

This identifies each category's contribution to overall sales.

------------------------------------------------------------------------

### Profit by City

A pie chart compares:

``` text
City
   ↓
Profit
```

This provides a geographical view of profitability.

------------------------------------------------------------------------

### Average Days on Market

A table displays:

``` text
City
   ↓
Avg Days on Market
```

This helps understand how long properties remain on the market across
cities.

------------------------------------------------------------------------

### Total Sales by Locality

A column chart compares:

``` text
Locality
        ↓
Total Sales
```

This enables detailed locality-level sales analysis.

------------------------------------------------------------------------

## 🧮 DAX Measures

The dashboard uses several measures for real-estate business analysis.

The measures identified in the report include:

``` text
Avg Sale Price
Total Sales
Total Transactions
Total Profit
Total Customers
Avg Discount %
% Sales by Category
Avg Days on Market
```

The dashboard also uses direct aggregations of transactional fields such
as:

``` text
Sales
Profit
CostPrice
GrossSales
```

### Example DAX Patterns

A typical total sales measure can be implemented as:

``` dax
Total Sales =
SUM('Fact Sales'[Sales])
```

A typical total profit measure:

``` dax
Total Profit =
SUM('Fact Sales'[Profit])
```

An average sale price can follow the pattern:

``` dax
Avg Sale Price =
AVERAGE('Fact Sales'[SalePrice])
```

A percentage-of-total measure can use `DIVIDE` and `CALCULATE`, for
example:

``` dax
% Sales by Category =
DIVIDE(
    [Total Sales],
    CALCULATE(
        [Total Sales],
        ALL('Dim Product'[Category])
    )
)
```

> The examples above demonstrate the DAX patterns represented by the
> report. Exact column/measure definitions should be checked in Power
> BI's Model view before modifying the PBIX.

------------------------------------------------------------------------

## 🔍 Business Questions Answered

The dashboard can be used to answer questions such as:

1.  What is the total sales generated?
2.  What is the total profit?
3.  What is the average sale price?
4.  How many transactions have taken place?
5.  How many customers are represented?
6.  Which property category generates the highest sales?
7.  What percentage of sales comes from each category?
8.  Which locality generates the highest profit?
9.  Which city contributes the most profit?
10. Which categories have the highest average discount?
11. How do cost price, profit and gross sales compare across categories?
12. Which cities have properties with the highest average days on
    market?
13. Which localities generate the highest total sales?
14. How do results change when a specific city, category, locality or
    date range is selected?

------------------------------------------------------------------------

## 📈 Analytical Workflow

The dashboard supports the following analysis flow:

``` text
Date Selection
      ↓
City Selection
      ↓
Category Selection
      ↓
Locality Selection
      ↓
      KPIs
      ↓
Sales Analysis
      ↓
Profit Analysis
      ↓
Discount Analysis
      ↓
Days-on-Market Analysis
```

Because the visuals respond to slicer selections, users can perform both
high-level and granular analysis from the same report.

------------------------------------------------------------------------

## 🧠 Skills Demonstrated

This project demonstrates practical knowledge of:

-   Microsoft Power BI
-   Power BI dashboard design
-   Data modeling
-   Star-schema concepts
-   Fact and dimension tables
-   DAX measures
-   `SUM`
-   `AVERAGE`
-   `DIVIDE`
-   `CALCULATE`
-   Percentage-of-total analysis
-   KPI development
-   Interactive slicers
-   Real-estate sales analytics
-   Geographical analysis
-   Category analysis
-   Profitability analysis
-   Discount analysis
-   Days-on-market analysis
-   Business intelligence reporting
-   Data storytelling

------------------------------------------------------------------------

## 🚀 How to Open the Project

### Prerequisites

Install:

-   **Microsoft Power BI Desktop**
-   A compatible Windows environment

### Steps

1.  Download the `.pbix` file.
2.  Open `real_estate_(1).pbix` using **Power BI Desktop**.
3.  Wait for the report to load.
4.  Navigate between **OverView** and **Overview**.
5.  Review the KPI cards.
6.  Use the Date, City, Category and Locality slicers.
7.  Interact with the charts and table.
8.  Open the **Model** view to inspect relationships.
9.  Open the **Data** view to inspect the underlying tables.
10. Review the DAX measures used by the report.

------------------------------------------------------------------------

## 📁 Project Structure

``` text
Real-Estate-PowerBI/
│
├── real_estate.pbix
└── README.md
```

------------------------------------------------------------------------

## 💼 Business Use Cases

This dashboard can support:

-   Real-estate sales management
-   Property performance analysis
-   City-level market analysis
-   Locality-level sales analysis
-   Profitability analysis
-   Discount strategy analysis
-   Property category comparison
-   Sales performance monitoring
-   Customer and transaction analysis
-   Market performance reporting

------------------------------------------------------------------------

## 🔮 Future Enhancements

Potential improvements include:

-   Add property price trend analysis.
-   Add monthly and yearly sales trends.
-   Add profit margin %.
-   Add year-over-year sales growth.
-   Add month-over-month sales growth.
-   Add top-performing properties.
-   Add top-performing cities and localities.
-   Add property type comparison.
-   Add average property price by locality.
-   Add sales volume forecasting.
-   Add days-on-market trend analysis.
-   Add interactive map visualization.
-   Add drill-through pages for individual properties.
-   Add customer segmentation.
-   Add Power BI Service publishing and scheduled refresh.
-   Add automated data refresh from a real-estate database.

------------------------------------------------------------------------

## ⭐ Project Summary

The **Real Estate Sales Analysis Dashboard** transforms transactional
real-estate data into an interactive Power BI business intelligence
solution.

By combining a dimensional data model, DAX measures, KPI cards,
geographical analysis, category analysis, discount analysis, and
days-on-market metrics, the dashboard provides a comprehensive view of
real-estate business performance.

The project demonstrates practical skills in **Power BI, DAX, data
modeling, interactive visualization, and business analytics**, making it
suitable for a portfolio, academic project, or data analyst interview.

------------------------------------------------------------------------

## 👨‍💻 Author

**Yeshwanth**

**Power BI \| Data Analytics \| DAX \| Business Intelligence**
