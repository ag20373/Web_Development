# SQL Basics : Getting Started 
## What is SQL ? Why SQL Server ?
Ans : SQL (Structured Query Language) is used to store, retrieve, and manage data in relational databases.
SQL Server is a powerful, secure, and scalable RDBMS developed by Microsoft, widely used in enterprise environments.

## Installing  SQL Server And SSMS
Ans : SQL Server: Install from Microsoft’s official site by downloading the installer (e.g., Developer Edition).
SSMS (SQL Server Management Studio): A GUI tool to manage SQL Server easily—download separately from Microsoft and install.

## Data Types is SQL Server
Ans : Types Are :
Common SQL Server data types include:
-> INT, BIGINT, DECIMAL – for numbers
-> VARCHAR, NVARCHAR, CHAR – for text
-> DATE, DATETIME, TIME – for date and time
-> BIT – for Boolean (true/false)
-> FLOAT, REAL – for approximate numbers

## SQL Commnads : DDL , DML , DCL , TCL , DQL
Ans : Commands are :
-> DDL (Data Definition Language): Defines structure
    CREATE, ALTER, DROP

-> DML (Data Manipulation Language): Modifies data
    INSERT, UPDATE, DELETE

-> DCL (Data Control Language): Manages access
    GRANT, REVOKE

-> TCL (Transaction Control Language): Controls transactions
    COMMIT, ROLLBACK, SAVEPOINT

-> DQL (Data Query Language): Queries data
    SELECT

# SQL SELECT And Data Retrieval
## SELECT statement basics
Ans : The SELECT statement is used to fetch data from a database.

→ SELECT * FROM Employees; 
This fetches all the Column and Rows PResent in Employees.

## Selecting Specific Coulmns.
Ans : Instead of fetching all columns, you can choose only the required ones.

→ SELECT FirstName, LastName FROM Employees;
Fetches only FirstName and LastName from Employees.

## Using BETWEEN , IN , LIKE , NULL conditions
Ans : 
→ BETWEEN : Used to filter rows within a range (inclusive).
SELECT * FROM Employees WHERE Salary BETWEEN 30000 AND 50000;

→ IN : Used to filter rows matching any of the values in a list.
SELECT * FROM Employees WHERE Department IN ('HR', 'IT', 'Sales');

→ LIKE : Used for pattern matching in strings.
SELECT * FROM Employees WHERE FirstName LIKE 'A%';   -- starts with A
SELECT * FROM Employees WHERE LastName LIKE '%son'; -- ends with son
SELECT * FROM Employees WHERE FirstName LIKE '_a%'; -- second letter a

## Sorting results with ORDER BY
Ans : ORDER BY is used to sort the result set by one or more columns.

→ SELECT * FROM Employees ORDER BY Salary ASC;  -- Ascending (default)
→ SELECT * FROM Employees ORDER BY HireDate DESC; -- Descending
→ SELECT * FROM Employees ORDER BY Department, Salary DESC; -- Multi-level sorting

## Limiting results with TOP
Ans : TOP is used to limit the number of rows returned (used in SQL Server).
→ SELECT TOP 5 * FROM Employees;
Returns only the first 5 rows of the Employees table.

→ SELECT TOP 3 * FROM Employees ORDER BY Salary DESC;
Returns top 3 highest paid employees.

## How can we Optimized SELECT Query ?
Ans : Following 
1. Select Only Required Columns
SELECT FirstName, LastName FROM Employees; -- ✅ Good  
SELECT * FROM Employees;                   -- ❌ Avoid

2. Use WHERE to Filter Early - Avoid pulling unnecessary rows:
SELECT * FROM Orders WHERE OrderDate >= '2024-01-01';

3. Use Indexes on Filter/Search Columns
Indexes improve speed on WHERE, JOIN, ORDER BY columns.
-- Example: If you often filter by DepartmentID, index it
CREATE INDEX idx_department ON Employees(DepartmentID);

4. Avoid Functions on Indexed Columns
-- ❌ Slower
SELECT * FROM Employees WHERE YEAR(HireDate) = 2024;
-- ✅ Better
SELECT * FROM Employees WHERE HireDate BETWEEN '2024-01-01' AND '2024-12-31';

5. Use LIMIT / TOP if Needed
SELECT TOP 10 * FROM Products ORDER BY Price DESC;

6. Use No-Lock Always

## What Need to be taken care when using SELECT Query?
Ans : 
1. Avoid SELECT : Pulls all data, impacts performance & network.
SELECT EmpID, EmpName FROM Employees; -- ✅ Better

2. Check for NULLs : Use IS NULL / IS NOT NULL correctly.
SELECT * FROM Users WHERE Email IS NULL;

3. Use Proper WHERE Clause : Missing WHERE can result in huge datasets.
4. Mind Case Sensitivity (depends on DB collation)
5. Data Type Mismatch

# SQL Aggregation and Grouping Data
## Aggregate Function SUM() , AVG() , COUNT() , MIN() ,MAX()
Ans : These functions are used to perform calculations on columns across multiple rows.
Function	        Purpose	                    Example
SUM()	            Total of numeric column	    SELECT SUM(Salary) FROM Employees;
AVG()	            Average of numeric column	SELECT AVG(Salary) FROM Employees;
COUNT()	            Count of rows (non-null)	SELECT COUNT(Salary) FROM Employees;
MIN()	            Minimum value	            SELECT MIN(Salary) FROM Employees;
MAX()	            Maximum value	            SELECT MAX(Salary) FROM Employees;

Note: These functions ignore NULL values (except COUNT(*)).

## Grouping result with GROUP BY
Ans : GROUP BY is used to group rows that have the same values in one or more columns.

**SELECT Department, COUNT(*) AS TotalEmployees
FROM Employees
GROUP BY Department;**

This groups all employees department-wise and counts how many are in each.

## Filtering Group by Having
Ans : HAVING filters results after GROUP BY, especially on aggregate results.

**SELECT Department, AVG(Salary) AS AvgSalary
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 50000;**

This will only show departments where average salary is more than ₹50,000.

## Difference Between WHERE and HAVING
Ans : 
Feature	        WHERE	                        HAVING
Use	            Filters rows before grouping	Filters groups after grouping
Used with	    Regular columns	                Aggregate functions (SUM, COUNT, etc.)
Works on	    Row-level filtering	            Group-level filtering
Example	        WHERE Salary > 30000	        HAVING AVG(Salary) > 50000

# SQL Joins And Relationships
## INNER JOIN , LEFT JOIN , Right Join , Full Outer oin, Cross Join
Ans : Let’s assume two tables :
-- Table: Employees
EmpID | Name   | DeptID
------------------------
1     | Amit   | 10
2     | Neha   | 20
3     | Ravi   | NULL
4     | Sonal  | 30

-- Table: Departments
DeptID | DeptName
--------------------
10     | HR
20     | IT
40     | Finance

1. Inner Join : Only Matching rows from both tables

SELECT * FFROM Employees E
INNER JOIN Departments D ON E.DeptID = D.DeptID;

Result :  Amit, Neha (Ravi is skipped because DeptID is NULL, Sonal is skipped because 30 doesn’t exist in Departments)

2. Left Join : All from left table (Employees), even if no match

SELECT * FROM Employees E
LEFT JOIN Departments D ON E.DeptID = D.DeptID;

Result : Amit, Neha (matched) + Ravi & Sonal (NULLs from Departments)

3. Right Join - All from right table (Departments)

SELECT * FROM Employees E
RIGHT JOIN Departments D ON E.DeptID = D.DeptID;

Result : Amit, Neha (matched) + DeptID 40 from Departments (no employee – so NULLs from Employees)

4. Full Outer Join - All Rows from both Sides

SELECT * FROM Employees E
FULL OUTER JOIN Departments D ON E.DeptID = D.DeptID;

Combines results of LEFT + RIGHT joins

5. CROSS JOIN – All possible combinations (Cartesian Product)

SELECT * FROM Employees E
CROSS JOIN Departments D;

4 Employees × 3 Departments = 12 rows
(Used rarely and carefully)

## Self Join , Non - Equal Joins ?
Ans : 
1. Self Join – Table joins to itself

-- Manager-Employee hierarchy
SELECT E1.Name AS Employee, E2.Name AS Manager
FROM Employees E1
LEFT JOIN Employees E2 ON E1.ManagerID = E2.EmpID;

Use case: Show each employee with their manager name

1. Non-Equal Join – Join using operators other than =

-- Example: Find Employees in departments with higher ID
SELECT * FROM Employees E
JOIN Departments D ON E.DeptID > D.DeptID;

Not common, but possible when using ranges or custom conditions

## Primary and Foreign Key ?
Ans : 
Primary Key	Uniquely identifies each record in a table. Cannot be NULL.
Foreign Key	A column that references the Primary Key of another table.

-- Department Table
CREATE TABLE Departments (
    DeptID INT PRIMARY KEY,
    DeptName VARCHAR(50)
);

-- Employees Table
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50),
    DeptID INT,
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);

## Entity RelationShip Diagram ?
Ans :  ERD is avisual representation of tables and their resltionships in a database.

1. Entities =  Table(like Employees , Departments)
2. Attributes = Columns (like EmpID , DeptID)
3. Realtionships = Arrows connecting Primary Key - Foreign Key.

-> Common ERD Symbols:
Symbol 	    Meaning
🔷	        Entity (Table)
🔑	        Primary Key
🗝️	         Foreign Key
→	         Relationship (1:1, 1:M, M:N)

-> Example Relationship:

[Departments] 🔑DeptID 1 ⟶ ∞ DeptID [Employees]
➡ One department can have many employees (1-to-many)

-> Let me know if you want :
Diagram image of the ERD
ERD generation tool suggestion
Or live queries to test joins on dummy tables

# SQL SubQueries and Advance Queries 
## Subquieries inside SELECT, FROM , WHERE
Ans : A subquery is a query inside another query , used to compute values dynamically.

1. Subquery in SELECT (used for Scalar Value)
SELECT Name,
  (SELECT AVG(Salary) FROM Employees) AS AvgSalary
FROM Employees;
Every row will show average salary next to each employee.

2. Subquery in FROM (inline/derived table)
SELECT DeptID, AvgSalary
FROM (
    SELECT DeptID, AVG(Salary) AS AvgSalary
    FROM Employees
    GROUP BY DeptID
) AS DeptAvg;
You can treat a subquery as a temporary table.

3. Subquery in WHERE (most common)
SELECT Name, Salary
FROM Employees
WHERE Salary > (SELECT AVG(Salary) FROM Employees);
Returns only employees who earn more than average.

## Correlated Subquries
Ans : A correlated subquery uses a value from the outer query . It runs once for each row of the Outer query.

SELECT E1.Name , E1. Salary FROm Employees E1 WHERE E1. Salary > (SELECT AVG(Salary) FROM Employees E2 WHERE Employees E2 WHERE E2.DeptID = E1.DeptID);

This compares each employee's salary with the average salary of their own department.

Note : Correlated subqueries are powerful But can be sloe - use them wisely

## Common Table Expressions (CTEs)
Ans : A CTE is a Temporary Result set defined with a WITh clause - makes complex queries readible.

WITH DeptWiseAvg AS (
    SELECT DeptID, AVG(Salary) AS AvgSalary
    FROM Employees
    GROUP BY DeptID
)
SELECT E.Name, E.Salary, D.AvgSalary
FROM Employees E
JOIN DeptWiseAvg D ON E.DeptID = D.DeptID;

Used like a named subquery, especially good for reusability and chaining.

## Recursive CTEs
Ans : Used to query hierarchical/parent-child data (like Org Chart, Tree structure).

WITH EmployeeCTE AS (
    SELECT EmpID, Name, ManagerID, 0 AS Level
    FROM Employees
    WHERE ManagerID IS NULL   -- Top-level boss

    UNION ALL

    SELECT E.EmpID, E.Name, E.ManagerID, C.Level + 1
    FROM Employees E
    JOIN EmployeeCTE C ON E.ManagerID = C.EmpID
)
SELECT * FROM EmployeeCTE;

This will list all employees along with their level in hierarchy (e.g., CEO → Manager → Team Lead → Developer)

# SET Operators in SQL Server
## UNION vs UNION ALL
Ans : 
1. UNION : Removes Duplicates , Slower PErformace bcoz of Sorting , Unique Result 

SELECT City FROM Customers
UNION
SELECT City FROM Suppliers;

Returns unique list of cities from both tables.

2. UNION ALL : Dont Remove Duplicates , Faster , When you wan tall results , inculding duplicates

SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers;

Returns all cities including duplicates.

## INTERSECT VS EXCEPT 
Ans : 
1. INTERSECTION : Returns rows common in both queries

-- Common cities between both tables
SELECT City FROM Customers
INTERSECT
SELECT City FROM Suppliers;

2. EXCEPT : Returns rows from first query that are not in second

-- Cities that are in Customers but not in Suppliers
SELECT City FROM Customers
EXCEPT
SELECT City FROM Suppliers;

All columns used in both queries must match in number and data type.

## Merging Data with MERGE
Ans : MERGE is used to insert , Update or delete rows based on matching conditions - very usefull for syncing tables. 

-> Query
MERGE TragetTable AS T
USING SourceTable AS S
ON T.ID = S.ID

WHEN MATHCED THEN 
    UPDATE SET T.Name = S.Name

WHEN NOT MATCHED BY TARGET THEN
    INSERT (ID, Name) VALUES (S.ID, S.Name)

WHEN NOT MATCHED BY SOURCE THEN
    DELETE;

-> Use Case Example:
    1. TargetTable → current records
    2. SourceTable → updated records from another system

You can update if match , insert if new , or delete if missing -- all in one MERGE.

# WINDOW Functions (Analytical Functions)
## Diffference In ROW_NUMBER() , RANK() , DENSE_RANK()?
Ans :  
1. ROW_NUMBER() : Gives unique row numbers to each row - It does nt handle Duplicates values (Always Unque ,even for duplicates)
2. RANK() : Gives Same rank to ties , but skips next number .Handle Duplicates but leave gaps
3. DENSE_RANK() : Gives same rank to ties, no gap - Handle duplicates but no gap

Sample Employees Table
EmpID	Name	Department	Salary
1	    Amit	HR	        50000
2	    Neha	IT	        70000
3	    Ravi	HR	        60000
4	    Kiran	IT	        70000
5	    Sonal	HR	        50000

Query : 
SELECT Name, Salary,
  ROW_NUMBER() OVER (ORDER BY Salary DESC) AS RowNum, 
  RANK()       OVER (ORDER BY Salary DESC) AS RankNum,
  DENSE_RANK() OVER (ORDER BY Salary DESC) AS DenseRank
FROM Employees;

Name	Salary	RowNum	RankNum	DenseRank
Neha	70000	1	    1	    1
Kiran	70000	2	    1	    1
Ravi	60000	3	    3	    2
Amit	50000	4	    4	    3
Sonal	50000	5	    4	    3

Explanation:
ROW_NUMBER() → unique number to each row
RANK() → same rank for ties but skips next
DENSE_RANK() → same rank for ties but no skipping

## LEAD() and LAG()
Ans : 
Used For Look Ahead(LEAD) or Look Behind(LAG) in data.

Query : 
SELECT Name, Salary,
  LAG(Salary)  OVER (ORDER BY Salary) AS PrevSalary,
  LEAD(Salary) OVER (ORDER BY Salary) AS NextSalary
FROM Employees;

Name	Salary	PrevSalary	NextSalary
Neha	70000	NULL	    70000
Kiran	70000	70000	    60000
Ravi	60000	70000	    50000
Amit	50000	60000	    50000
Sonal	50000	50000	    NULL

Shows:
Current row’s salary
Previous row’s salary
Next row’s salary

## Partitioning data using PARTITION BY
Ans : PARTITION BY devides data into groups for window functions.

Query : 
SELECT Name, Department, Salary,
  RANK() OVER (PARTITION BY Department ORDER BY Salary DESC) AS DeptRank
FROM Employees;

-> RANK is calculated within each department, not for whole table.
It's like GROUP BY + analytics combined.

| Name  | Dept | Salary | DeptRank |
| ----- | ---- | ------ | -------- |
| Ravi  | HR   | 60000  | 1        |
| Amit  | HR   | 50000  | 2        |
| Sonal | HR   | 50000  | 2        |
| Neha  | IT   | 70000  | 1        |
| Kiran | IT   | 70000  | 1        |
-> HR as Department has two salary 6000 - Rank 1 and 5000 - Rank 2
-> IT as Departmetn has one Salary 7000 - Rank 1.

## Running Totals and Moving Averages
Ans :
1. Running Totals

Query :
SELECT Name, Salary,
  SUM(Salary) OVER (ORDER BY EmpID) AS RunningTotal
FROM Employees;

| Name  | Salary | RunningTotal |
| ----- | ------ | ------------ |
| Amit  | 50000  | 50000        |
| Neha  | 70000  | 120000       |
| Ravi  | 60000  | 180000       |
| Kiran | 70000  | 250000       |
| Sonal | 50000  | 300000       |

-> Table Values are Getting Sum in each Row Shown in Running Rows

2. Moving Averages (3-row Window)

Query : 
SELECT Name, Salary,
  AVG(Salary) OVER (
    ORDER BY EmpID
    ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
  ) AS MovingAvg
FROM Employees;

| Name  | Salary | MovingAvg |
| ----- | ------ | --------- |
| Amit  | 50000  | 50000.00  |
| Neha  | 70000  | 60000.00  |
| Ravi  | 60000  | 60000.00  |
| Kiran | 70000  | 66666.66  |
| Sonal | 50000  | 60000.00  |

Calculates average of current + 2 previous rows

# Stored Procedures and Functions
## Creating Stored Prodedure and
Ans :  A Stored Procedure is a saved SQL block that you can reuse anytime.

-> Syntax
CREATE PROCEDURE GetAllEmployees
AS
BEGIN
    SELECT * FROM Employees;
END;

-> Execution
EXEC GetAllEmployees;

## Using Parameter in Stored PRoceduure
Ans : 
-> Syntax
CREATE PROCEDURE GetEmployeesByDept
    @DeptName VARCHAR(50)
AS
BEGIN
    SELECT * FROM Employees
    WHERE Department = @DeptName;
END;

-> EXEC GetEmployeesByDept @DeptName = 'HR';

## Scalar and Table Valued Functions
Ans : 
-> Scalar Valued Function - Return single value
CREATE FUNCTION GetEmployeeCount()
RETURNS INT
AS
BEGIN
    DECLARE @Count INT;
    SELECT @Count = COUNT(*) FROM Employees;
    RETURN @Count;
END;

SELECT dbo.GetEmployeeCount() AS TotalEmployees;

->  Table-Valued Function – returns entire table
CREATE FUNCTION GetHighSalaryEmployees(@MinSalary INT)
RETURNS TABLE
AS
RETURN (
    SELECT * FROM Employees WHERE Salary > @MinSalary
);

SELECT * FROM dbo.GetHighSalaryEmployees(60000);

## Error Handling in Stored Prodecure
Ans : Use TRY...CATCH block to handle errors like divide-by-zero, constraint violation, etc.

# Transactions & Error Handling
## ACID Properties
Ans : 
A - Atomicity - ya to saari queries chalengi , ya koi bhi nahi -- all or nothing
C - Consistency - Data hammesha valid state mein rehna chiya
I - Isolation - Ek Transaction durse se interfere na kare
D - Durability - Data Permentant ho jata hai after commit.

Example : Bank Transfer- Withdraw from A + Deposit to B - both should succeed together , warna rollback.

## BEGIN TRAN , COMMIT , ROLLBACK
Ans : These are used to control Transaction

-> Query
BEGIN TRAN;

UPDATE Accounts SET Balance = Balance - 5000 WHERE AccountID = 1;  -- Debit
UPDATE Accounts SET Balance = Balance + 5000 WHERE AccountID = 2;  -- Credit

-- If no error:
COMMIT;
-- If error occurs:
-- ROLLBACK;

-> Explanation
- BEGIN TRAN se transaction start hota hai.

- COMMIT karte hi data permanent ho jata hai.

- Agar koi error aaye to ROLLBACK se pura transaction cancel ho jata hai.

## Handling Deadlock
Ans : Deadlock tab hota hai jab 2 queries ek dusre ka resource hold karke wait kar rahi hoti hain — and system auto-kills one.

Tips to Avoid Deadlocks:

1. Always access tables in same order across all queries.
2. Keep transactions short and fast.
3. Use TRY...CATCH block to retry if deadlock happens.

## Using WITH(NOLOCK) For Performace
Ans : SELECT * FROM Orders WITH (NOLOCK);
-> With (NOLOCK) ka atlab hota hai 
1. ye query lock acquire nahi karegi
2. Dusri queries ko block nahi karegi
3. Data dirty ya uncommitted ho sakta hai (i.e. bot 100% accurate)

-> Use Case :
Large reporting queries jahan read performance chahiya auur thoda inconsistent data chalta hai.

-> Don't use for :
Bank Balance , critical financial transactions - Kyunki data stable ya incorrent ho sakta hai.

# Performace Optimization And Indexing
| ProductID | ProductName       | Category | Price  | Stock | CreatedDate |
| --------- | ----------------- | -------- | ------ | ----- | ----------- |
| 1         | iPhone 14 Pro Max | Mobiles  | 130000 | 25    | 2023-12-01  |
| 2         | Samsung M14       | Mobiles  | 15000  | 120   | 2024-01-10  |
| 3         | HP Laptop         | Laptops  | 60000  | 10    | 2024-02-05  |
| ...       | ...               | ...      | ...    | ...   | ...         |

## Clustered Vs. No-Clustered Indexes
Ans : 
1. Clustered Index
By default, ProductID pe Clustered Index hota hai — isme data physically sorted hota hai.

Query : 
-> CREATE CLUSTERED INDEX IX_ProductID ON Products(ProductID);
Jab aap query likhte ho:
-> SELECT * FROM Products WHERE ProductID = 5;
Ye fast hoga kyunki clustered index se direct data milega.

Points :
-> Actual Data is sorted in index
-> Only One Clustered Index is Allowed
-> Faster for range Queries, sorting
-> Example Column : Primary Key

2. Non - Clustered Index 
Agar user search karta hai by ProductName or Category, toh performance slow ho sakti hai agar index nahi hai.

Query : 
-> CREATE NONCLUSTERED INDEX IX_ProductName ON Products(ProductName);
Ab ye query bhi fast chalegi:
SELECT * FROM Products WHERE ProductName LIKE 'iPhone%';

Points: 
-> Separate structure contains pointers to data
-> Multiple Non Clustered index Allowed
-> Faster for specific column lookups
-> Name, Email , City etc.

## Query Optimization Techiques
Ans : 
1. Avoid SELECT *  -> Select REquired Columns.
2. Use WHERE clause effectively -> REducses Rows Scanned
3. USe JOINs properly ->  Use Inner Join When applicable
4. Use Indexes ->  On frequently searched or filtered column.
5. Use EXISTS insted of IN ->  Subqueires with Large Data
6. Use WITH (NOLOCK) for reads -> 	In non-critical reports (fast, but risky)
7. Avoid Functions in WHERE Clause
8. Use TOP , LIMIT , OFFSET ->  To imit rows returned

## Execution Plans and Index Tuning
Ans : 
1. Execution Plan :
-> Shows how SQL Serer executes your query
-> Helps identify slow operations , missing indexes table scans

How to view :
-- In SSMS : Press CTRL + M
-- Or click on "Display Estimated Execution Plan"

Checks For : 
1.  "Table Scan" or "Clustered Index Scan" → 🔴
2. "Index Seek" → ✅ (faster)
3. "Key Lookup" → May need Include Columns or Covering Index

2. Index Tuning : 
Use Database Engine Tuning Advisor or manually analyze : 
SELECT * FROM sys.dm_db_missing_index_details;
Suggests missing indexes based on query patterns.

## SQL Profiler and Performace Monitoring
Ans :
1.  SQL Profiler 
-> Tool to monitor real time query activity
-> Detects : long - running queires , locks , deadlocks, slow procedures.
-> Use it to 
    - Track which query is taking more time
    - Identify who/what is causing load

2. Other Monitoring Tools
a. Activity Monitor	- Real-time stats on CPU, queries
b. Extended Events - Lightweight alternative to Profiler
c. Dynamic Management Views (DMVs) - Get internal performance stats

# 