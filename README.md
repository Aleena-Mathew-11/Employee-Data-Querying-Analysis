# MySQL Employee Data Querying & Analysis

## 📌 Project Overview

This project focuses on querying and analyzing employee data using MySQL. It builds upon a previously created Employee Database and demonstrates the use of SQL querying techniques to retrieve, filter, sort, aggregate, and analyze data.

The project covers fundamental and intermediate SQL concepts including filtering records, aggregate functions, grouping data, and performing joins between multiple tables.

---

## 🎯 Objectives

- Retrieve and analyze employee information using SQL queries.
- Apply filtering techniques using WHERE conditions.
- Perform data sorting and limiting operations.
- Use aggregate functions to generate business insights.
- Group data and apply conditions using GROUP BY and HAVING.
- Establish relationships between tables using JOIN operations.
- Develop practical SQL querying skills for real-world database analysis.

---

## 🗄️ Database Structure

### Departments Table

- department_id
- department_name

### Location Table

- location_id
- location

### Employees Table

- employee_id
- employee_name
- gender
- age
- hire_date
- designation
- department_id
- location_id
- salary

---

## 🛠 SQL Concepts Implemented

### DISTINCT

```sql
SELECT DISTINCT salary
FROM Employees;
```

### Alias (AS)

```sql
SELECT age AS Employee_Age,
       salary AS Employee_Salary
FROM Employees;
```

### WHERE Clause

```sql
SELECT employee_id,
       employee_name,
       salary,
       hire_date
FROM Employees
WHERE salary > 50000
AND hire_date < '2016-01-01';
```

### UPDATE Statement

```sql
UPDATE Employees
SET designation = 'Data Scientist'
WHERE employee_id = 5004;
```

### ORDER BY

```sql
SELECT employee_id,
       employee_name,
       department_id,
       salary
FROM Employees
ORDER BY department_id ASC,
         salary DESC;
```

### LIMIT

```sql
SELECT employee_id,
       employee_name,
       hire_date,
       designation,
       salary
FROM Employees
WHERE YEAR(hire_date) = 2018
ORDER BY hire_date ASC
LIMIT 5;
```

---

## 📊 Aggregate Functions

### Total Salary in Finance Department

```sql
SELECT SUM(salary) AS Total_Finance_Salary
FROM Employees
WHERE department_id = 7;
```

### Minimum Employee Age

```sql
SELECT MIN(age) AS Youngest_Employee_Age
FROM Employees;
```

---

## 📈 GROUP BY Operations

### Maximum Salary by Location

```sql
SELECT l.location,
       MAX(e.salary) AS Max_Salary
FROM Employees e
JOIN Location l
ON e.location_id = l.location_id
GROUP BY l.location;
```

### Average Salary of Analyst Roles

```sql
SELECT designation,
       AVG(salary) AS Avg_Salary
FROM Employees
WHERE designation LIKE '%Analyst%'
GROUP BY designation;
```

---


## 🔍 HAVING Clause

### Departments with Less Than 3 Employees

```sql
SELECT department_id,
       COUNT(*) AS Employee_Count
FROM Employees
GROUP BY department_id
HAVING COUNT(*) < 3;
```

### Locations with Female Employees Having Average Age Below 30

```sql
SELECT location_id,
       AVG(age) AS Avg_Female_Age
FROM Employees
WHERE gender = 'F'
GROUP BY location_id
HAVING AVG(age) < 30;
```

---

## 🔗 JOIN Operations

### INNER JOIN

```sql
SELECT e.employee_name,
       e.designation,
       d.department_name
FROM Employees e
INNER JOIN Departments d
ON e.department_id = d.department_id;
```

### LEFT JOIN

```sql
SELECT d.department_name,
       COUNT(e.employee_id) AS Total_Employees
FROM Departments d
LEFT JOIN Employees e
ON d.department_id = e.department_id
GROUP BY d.department_name;
```

### RIGHT JOIN

```sql
SELECT l.location,
       e.employee_name
FROM Employees e
RIGHT JOIN Location l
ON e.location_id = l.location_id;
```

---

## 💻 Technologies Used

- MySQL
- SQL
- Relational Database Management System (RDBMS)
- Data Querying
- Data Analysis

---

## 📚 Skills Demonstrated

✅ DISTINCT Queries

✅ Aliases (AS)

✅ WHERE Clause & Operators

✅ UPDATE Statements

✅ ORDER BY

✅ LIMIT

✅ Aggregate Functions

✅ GROUP BY

✅ HAVING

✅ INNER JOIN

✅ LEFT JOIN

✅ RIGHT JOIN

✅ Employee Data Analysis

---

## 🎓 Learning Outcomes

Through this project, I gained practical experience in:

- Writing SQL queries for real-world business scenarios
- Retrieving and filtering data efficiently
- Using aggregate functions for reporting
- Applying GROUP BY and HAVING clauses
- Combining data from multiple tables using JOINs
- Transforming raw data into meaningful insights

---

## 🚀 Key Takeaways

- Improved SQL querying and analytical skills.
- Learned to extract business insights from employee datasets.
- Strengthened understanding of relational database concepts.
- Gained hands-on experience with joins, aggregations, and data filtering.

---

## 👩‍💻 Author

Aleena Mathew

Aspiring Data Analyst | SQL | Excel | Power BI | Python
