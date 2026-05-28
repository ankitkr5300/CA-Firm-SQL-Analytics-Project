# CA Firm Workforce Analytics (SQL Project)

## Project Overview

This project is a SQL-based data analytics project built using a fictional CA firm workforce dataset.

The project focuses on:

* Employee analytics
* Salary analysis
* Department-wise insights
* Payroll trends
* Workforce reporting

This project demonstrates practical SQL skills required for Data Analyst roles.

---

## Database Structure

### Table 1: Credence_Fintax

Contains information about Chartered Accountants (CA).

| Column Name | Description  |
| ----------- | ------------ |
| CAID        | Unique CA ID |
| CA          | CA Name      |

---

### Table 2: Employees

Contains employee details working under different CAs.

| Column Name | Description                     |
| ----------- | ------------------------------- |
| Empid       | Employee ID                     |
| FirstName   | Employee First Name             |
| LastName    | Employee Last Name              |
| Email       | Employee Email                  |
| MobileNo    | Mobile Number                   |
| Department  | Employee Department             |
| UnderWork   | CA ID under whom employee works |
| Salary      | Employee Salary                 |

---

## Skills Used

* SQL
* Joins
* Aggregate Functions
* Group By
* Subqueries
* Data Analysis
* Workforce Analytics
* Payroll Analysis

---

## Example SQL Analysis

### Total Employees Under Each CA

```sql
SELECT 
c.CA,
COUNT(e.Empid) AS TotalEmployees
FROM Employees e
JOIN Credence_Fintax c
ON e.UnderWork = c.CAID
GROUP BY c.CA;
```

### Highest Salary Employee Under Each CA

```sql
SELECT 
c.CA,
e.FirstName,
e.LastName,
e.Salary
FROM Employees e
JOIN Credence_Fintax c
ON e.UnderWork = c.CAID
WHERE (e.UnderWork, e.Salary) IN (
    SELECT UnderWork, MAX(Salary)
    FROM Employees
    GROUP BY UnderWork
);
```

### Department Wise Average Salary

```sql
SELECT 
Department,
AVG(Salary) AS AverageSalary
FROM Employees
GROUP BY Department
ORDER BY AverageSalary DESC;
```

---

## Key Insights

* Workforce distribution across departments
* Salary comparison between employees
* Highest paid employees under each CA
* Department-wise salary trends
* Payroll analytics for decision making

---

## Tools Used

* MySQL
* GitHub
* SQL Queries
* Data Analytics Concepts

---

## Author

Ankit Kumar
Aspiring Data Analyst | SQL Enthusiast
