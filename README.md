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
- Column	Data Type	Description
- OrderID	INT	Unique identifier for each order
- CustomerId	VARCHAR	Unique identifier for each customer
- Product	VARCHAR	Product name (in this case, "Gloves")
- Region	VARCHAR	Region where the sale occurred (e.g., "East")
- OrderDate	DATE	Date when the order was placed
- Quantity	INT	Number of items ordered
- UnitPrice	SMALLINT	Price per unit of the product

## Goals of the Analysis
- Calculate to Retrive the total sales for easch product category.
- find the number of sales transactions in each region.
- find the highest-selling product by total sales value..
- calculate total revenue per product.
- calculate monthly sales totals for the current year.
- find the top 5 customers by total purchase amount.
  
## Calculate to Retrive the total sales for easch product category
- we can use this SQL query 
- SELECT 
    Product, 
    SUM(Quantity * UnitPrice) AS TotalSales
FROM 
    LITA_SalesData_Project
GROUP BY 
    Product
ORDER BY 
    TotalSales DESC;
  - [Totale Sales SQL](https://github.com/user-attachments/assets/fcdd5d5b-b259-4474-9ed0-8c1e32fd30dc)
## Calculate to find the number of sales transactions in each region.
- SELECT 
    Region, 
    COUNT(*) AS NumberOfTransactions
FROM 
     [dbo].[LITA_Capstone_Saledataset]
GROUP BY 
    Region
ORDER BY 
    NumberOfTransactions DESC;
  - [Sales by Region](https://github.com/user-attachments/assets/4d9a732e-1667-4dae-ba3c-b75ee2801711)
 
## find the highest-selling product by total sales value.
  - SELECT TOP 1 
    Product, 
    SUM(Quantity * UnitPrice) as
	Total_sales_value
FROM 
    [dbo].[LITA_Capstone_Saledataset]
GROUP BY 
    Product
ORDER BY 
    Total_Sales_value DESC
  - [Highest Product](https://github.com/user-attachments/assets/19575113-7045-4e8b-abe7-9ea0423bf393)
    
## calculate total revenue per product.
- SELECT 
    Product, 
    SUM(Quantity * UnitPrice) AS TotalRevenue
FROM 
    [dbo].[LITA_Capstone_Saledataset]
GROUP BY 
    Product
ORDER BY 
    TotalRevenue DESC;
  - [Total Revenue by Sales](https://github.com/user-attachments/assets/118aa14e-dc09-49c8-83a7-4dc09d5e851a)

## calculate monthly sales totals for the current year.
- SELECT 
    MONTH (OrderDate) AS Sales_Month, 
    SUM(Quantity * UnitPrice) AS TotalSales
FROM 
    [dbo].[LITA_Capstone_Saledataset]
WHERE 
    YEAR(OrderDate) = YEAR(GETDATE())
GROUP BY 
    MONTH (OrderDate)
ORDER BY 
    Sales_Month;
  - [Sales by Month](https://github.com/user-attachments/assets/7b8572be-1f10-4360-b32c-bdfb2350d9e8)
    
## find the top 5 customers by total purchase amount.
- SELECT TOP 5 
    Customer_Id, 
    SUM(Quantity * UnitPrice) AS TotalPurchaseAmount
FROM 
    [dbo].[LITA_Capstone_Saledataset]
GROUP BY 
    Customer_Id
ORDER BY 
    TotalPurchaseAmount DESC;
  - [Top 5 Customer](https://github.com/user-attachments/assets/2e267175-a587-43db-b167-a50cb32addca)














