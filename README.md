### LITA-CAPSTONE-PROJECT SALES DATA

PROJECT TITLE:sales analysis and performance data Using Microsoft Excel,SQL and powerBi 

### PROJECT OVERVIEW
---
This is a sales analysis that include different data set and documentation to make it easier to understand the sales perfomance of each region.Sales metrics include are:Customer ID,products bought,Region,Date of purchases,quantity purcahesed  an total sales 

### Objectives
1. To Identfy customers for each product from each region
2. To identify product performance
3. To Identify and undertand revenue resources from each region,date of purchase,quantity of product bought

### Data Sources  
This sales data is a LITA Capstone Project an open data which can be freely downloaded online through data repository site such as kaggle etc

### Tools Used
- MicrosoftExcel [Download Here](https://microsoft.com)
- SQL
- Powerbi Visualization
### Exploratory Data Analysis
---
  1.Loading and initial exploration of Data
- Using Excel
    - Opening and studying of Data:Load,the data on Excel to insectthe rows,columns and data types.
    - Remove Duplicates:This is to remove dulpicates in the data and clear them out.
    - Summary Statistics:Analyse and summarise the data using AVERAGE,AVERAGEIF,SUM,SUMIF etc To calculate total revenue,sum total of sales and Average sales ;
- Using SQL
    -  Import DAta:Import your already cleaned data,remove the empty rows and load the clean data into SQL database
    -  Inspect table structrue: Use DESCRIBE table_name;or SELECT*FROM[dbo].[CAPSTONE PROJECT] For sales
- Basic Queries:
    -     CREATE DATABASE DAMMY_db
          SELECT * FROM  [dbo].[CAPSTONE PROJECT]
  ---
 2. For Data Cleaning
  - Using Excel
     - Remove Duplicates :Use remove duplicate duplicates under the data tab to clear duplicate rows
     - Data Formating of Data:Ensure that all dates,values and Customers IDs are properly formtted

  3.  Descriptive statistics and Agregation
  -Using Excel
      1. Calculate the sales column using Quantity *Unit price
      2. Calculate the totl sales (revune) using the subtotal function
      3. calculate the average sales using the Average function
      4. Calculate the minimum range usinf the MIN function
      5. CAlcuate the maxium rang uing the MAX function
      6. calculate the average sales per product (Shirt,Shoe ,Hat,Gloves,Socks and jackets)using the IF function (AVERAGE IF)
      7. calculate the average revenue per region (NORTH,SOUTH,EAST WEST) using the SUMIF function
  - Using SQL
  - Write queries to extract key insight based on the following quetsions;
    1. Retrieve the total sales for each product category
    2. Find the number  of sales transactios in each region
    3. Find the hghest-selling product by total sales value
    4. Calculate total revenue per product
    5. Calculate Monthly sales  total sales for the current year
    6. Find the top 5 customers by total purchase amount
    7. Calculate the percentage of total sale by each region
    8. Identfy products ith no sals in the last quarter
   
    Some of the quqeries are;
    1. Retrieve the total sales for each product category:

    
              SELECT Product,SUM Quantity * UnitPrice) AS total_sales
              FROM [dbo].[CAPSTONE PROJECT] 
              GROUP BY product
       ---
     3. Identify productswith no sales in the last quarter ;
   
                SELECT Distinct product
                FROM [dbo].[CAPSTONE PROJECT]
                WHERE product NOT IN (
                      SELECT Product
                      FROM [dbo].[CAPSTONE PROJECT]
                      WHERE orderDate >= DATEADD(month, -1, GETDATE())
 )
ORDER BY product;
  .  Well desribed statistics and Aggregation

  2.Using Excel
  . Calculating the sales column (Quantity*Unit Price)
  . 
  

  
- ]in  the 
