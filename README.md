# 💼 Payroll Management System — MySQL

A relational database project built with **MySQL** to manage employee payroll, attendance, benefits, bonuses, deductions, and reporting for an organization.

> **Group 8 — Database Management Systems Project**

---

## 📋 Table of Contents

- [Overview](#overview)
- [Database Schema](#database-schema)
- [Features](#features)
- [Getting Started](#getting-started)
- [Sample Data](#sample-data)
- [SQL Queries](#sql-queries)
- [Contributors](#contributors)

---

## Overview

This project implements a complete **Payroll Management System** using MySQL. It handles two types of employee salary structures (Fixed and Hourly), tracks attendance, computes payroll, manages deductions and bonuses, and generates analytical reports.

---

## Database Schema

The database `Group8PayrollManagementSystem` contains the following tables:

| Table | Description |
|---|---|
| `JobRole` | Defines job roles within the organization |
| `Employee` | Stores employee personal and job-related information |
| `FixedSalary` | Salary details for fixed-pay employees |
| `HourlySalary` | Hourly rate details for hourly employees |
| `Attendance` | Daily attendance and hours worked |
| `Benefits` | Employee benefits like health insurance, retirement plans |
| `Bonuses` | Bonus records per employee |
| `Deductions` | Deductions such as loans and insurance |
| `Payroll` | Payroll records with pay period information |
| `Payments` | Payment transactions linked to payroll |
| `Users` | Login credentials and user access |
| `Reports` | Generated report metadata |
| `AuditLog` | System activity log for compliance |
| `Miscellaneous` | Miscellaneous configuration data |

### Entity Relationship Overview

```
JobRole ──< Employee >──< FixedSalary
                     >──< HourlySalary
                     >──< Attendance
                     >──< Benefits
                     >──< Bonuses
                     >──< Deductions
                     >──< Payroll >──< Payments
                     >──< Users >──< Reports
                                  >──< AuditLog
```

---

## Features

- ✅ Supports **Fixed** and **Hourly** salary types
- ✅ Tracks **daily attendance** including absences
- ✅ Manages **benefits**, **bonuses**, and **deductions**
- ✅ Full **payroll computation** per pay period
- ✅ **Audit logging** for system activities
- ✅ **Analytical queries** for HR insights

---

## Getting Started

### Prerequisites

- MySQL 8.0 or later
- MySQL Workbench or any MySQL-compatible client

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/payroll-management-system.git
   cd payroll-management-system
   ```

2. Open your MySQL client and run the SQL file:
   ```bash
   mysql -u root -p < Group8PayrollManagementSystem_4.sql
   ```

3. Verify the database was created:
   ```sql
   SHOW DATABASES;
   USE Group8PayrollManagementSystem;
   SHOW TABLES;
   ```

---

## Sample Data

The script includes sample data for:

- 2 employees: `John Doe` (Fixed Salary) and `Jane Smith` (Hourly)
- Attendance records for March 2025
- Benefits, bonuses, and deductions for both employees
- Payroll and payment records

---

## SQL Queries

The project includes the following analytical queries:

| Query | Description |
|---|---|
| Net Pay Calculation | Computes net pay per employee after bonuses and deductions |
| Department-wise Payroll | Total payroll expense broken down by department |
| Absence Tracking | Employees absent more than 3 days in a month |
| Bonus Analysis | Bonus frequency and totals over the last 12 months |
| Salary Outliers | Employees earning significantly above or below their role's average |
| High Deductions | Employees with deductions exceeding 20% of base salary |
| No Bonus Employees | Employees who received no bonus in the current year |
| Combined Bonus & Deductions | Employees who had both a bonus and deductions in the same month |

---

## Contributors

| Name | Contributions |
|---|---|
| Soumya Saswat Patra | Salary outlier analysis, high deduction queries, bonus+deduction overlap |
| Gauri Jayesh Pawar | Absence tracking, no-bonus employee identification |
| Abhishek Bhadauria | Department-wise payroll, bonus frequency analysis |
| *(Group 8 Members)* | Schema design, insert scripts, core payroll logic |

---

## License

This project is for academic purposes only.
