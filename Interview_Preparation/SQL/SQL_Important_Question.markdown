# Important Questions From Basics
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

## What are Indexes ? Why Use It ? How To create ?
Ans : Index ek special data structure hota hai SQL databases mein jo ki table ke column ke upar banaya jata hai - Jisse data fast retrieve kiya ja sake , without scanning the entire table.

Simple Words: Index ek kitaab ke index jaise hota hai – jaise kitaab ke last mein diya hota hai kis page par kya topic hai, waise hi SQL Index batata hai ki kisi value ko kahaan se access karna hai bina pura table padhe.

- Why Use Indexes ?
 1. Fast Search : Index hone se data jaldi milta hai, specially jab large table ho (1 lakh+ rows).
 2. Better PErformace : Jo queries slow chal rahi ho, unhe optimize karne ke liye indexes helpful hote hain.
 3. Efficient Sorting : ORDER BY, GROUP BY, JOIN jaisi queries mein performance boost hota hai.

-> Disadvantages "
 1. INSERT/UPDATE/DELETE thoda slow ho jata hai kyunki index bhi update karna padta hai.
 2. Index banane se storage use hoti hai.

-> How To Create a Index in SQL (Kaise Banaye Index)
 Syntax : CREATE INDEX index_name ON table_name (column_name);

 - Example 1 : Simple Index 

 CREATE INDEX idx_customer_name
 ON Customers (CustomerName);

 Iska matlab: Jab bhi aap query likhoge:

 SELECT * FROM Customers WHERE CustomerName = 'Amit';

 To SQL engine directly CUstomerName column ka index check karega aur fast result dega.

 - Example 2 :  Composite Index(Multiple Columns)

 CREATE INDEX idx_order_customer_date
 ON Orders (CustomerID, OrderDate);

 SELECT * FROM Orders 
 WHERE CustomerID = 101 AND OrderDate = '2025-07-03';

 To ye index dono columns ke liye use hoga

-> Real World Example :
 Scenario : E- Commerce App
 Table : Products
 Columns :  ProductID, ProductName, Category, Price, StockQuantity
 
 Problem without Index: 
 SELECT * FROM Products WHERE ProductName = 'Samsung TV';
 Agar 1 million products hain, to poora table scan hoga → slow query.
 
 Solution with Index:
 CREATE INDEX idx_product_name
 ON Products (ProductName);
 Ab query directly index se match karega → fast result (~10x faster).

-> Types Of Indexes 
 1. Clustered Index : Data table ke rows ko sort karke store karta hai (ek hi ho sakta hai).
 2. Non-Clustered Index : Separate structure hota hai, jisme pointers hote hain actual data rows ke liye.
 3. Unique Index : 	Duplicate values allow nahi karta (jaise Aadhaar Number).
 4. Composite Index : Multiple columns ka ek saath index banata hai.

->  Best Use Case
 1. WHERE clause mein jo columns frequently use hote hain unpe index lagao.
 2. SELECT * avoid karo — sirf required columns lo.
 3. Har column par index mat lagao — INSERT/UPDATE slow ho jata hai.
 4. Use SQL Server Profiler ya Execution Plan to check indexes ka impact.

## Why Use No Lock?
Ans : WITH (NOLOCK) SQL Server ka ek query hint hai jo batata hai ki query ko shared locks acquire nahi karne hain aur locked data ko bhi read rarna allowed hai.

-> What Does NOLOCK Do?
* Normally jab app query run karte ho, SQL Server locks lagata hai (read lock , write lock) jisse data consisten rahe.
* Agar Dusra transaction Chal raha ho (E.G. UPDATE) , to aapki SELECT query ruk jaati hai lock release hone tak.
* No LOCK hint lagana se 
  - SQL Server lock ko ignore karta hai
  - Dirty data bhi read ho skta hai.
  - Query Zayada fast ho jaati hai , especially large tables ke saath.

-> Risk With NOLOCK
  1. Dirty Reads : Jo data abhi update ho raha hai, usi moment read kar loge — data inaccurate ho sakta hai.
  2. Phantom Reads : Same query baar-baar chalane par alag-alag result aa sakta hai.
  3. Missing/Extra Rows : Table scan karte waqt rows add/delete ho rahe ho to result inconsistent ho sakta hai.

## How To Check For Row/Columns with Null Values ? Why is it important ? Should we have Null values or not ? 
Ans : 
1. How to Check Rows/Columns with NULL values?

→ Row mein NULL check karna (Column-wise)
SELECT * FROM Employees WHERE Email IS NULL;
Yeh query aapko woh rows degi jahan Email column empty (NULL) hai.

→ Multiple Columns mein NULL check karna
SELECT * FROM Employees WHERE Email IS NULL OR Phone IS NULL;
Dono column mein se koi bhi NULL ho, woh row return karega.

→ NULL Count nikalna Column-wise
SELECT
  COUNT(*) AS TotalRows,
  COUNT(Email) AS EmailFilled,
  COUNT(*) - COUNT(Email) AS EmailNulls,
  COUNT(Phone) AS PhoneFilled,
  COUNT(*) - COUNT(Phone) AS PhoneNulls
FROM Employees;

2. Why is it Important to Check NULLs?
-> Jab NULL hota hai, iska matlab hai value hi nahi hai – matlab unknown, missing, ya applicable nahi hai.
-> Agar aap calculation karte ho (SUM, AVG), ya condition check karte ho (WHERE Salary > 50000), toh NULL ka galat effect pad sakta hai.
-> NULL ke sath comparison (=, >, <) directly kaam nahi karta — aapko IS NULL ya IS NOT NULL lagana padta hai.

3. Should We Have NULLs or Not?
-> NULL hona kabhi-kabhi sahi hota hai, jaise:
MiddleName – sabka nahi hota
ManagerID – top-level employees ka manager nahi hota

-> Lekin bahut zyada NULLs hona dikkat de sakta hai:
Reporting mein confusion
Aggregations galat
JOINs fail ho sakte hai

4. Best Practices:
NULL tabhi use karo jab value genuinely missing ho.
Defaults set karo (DEFAULT '' or 0) agar possible ho.
Reporting & Logic likhte waqt hamesha IS NULL check zarur rakho.

## How To Find NULL Count in a column?
Ans : 
SELECT
  COUNT(*) AS TotalRows,
  COUNT(Email) AS EmailFilled,
  COUNT(*) - COUNT(Email) AS EmailNulls,
  COUNT(Phone) AS PhoneFilled,
  COUNT(*) - COUNT(Phone) AS PhoneNulls
FROM Employees;

Note : Count(column) don't not Consider Null.
       If 5 row with 2 null data 
       Count will come out as 3.
       Total Count - Count = Total null count.

## How To Handle Aggreagate Function with NULL records ?
Ans : Default Behavior of Aggregate Functions with NULLs
Srno Function                NULL ka Default Treatment
1    SUM(column)             NULL ko Ignore karta hai
2    AVG(column)             NULL ko ignore kata hai(sirf non null ka average)
3    COUNT(column)           NULL values count nahi karta 
4    COUNT(*)                Saari rows count karta hai(null ho ya na ho)
5    MAX(column)             NULL ignore

## What is ISNULL / COALESCE ?
Ans : SQL mein jab kisi column ya expression ki value NULL ho , aur aap chahte ho ki uski jagha koi default use ho -- tab ISNULL() aur COALESCE() ka use hota hai.

-> ISNULL() - Simple NULL Handler
  Syntax : ISNULL(expression, replacement_value)
  Agar expression NULL hai, to replacement_value return hoti hai , Nahin to expression ki actual value return hti hai.

  SELECT ISNULL(NULL, 0);  -- Output: 0
  SELECT ISNULL(100, 0);   -- Output: 100

-> COALESCE() - Multi- Value NULL Handler
  Syntax : COALESCE(value1 , value2 , value3, ....)

  SELECT COALESCE(NULL, NULL, 300, NULL); -- Output: 300

  USE Case : Fall Bakc Values
  SELECT 
  COALESCE(MobileNumber, AlternateMobile, 'No Number') AS ContactNumber
  FROM Customers;

  Ye query MobileNumber agar NULL ho, to AlternateMobile le legi, warna "No Number".


## Difference in Having and Where ?
Ans : 
Feature         WHERE                   HAVING
- Use           Row - Level Filtering   Group Level Filtering
- Applies       Before Aggregation      After Aggregation
- Aggregate Fn  Not Allowed             Allowed.

| TransactionID | CustomerName | City   | Amount | Status  |
| ------------- | ------------ | ------ | ------ | ------- |
| 1             | Amit         | Mumbai | 1500   | Done    |
| 2             | Rahul        | Delhi  | 700    | Pending |
| 3             | Amit         | Mumbai | 3500   | Done    |
| 4             | Riya         | Mumbai | 1000   | Done    |
| 5             | Rahul        | Delhi  | 3000   | Done    |
| 6             | Amit         | Mumbai | NULL   | Done    |

1. Filter All Orders Above ₹1000 — Use WHERE
  SELECT * FROM SalesTransactions
  WHERE Amount > 1000;
  👉 Filters rows directly.

2. Total Sales by Customer — Use GROUP BY
  SELECT CustomerName, SUM(Amount) AS TotalSale
  FROM SalesTransactions
  GROUP BY CustomerName;

3.  Only Those Customers Whose Total Sale > ₹4000 — Use HAVING
  SELECT CustomerName, SUM(Amount) AS TotalSale
  FROM SalesTransactions  
  GROUP BY CustomerName
  HAVING SUM(Amount) > 4000;

4. Combine WHERE + HAVING
  Q Find customers from 'Mumbai' whose total completed (Status = 'Done') sales are more than ₹4000.

  SELECT CustomerName, SUM(ISNULL(Amount, 0)) AS TotalSale
  FROM SalesTransactions
  WHERE City = 'Mumbai' AND Status = 'Done'
  GROUP BY CustomerName
  HAVING SUM(ISNULL(Amount, 0)) > 4000;


## What is CTE ?
Ans : CTE (Common Table Expression) Ek Temporary result set hota hai jo aapki main SQL query ke upar define kiya jata hai - Jise app reuse , nest , aur recursive query ke liya use kar sakte ho.

It is defined using the WITH keyword and behhaves like a temporary name result set (jaise ek virtual table) , jo sirf us query ke duration ke liya valid hota hai.

-> Basic Syntax : 
 WITH CTE_Name AS (
    SELECT column1, column2
    FROM TableName
    WHERE condition
)
SELECT * FROM CTE_Name;

-> Why USe CTE ?
  1. Readable Queries    Complex nested subqeries ko simple banata hai
  2. Reusable Logic      EK hi logic baar baar likhne ki zarurat nahi
  3. joins aur Aggregations mein clarity

-> Real World Example 
  1. Find Customers Whose Total Sale > 2000
  -- Step 1: Make a CTE to calculate total sale per customer
    WITH SalesCTE AS (
    SELECT CustomerName, SUM(Amount) AS TotalAmount
    FROM Sales
    GROUP BY CustomerName
  )

  -- Step 2: Use CTE in main query
  SELECT * 
  FROM SalesCTE
  WHERE TotalAmount > 2000;

## Difference in UNION and UNION ALL?
Ans : 
| Feature             | `UNION`                              | `UNION ALL`                                    |
| -----------------   | ------------------------------------ | ---------------------------------------------- |
| 🔁 Duplicate Rows  | Removes duplicates (DISTINCT)        | Keeps all duplicates                           |
| ⚡ Performance     | Slower (needs sort & compare)        | Faster                                         |
| ✅ Use Case        | When you need unique combined result | When you want all records including duplicates |

// Removes Duplicates
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers;

// Duplicates Not Removed
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers;


## Difference in Intersection and EXCEPT?
Ans : 
| Feature           | `INTERSECT`                      | `EXCEPT`                            |
| ----------------- | -------------------------------- | ----------------------------------- |
| 📌 Output         | Common rows between both queries | Rows from first query not in second |
| 🔄 Duplicate Rows | Removed by default               | Removed by default                  |
| ✅ Use Case        | Find common data                 | Find mismatches                     |


## Does Column Sructure between two table to to be same to perform UNION ,UNION ALL , INTERSECTION ,EXCEPT , MERGE? 
Ans : YES (Structure Compatibility Required)

## What is the use MERGE ?
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

## Diffference In ROW_NUMBER() , RANK() , DENSE_RANK()
Ans :

## Difference in LEAD() and LAG()
Ans : 

## Scalar and Table Valued Functions
Ans : 

## Error Handling in Stored Prodecure
Ans :

## ACID Properties
Ans :

## BEGIN TRAN , COMMIT , ROLLBACK
Ans :

## Performace Optimization and Indexing
Ans : 

## Purpose OF Triggers in SQL
Ans : 