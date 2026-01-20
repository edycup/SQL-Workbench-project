# 📊 SQL Portfolio: Data Analysis & Database Management

## 👤 About the project
This repository documents my journey in mastering relational databases, solving real-world business problems, and generating data-driven insights using **MySQL Workbench**.

## 🛠 Tech Stack
* **Database Management:** MySQL Workbench.
* **Query Language:** SQL (Structured Query Language).
* **Key Concepts:** Relational vs. Non-Relational Databases, Primary/Foreign Keys, and Table Joins.

---

## 📂 Key Projects

### 1. Northwind Traders Analysis (Sales & Supply Chain)
**Scenario:** Acting as a Junior Data Analyst for Northwind Traders to solve real-world business requests.

**Key Achievements:**
* **Inventory & Supply Chain:** Linked products to their respective suppliers and categories to streamline management.
* **Sales Volume Analysis:** Calculated the total quantity ordered for each product to identify sales trends.
* **Customer Segmentation:** Created targeted reports for customers in specific regions like the USA and UK.
* **Reporting:** Developed a complete order overview combining customer names and employee details.

### 2. World Database (Global Demographics)
**Scenario:** Analysis of global data including countries, cities, and languages for an international research organization.

**Key Achievements:**
* **Demographic Insights:** Identified cities with populations exceeding 2 million and those with specific name prefixes for travel blogging.
* **Economic Analysis:** Calculated GDP per capita to identify high-performance urban areas.
* **Health Metrics:** Identified countries with the highest life expectancy to assist in healthcare resource prioritization.
* **Geographical Queries:** Mapped out all cities within Europe and identified capital cities like Madrid (Spain).

---

## 💻 Illustrative SQL Queries

Below are selected queries that demonstrate my ability to handle complex data relationships and logic.


### 1. Sales Volume & Price Analysis
This query calculates the total quantity ordered for every product in the inventory.
```sql
SELECT
    Products.ProductName,
    Products.Price,
    SUM(OrderDetails.Quantity) AS TotalQuantityOrdered
FROM Products
JOIN OrderDetails 
    ON Products.ProductID = OrderDetails.ProductID
GROUP BY 
    Products.ProductName, 
    Products.Price;
````
### 2. High GDP per Capita Identification
A complex query using subqueries to find cities where the country's GDP per capita is above the global average.
```sql
SELECT 
    city.Name AS Cities, 
    country.Name AS Countries, 
    (country.GNP / country.Population) AS High_AVG_per_Capita
FROM city
JOIN country 
    ON city.CountryCode = country.Code
WHERE (country.GNP / country.Population) > (
    SELECT AVG(GNP / Population) 
    FROM country 
    WHERE Population > 0
)
ORDER BY High_AVG_per_Capita DESC;
````
### 3. Multi-Table Join (Orders, Customers, Employees)
Demonstrates the ability to normalize and present data from three different tables into a single readable report.
```sql
SELECT 
    Orders.OrderID,
    Orders.OrderDate,
    Customers.CustomerName,
    CONCAT(Employees.FirstName, ' ', Employees.LastName) AS EmployeeName
FROM Orders
JOIN Customers 
    ON Orders.CustomerID = Customers.CustomerID
JOIN Employees 
    ON Orders.EmployeeID = Employees.EmployeeID;
````
---
## 🧠 Core Competencies
**Relational Logic: Understanding of Primary Keys (unique identifiers) and Foreign Keys (cross-table connections).**
* Data Filtering: Mastery of WHERE, BETWEEN, IN, and LIKE operators.
* Join Proficiency: Ability to implement INNER JOIN, LEFT JOIN, RIGHT JOIN, and SELF-JOIN based on data requirements.
* Data Organization: Skilled in using ORDER BY, GROUP BY, and LIMIT/OFFSET for paginated and organized reporting.
---
## 📫 Contact
* **Name:** Edmilson Fernandes de Assuncao
* **[LinkedIn:](www.linkedin.com/in/edmillson-ass)**


