---
lab:
    title: 'Get started with Azure Data Studio'
    module: 'Module 1: Exploring SQL Server query tools'
---

# Lab: Get started with Azure Data Studio
 
In this exercise, you will use Azure Data Studio to connect to the _MyStore_ database and run a simple query.

**Estimated Time: 20 minutes**
**Lab files: D:\Lab Code\SQL Server Tools\script1.sql**

# Lab Overview

Students will explore the lab environment, connect to the lab virtual machine and connect to a SQL Server using Azure Data Studio.


# Exercise 1: Connect to the lab environment

When the VM lab environment opens, select the  **Ctrl+Alt+Delete** button in the **Resources** tab to open the login screen. 
Select the password on the **Resources** tab for the **Administrator** account to populate the password field, and then select the arrow to sign in to Windows.

# Exercise 2: Execute a query 

You will now use Azure Data Studio to connect to a SQL Server and run a query.

## Task 1: Open Azure Data Studio

1.There is an icon in the toolbar to open Azure Data Studio. 

![Picture 1](../images/Module1-Unit6-picture1.png)

Select the icon for Azure Data Studio. The tool will open to a Welcome screen. If you get a message in the lower right corner asking if you want to enable **Preview features**, you can select either option. 

2. From the **File** menu, select **New Query**. You should now see a blank query window. 

## Task 2: Execute a query

1. You are going to run the following query. You can try typing it in directly or you can select File/Open File, and navigate to D:\Lab Code\SQL Server Tools. Double-click on the file script1.sql and it will be loaded into a new query window.

```tsql
USE MyStore;

SELECT custid AS CustomerID, YEAR(orderdate) AS OrderYear

FROM Sales.Orders

WHERE freight > 500

GROUP BY custid, YEAR(orderdate) 

HAVING COUNT(*) > 1

ORDER BY CustomerID, OrderYear;
```

2. Select the Run button next to the green arrow in the upper left corner.  

![Picture 2](../images/Module1-Unit6-picture2.png)

3. You will be prompted to connect to your SQL Server. Enter a single dot for the Server, which indicates your default local SQL Server. Because the Authentication type is Windows Authentication, the tool will use your login credentials from Windows and you don't need to enter anything for User name and Password. 

4. Select **Connect**. 

![Picture 3](../images/Module1-Unit6-picture3.png)

You should see three rows returned in the Results Window. 

5. Notice that just above the results, to the right of the word **Results**, there is a **Messages** tab. You can select that table to see special messages, including the row count. If there are any error messages, they will appear in the **Messages** tab. 

6. Now use your mouse to lightlight just the first four lines of the SELECT statement:

```tsql
USE MyStore;

SELECT custid AS CustomerID, YEAR(orderdate) AS OrderYear

FROM Sales.Orders

WHERE freight > 500

GROUP BY custid, YEAR(orderdate) 
```

7. Select the Run button. You should now see 10 rows returned because we are not filtering with the HAVING clause. 

Notice that the first line of the script specifies the database to access with the USE command. As an alternative to USE, you can select the dropdown box above the query, and see all the databases within the local SQL Server. 

![Picture 4](../images/Module1-Unit6-picture4.png)

We will only be using the _MyStore_ database. 

To finish this exercise select **Done** below.

