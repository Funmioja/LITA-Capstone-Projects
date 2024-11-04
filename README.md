#### LITA-Capstone-Projects
### Sales Data Analysis Report on Capstone project
## Overview
This report provides an initial exploration of a sales dataset to identify key insights and trends. 
I performed a basic analysis using pivot tables and Excel formulas to calculate metrics, 
such as total sales by product, region, and month, along with average sales per product and total revenue by region. 
Additional analyses were conducted to uncover interesting patterns in the data, which can help inform business decisions.

## Data Summary
The dataset contains the following columns:
- OrderID: Unique identifier for each order
- Customer Id: Identifier for the customer who placed the order
- Product: Product type (in this case, "Gloves" is the only product category)
- Region: Sales region (in this dataset, only the "East" region is present)
- OrderDate: Date of the order
- Quantity: Quantity of products ordered
- UnitPrice: Price per unit of the product

## Analysis Goals
- Summarize total sales (revenue) by product, region, and month.
- Calculate average sales per product.
- Determine total revenue by region.
- Highlight additional insights, such as monthly trends, top customers, and year-over-year performance.

## Data Preparation
To facilitate analysis, I calculated Total Sales by adding a new column using the formula:
Total Sales = Quantity * UnitPrice
- [Total Sale](https://github.com/user-attachments/assets/37178c9a-82bb-42ac-8d31-d6769a501c03)

## Summary of Total Sales by Product, Region, and Month
I used a pivot table to analyze Total Sales by:
- Product: Grouped by each product category.
- Region: Grouped by each sales region.
- Month and Year: Grouped by month and year of the OrderDate field.
- [Summary of Total Sales, Region and Month](https://github.com/user-attachments/assets/d25a6e14-b853-44b3-8db0-92241fea2a3b)

## Average Sales per Product
To analyze average revenue generated per product, I calculated the average Total Sales for each product.
Code used what the:
=AVERAGEIF Function (product column, "product name", total sales)
- [Average sales of all Product ](https://github.com/user-attachments/assets/f7002a78-9831-4a18-b9cb-cd6df708c7f5)

## Total Revenue by Region
Using a SUMIF formula, I calculated the total revenue for each region as follows:
- =SUMIF(Region, "Region Name", Total Sales)
- [Total Revenue by Region](https://github.com/user-attachments/assets/1514d496-15a5-4c37-9466-2c5287ef456d)

### Summary
This initial analysis provides a foundational understanding of the sales data and highlights 
key insights such as monthly trends, high-revenue customers, and revenue performance.

### SQL Sales Data Analysis Report
## Overview
This report provides SQL queries for an initial exploration of sales data. 
The analysis focuses on calculating total sales by product, region, and month, 
as well as deriving additional metrics like average sales per product and total revenue by region. 
These SQL queries can be used to quickly gather insights into the data for reporting and decision-making.

## Table Structure
Assume we have a table called sales_data with the following structure:


