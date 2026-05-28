# CA Firm SQL Analytics Project

A comprehensive SQL analytics project for managing and analyzing employee data across Credence Fintax CA firm offices.

## 📋 Project Overview

This project contains SQL database schemas and scripts for:
- Managing CA firm employee records
- Tracking employee departments and reporting structure
- Analyzing salary and compensation data
- Generating HR analytics and reports

## 📁 Database Structure

### Tables

#### Credence_Fintax
Stores information about CAs (Chartered Accountants) heading different offices.
- **CAID** (INT, PRIMARY KEY): Unique CA identifier
- **CA** (VARCHAR 100): Name of the Chartered Accountant

#### Employees
Comprehensive employee data for the CA firm.
- **Empid** (INT, PRIMARY KEY): Employee ID
- **FirstName** (VARCHAR 200): Employee first name
- **LastName** (VARCHAR 200): Employee last name
- **Email** (VARCHAR 255, UNIQUE): Employee email address
- **MobileNo** (VARCHAR 150): Contact phone number
- **Department** (VARCHAR 150): Department assignment
- **UnderWork** (INT): Reports to CA (Foreign Key to Credence_Fintax.CAID)
- **Salary** (INT): Monthly salary in INR

## 👥 Departments

- Accountant
- Assistant Accountant
- GST
- Tally work
- Taxation work
- Auditor
- Income Tax Specialist
- TDS Executive
- Articled Assistant
- Senior Auditor
- Payroll Executive
- Taxation Manager
- GST Specialist
- Corporate Compliance
- Admin

## 🏢 CA Offices

| CAID | CA Name |
|------|---------|
| 53426 | Chandra Bhushan |
| 65984 | Vikash Singh |
| 75895 | Prakash Singh |

## 📊 Key Statistics

- **Total Employees**: 298
- **Total CA Offices**: 3
- **Average Salary**: ₹18,500+ (varies by department)
- **Department Distribution**: 15+ specialized departments

## 🚀 Getting Started

1. Create the database tables using `schema.sql`
2. Insert sample data using `data.sql`
3. Run analytics queries from `queries.sql`

## 📝 Sample Queries

### Find employees by CA office
```sql
SELECT e.* FROM Employees e 
WHERE e.UnderWork = 53426;
```

### Average salary by department
```sql
SELECT Department, AVG(Salary) as AvgSalary 
FROM Employees 
GROUP BY Department;
```

### Employees by CA
```sql
SELECT cf.CA, COUNT(e.Empid) as EmployeeCount 
FROM Credence_Fintax cf 
LEFT JOIN Employees e ON cf.CAID = e.UnderWork 
GROUP BY cf.CA;
```

## 📦 Files

- `schema.sql` - Database table definitions
- `data.sql` - Sample employee and CA data
- `queries.sql` - Useful analytics queries
- `README.md` - Project documentation

## 🔧 Technical Details

- **Database**: SQL Server / MySQL Compatible
- **Encoding**: UTF-8
- **Character Set**: Supports Indian names and characters

## 📧 Contact

For questions or suggestions regarding this project, please reach out to the development team.

---
**Last Updated**: May 28, 2026
