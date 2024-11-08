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
     - Data Formating of Data:Ensure that all dates,values and Customers IDs are properly formatted

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
    8. Identfy products ith no sales in the last quarter
   
    Some of the quqeries are;
    1. Retrieve the total sales for each product category:

    
              SELECT Product,SUM Quantity * UnitPrice) AS total_sales
              FROM [dbo].[CAPSTONE PROJECT] 
              GROUP BY product
       ---
     2. Identify products with no sales in the last quarter ;
   
                SELECT Distinct product
                FROM [dbo].[CAPSTONE PROJECT]
                WHERE product NOT IN (
                      SELECT Product
                      FROM [dbo].[CAPSTONE PROJECT]
                      WHERE orderDate >= DATEADD(month, -1, GETDATE())
                       )
                      ORDER BY product;
    ---
    3. Calculte monthly sales totals for the current year:

                         SELECT 
                         MONTH(Orderdate) AS month,
                         DATENAME(MONTH, Orderdate) AS month_name,
                         SUM(Quantity * UnitPrice) AS monthly_sales

                     FROM
                       [dbo].[CAPSTONE PROJECT]
                       WHERE 
                       YEAR(Orderdate) = YEAR(GETDATE())
                       GROUP BY
	                      MONTH(Orderdate),
	                      DATENAME(MONTH, Orderdate)
                        ORDER BY month;
       ---
### Inference 
     1.Top perfoming products using Excel and SQL,is "shoes".it is considered to be the perfoiming product becasue of the total sales of #613,380 which is generated to be higher than the other product
     2. Regional Breakdown;
     - IN THE NORTH:There was an increase in the total turnover with 26% in year 2023 to 2024 from #143,960 to #243,040.The product should be invested on more for a better revenue
     - IN THE SOUTH:There was a decrease of about 4% in the revenue that was generated which is about #33,820.in cases like this,it is advised to look into the cause of the decrease against the coming year 
     -IN THE EAST:There was a decline in the total revenue from #393,945 to #91,980  making it a decline of 62%.The decrease in revenue may be  as result of competitors,increase, 	hardship or unstability of the economic condition in difficulty to earn means  an all,there by resuing in the reduction in patronage by people of that particular product.It is 	advise that prices of product should be reviewed,a good relationship should be encouraged eith the old and nwe customers ,discount should be given also
     -IN THE WEST

