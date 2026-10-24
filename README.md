# SDM Employees Database Management System

### SQL Project | MySQL | Database Management | Data Analysis

![MySQL](https://img.shields.io/badge/Database-MySQL-blue?logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/Language-SQL-orange)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [Database Schema](#-database-schema)
- [Project Features](#-project-features)
- [SQL Concepts Used](#-sql-concepts-used)
- [Project Queries](#-project-queries)
- [Screenshots](#-screenshots)
- [Project Structure](#-project-structure)
- [Installation and Setup](#-installation-and-setup)
- [How to Run](#-how-to-run)
- [Key Learnings](#-key-learnings)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

## 📖 Project Overview

The **SDM Employees Database Management System** is a SQL-based project developed using MySQL to manage employee and department information.

The project consists of two relational tables: `Employees` and `Departments`. It demonstrates how SQL can be used to retrieve, organize, join, and analyze employee data through various queries.

The database contains employee IDs, employee names, ages, department IDs, and department names across 10 professional domains. It includes 20 employee records and 15 SQL queries covering basic data retrieval, filtering, sorting, joins, and aggregate functions.

This project demonstrates practical SQL skills and foundational relational database concepts useful for database management and data analytics.

## 🎯 Project Objectives

- Create and manage a relational database using MySQL.
- Store employee and department information in structured tables.
- Establish relationships between tables using primary and foreign keys.
- Retrieve employee information using `SELECT` statements.
- Filter records using `WHERE` conditions.
- Sort data using `ORDER BY`.
- Combine related data using `JOIN` operations.
- Analyze employee data using aggregate functions.
- Calculate employee counts and age statistics for different departments.

## 🏗️ Database Schema

The database is named `SDM_Employees` and contains two tables.

### 1. Departments Table

Stores the available professional domains.

| Column | Data Type | Description |
|---|---|---|
| `Domain_id` | INT | Primary key identifying each domain |
| `Domain_name` | VARCHAR(50) | Name of the professional domain |

### 2. Employees Table

Stores employee details and their associated domains.

| Column | Data Type | Description |
|---|---|---|
| `Employee_id` | INT | Primary key identifying each employee |
| `Employee_name` | VARCHAR(50) | Employee's name |
| `age` | INT | Employee's age |
| `Domain_id` | INT | Foreign key referencing the Departments table |

### Relationship Between Tables

The `Domain_id` column connects the two tables.

- **Primary Key:** `Departments.Domain_id`
- **Foreign Key:** `Employees.Domain_id`
- **Relationship:** One department can have multiple employees.

```text
Departments
------------
Domain_id (PK)
Domain_name
      |
      | 1
      |
      | N
Employees
------------
Employee_id (PK)
Employee_name
age
Domain_id (FK)
```

## ✨ Project Features

- **Database Creation:** Creates the `SDM_Employees` database.
- **Table Creation:** Defines the employee and department tables.
- **Data Insertion:** Inserts sample records into both tables.
- **Employee Filtering:** Finds employees based on age and department.
- **Data Sorting:** Displays employees in ascending order of domain IDs.
- **Table Joins:** Combines employee and department information.
- **Department Analysis:** Counts employees in each department.
- **Age Analysis:** Calculates average, maximum, and minimum employee ages.
- **Grouped Analysis:** Counts employees by age.

## 🧠 SQL Concepts Used

| SQL Concept | Application |
|---|---|
| `CREATE DATABASE` | Creates the project database |
| `CREATE TABLE` | Defines the database structure |
| `INSERT INTO` | Adds employee and department records |
| `SELECT` | Retrieves database records |
| `WHERE` | Filters records based on conditions |
| `ORDER BY` | Sorts query results |
| `COUNT()` | Counts employees and records |
| `AVG()` | Calculates average employee age |
| `MAX()` | Finds the maximum age |
| `MIN()` | Finds the minimum age |
| `GROUP BY` | Groups records for aggregate analysis |
| `INNER JOIN` | Retrieves matching employee and department records |
| `LEFT JOIN` | Displays all departments, including those without employees |
| `PRIMARY KEY` | Uniquely identifies records |
| `FOREIGN KEY` | Establishes a relationship between tables |
| Table aliases | Simplifies SQL query writing |

## 🔍 Project Queries

The project includes 15 SQL queries organized around data retrieval and analysis.

| Query | Description |
|---|---|
| 01 | Display all records from Departments and Employees |
| 02 | Display employee names and domain IDs |
| 03 | Find employees older than 20 |
| 04 | Sort employees by domain ID in ascending order |
| 05 | Count the total number of employees |
| 06 | Display employee names with their domain names |
| 07 | Find employees belonging to the Data Scientist domain |
| 08 | Display employees aged 21 or younger with their domain details |
| 09 | Find employees working in Full Stack Development |
| 10 | Display all departments with their employee names |
| 11 | Count employees in each department |
| 12 | Calculate the average age in each department |
| 13 | Find the maximum age in each department |
| 14 | Find the minimum age in each department |
| 15 | Count employees by age |

### Example 1: Display Employees with Their Department Names

```sql
SELECT
    e.Employee_name,
    d.Domain_name
FROM Employees e
JOIN Departments d
    ON e.Domain_id = d.Domain_id;
```

**Purpose:** Combines employee and department information using an `INNER JOIN`.

### Example 2: Count Employees in Each Department

```sql
SELECT
    d.Domain_name,
    COUNT(e.Employee_id) AS Total_Employees
FROM Departments d
LEFT JOIN Employees e
    ON d.Domain_id = e.Domain_id
GROUP BY d.Domain_id, d.Domain_name;
```

**Purpose:** Counts employees for each department and includes departments with zero employees.

### Example 3: Calculate Average Age by Department

```sql
SELECT
    d.Domain_name,
    AVG(e.age) AS Average_Age
FROM Departments d
JOIN Employees e
    ON d.Domain_id = e.Domain_id
GROUP BY d.Domain_id, d.Domain_name;
```

**Purpose:** Calculates the average age of employees in each department.

### Example 4: Count Employees by Age

```sql
SELECT
    age,
    COUNT(*) AS Total_Employees
FROM Employees
GROUP BY age
ORDER BY age;
```







## 📁 Project Structure

A suggested repository structure is:

```text
SDM-Employees/
│
├── README.md
├── SDM_Employees.sql
│
└── screenshots/
    ├── database_setup.png
    ├── employee_records.png
    └── query_results.png
```

Save your complete SQL script as `SDM_Employees.sql`. The screenshot filenames are suggested names for organizing your images.

## ⚙️ Installation and Setup

### Prerequisites

- MySQL Server 8.0 or a compatible MySQL version.
- MySQL Workbench or another SQL editor.
- Basic knowledge of SQL.

### Step 1: Install MySQL

Download MySQL from the official website:

[Download MySQL Community Server](https://dev.mysql.com/downloads/mysql/)

You can also use MySQL Workbench to execute queries and view the results.

[Download MySQL Workbench](https://dev.mysql.com/downloads/workbench/)

### Step 2: Clone the Repository

Replace the placeholder below with your actual GitHub repository URL.

```bash
git clone YOUR_REPOSITORY_URL
```

Navigate to the project directory:

```bash
cd SDM-Employees
```

Alternatively, download the repository as a ZIP file from GitHub.

### Step 3: Open the SQL Script

Open `SDM_Employees.sql` in MySQL Workbench or your preferred SQL editor.

### Step 4: Create the Database

Execute the following statements:

```sql
CREATE DATABASE SDM_Employees;
USE SDM_Employees;
```

The full project script already includes these commands, so you can execute the complete script instead of running them separately.

## ▶️ How to Run

1. Start MySQL Server.
2. Open MySQL Workbench and connect to your local MySQL instance.
3. Open `SDM_Employees.sql`.
4. Execute the complete SQL script to create the database, create both tables, and insert the sample records.
5. Run the individual queries to view the results.
6. Review the output grids for employee details, department information, and age statistics.

To verify the total number of employees, execute:

```sql
USE SDM_Employees;

SELECT COUNT(*) AS Total_Employees
FROM Employees;
```

**Expected result:** `20` employees.

To verify the number of departments, execute:

```sql
SELECT COUNT(*) AS Total_Departments
FROM Departments;
```

**Expected result:** `10` departments.

> **Note:** The script creates a database with a fixed name. If you execute it again, the database may already exist. For a fresh run, use a new database name or reset the existing project database carefully.

## 📊 Key Learnings

Through this project, I practiced:

- Designing relational databases with primary and foreign keys.
- Creating tables and inserting structured data.
- Writing SQL queries to retrieve and filter information.
- Understanding the difference between `INNER JOIN` and `LEFT JOIN`.
- Using aggregate functions for data analysis.
- Grouping and sorting query results.
- Analyzing employee distribution and age statistics.
- Organizing SQL scripts into a practical database project.

## 🚀 Future Improvements

Potential enhancements include:

- Adding employee email addresses, salaries, and joining dates.
- Introducing employee department transfer records.
- Creating views for frequently used queries.
- Adding stored procedures for reusable operations.
- Using triggers to maintain audit records.
- Connecting the database to Power BI for interactive reporting.
- Developing a dashboard to visualize department-wise employee distribution and age demographics.

## 🛠️ Technologies Used

- **Database:** MySQL
- **Query Language:** SQL
- **SQL Editor:** MySQL Workbench
- **Version Control:** Git and GitHub

## 👩‍💻 Author

**Sapna Yadav**

Interested in data analytics, SQL, database management, and transforming structured data into useful insights.

Explore my work on GitHub:

[Visit My GitHub Profile](https://github.com/Sapna2026)

---

⭐ If you find this project useful, consider giving the repository a star!

*This project was created for SQL practice and learning relational database concepts.*
