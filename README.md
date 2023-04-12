# Window Functions :window:
## Overview
 This is a bit of code from T SQL using two types of window functions that can come in handy in certain situations. 
 First I used the ROW_NUMBER function to create a unique ID to filter on which is very useful for primary and foreign keys.
 The second function I used is the OVER() function to make a custom column of total sales to compare with individual. This was all done 
 in a sub query which I then filtered out 10 records in the WHERE clause using the unique SalesKey ID that was created. 
 ## Data :bar_chart:
 The data that I used for the this came from Microsofts sample data warehouse called AdventureworksDW2019.
 This query could be used to compare employee or customer data filtered on different specifications. [AdventureworksDW2019](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksDW2019.bak)
 ## Data Set 
 ```sql 
 USE AdventureWorksDW2019;
 GO
SELECT * FROM
(SELECT ROW_NUMBER() OVER (ORDER BY fs.SalesAmount DESC) SalesKey
      ,dc.CustomerKey
      ,dc.FirstName
      ,dc.LastName
	  ,dc.EnglishOccupation
	  ,fs.SalesAmount
	  ,sum(SalesAmount) OVER() Sum_SalesAmt
FROM dbo.FactInternetSales fs
INNER JOIN dbo.DimCustomer dc
 ON fs.CustomerKey = dc.CustomerKey)Tsales
WHERE SalesKey <= 1556 AND SalesKey > 1546 
 ```



![window](https://user-images.githubusercontent.com/123023771/231597599-24151401-c721-4e8b-ad99-637e95b252f3.jpg)

## Programs Used :computer:
- Transact SQL






