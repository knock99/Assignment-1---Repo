# Assignment-1 Window Functions
## Overview
 This is a bit of code from T SQL using two types of window functions that can come in handy in certain situations. 
 First I used the ROW_NUMBER function to create a unique ID to filter on which is very useful for primary and foreign keys.
 The second function I used is the OVER() function to make a custom column of total sales to compare to. This was all done 
 in a sub query which I then filtered out records in the WHERE clause using the unique SalesKey ID that was created. 
 ## Data
 The data that I used for the this came from Microsofts sample data warehouse called AdventureworksDW2019.
 This query could be used to compare employee or customer data filtered on different specifications. [AdventureworksDW2019](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksDW2019.bak)
 ## Data Set
 
