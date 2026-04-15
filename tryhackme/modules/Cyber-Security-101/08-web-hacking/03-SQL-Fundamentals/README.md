# TryHackMe Room: SQL Fundamentals

**Path:** Web Hacking  
**Module Type:** Theory + Hands-on (Database Fundamentals)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **databases and SQL** from a cybersecurity perspective.

It covers:
- Database fundamentals (tables, rows, keys)  
- Relational vs Non-relational databases  
- SQL syntax and commands  
- CRUD operations  
- Clauses, operators, and functions  

It builds the foundation required for understanding:
- SQL Injection (SQLi)  
- Backend data manipulation  
- Database-driven applications  

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Importance of databases | ✔ |
| 2 | Databases 101 | Types, tables, keys | ✔ |
| 3 | SQL | DBMS & query language | ✔ |
| 4 | Database & Tables | Creation & structure | ✔ |
| 5 | CRUD | Data operations | ✔ |
| 6 | Clauses | Filtering & grouping | ✔ |
| 7 | Operators | Logical conditions | ✔ |
| 8 | Functions | Data manipulation | ✔ |
| 9 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered (Module-Level)

- Relational vs Non-relational databases  
- Tables, rows, columns  
- Primary & Foreign keys  
- SQL syntax and query structure  
- CRUD operations  
- Data filtering (WHERE, LIKE, etc.)  
- Aggregation and grouping  
- Logical and comparison operators  
- SQL functions (COUNT, SUM, etc.)  

---

# Room Notes & Task Breakdown

---

## Task 2: Databases 101

**Room Objective:**  
Understand database types and structure.

---

### Key Learning

- Databases store structured data  
- Two main types:
  - Relational (structured, tables)  
  - Non-relational (flexible, NoSQL)  
- Data is stored as:
  - Tables → Rows → Columns  
- Keys define relationships and uniqueness  

---

### Q1: Variable format data?

Non-relational database  

**Explanation:**  
NoSQL handles flexible, unstructured data formats.

---

### Q2: Structured format data?

Relational database  

**Explanation:**  
SQL databases enforce schema → consistent structure.

---

### Q3: Record representation?

row  

**Explanation:**  
Each entry in a table is stored as a row.

---

### Q4: Link between tables?

foreign key  

**Explanation:**  
Connects one table to another.

---

### Q5: Unique record identifier?

primary key  

**Explanation:**  
Ensures each record is uniquely identifiable.

---

### Common Struggles

- Confusing relational vs NoSQL  
- Not visualizing tables (rows/columns)  
- Mixing up primary vs foreign keys  

---

## Task 3: SQL

**Room Objective:**  
Understand SQL and DBMS.

---

### Key Learning

- DBMS = interface between user and database  
- SQL = language to interact with databases  
- Used for:
  - Querying  
  - Inserting  
  - Updating  
  - Deleting data  

---

### Q1: Interface between user & DB?

DBMS  

**Explanation:**  
Software layer that manages database interaction.

---

### Q2: Query language?

SQL  

**Explanation:**  
Used to manipulate relational databases.

---

### Common Struggles

- Confusing DBMS vs database  
- Treating SQL as a programming language (it’s query-based)  

---

## Task 4: Database and Table Statements

**Room Objective:**  
Learn how to create and manage databases/tables.

---

### Key Learning

Core commands:

| Command | Purpose |
|--------|--------|
| CREATE DATABASE | Create DB |
| SHOW DATABASES | List DBs |
| USE | Select DB |
| CREATE TABLE | Create table |
| SHOW TABLES | List tables |
| DESCRIBE | View schema |
| ALTER | Modify table |
| DROP | Delete DB/table |

---

### Important Commands

Create DB

CREATE DATABASE thm_bookmarket_db;

List DBs

SHOW DATABASES;

Select DB

USE thm_bookmarket_db;

Create Table

CREATE TABLE book_inventory (
  book_id INT AUTO_INCREMENT PRIMARY KEY,
  book_name VARCHAR(255),
  publication_date DATE
);

---

### Q1: Flag database?

THM{575a947132312f97b30ee5aeebba629b723d30f9}

**Explanation:**  
Found using `SHOW DATABASES`.

---

### Q2: Flag in task_4_db?

THM{692aa7eaec2a2a827f4d1a8bed1f90e5e49d2410}

**Explanation:**  
Used:
- `USE task_4_db`
- `SHOW TABLES`

---

### Common Struggles

- Forgetting to `USE` database  
- Syntax errors in CREATE TABLE  
- Not understanding schema structure  

---

## Task 5: CRUD Operations

**Room Objective:**  
Learn core data manipulation operations.

---

### Key Learning

| Operation | SQL Command |
|----------|------------|
| Create | INSERT |
| Read | SELECT |
| Update | UPDATE |
| Delete | DELETE |

---

### Example

SELECT * FROM books;

---

### Q1: MITM tool?

Wi-Fi Pineapple  

**Explanation:**  
Filtered using SELECT queries on description.

---

### Q2: Shared category?

USB attacks  

**Explanation:**  
Both tools categorized under USB-based attacks.

---

### Common Struggles

- Mixing SELECT vs INSERT  
- Forgetting WHERE (dangerous in UPDATE/DELETE)  
- Not filtering results properly  

---

## Task 6: Clauses

**Room Objective:**  
Filter and organize query results.

---

### Key Learning

| Clause | Purpose |
|-------|--------|
| DISTINCT | Remove duplicates |
| GROUP BY | Group data |
| ORDER BY | Sort data |
| HAVING | Filter grouped results |

---

### Q1: Distinct categories?

6  

**Explanation:**  
Used DISTINCT on category column.

---

### Q2: First tool (ASC)?

Bash Bunny  

**Explanation:**  
Sorted alphabetically ascending.

---

### Q3: First tool (DESC)?

Wi-Fi Pineapple  

**Explanation:**  
Sorted descending order.

---

### Common Struggles

- Confusing WHERE vs HAVING  
- Forgetting ASC/DESC  
- Not understanding grouping  

---

## Task 7: Operators

**Room Objective:**  
Use logic and comparisons in queries.

---

### Key Learning

Logical:
- AND, OR, NOT  

Pattern:
- LIKE  

Range:
- BETWEEN  

Comparison:
- =, !=, <, >, <=, >=  

---

### Q1: Multi-tool device?

Flipper Zero  

**Explanation:**  
Filtered using category + description.

---

### Q2: Category ≥ 300?

RFID cloning  

**Explanation:**  
Used `amount >= 300`.

---

### Q3: Network tool < 100?

Lan Turtle  

**Explanation:**  
Filtered using category + amount.

---

### Common Struggles

- Mixing AND vs OR  
- Incorrect LIKE syntax  
- Not combining conditions properly  

---

## Task 8: Functions

**Room Objective:**  
Manipulate and aggregate data.

---

### Key Learning

String:
- CONCAT  
- LENGTH  
- SUBSTRING  

Aggregate:
- COUNT  
- SUM  
- MAX  
- MIN  

---

### Q1: Longest name?

USB Rubber Ducky  

**Explanation:**  
Used LENGTH + ORDER BY DESC.

---

### Q2: Total sum?

1444  

**Explanation:**  
Used SUM(amount).

---

### Q3: Names (non-zero ending)?

Flipper Zero & iCopy-XS  

**Explanation:**  
Used:
- SUBSTRING  
- GROUP_CONCAT  

---

### Common Struggles

- Not knowing when to use functions  
- Confusing aggregate vs string functions  
- Forgetting GROUP BY with aggregation  

---

# Tools / Technologies Used in This Module

- MySQL  
- SQL (Structured Query Language)  
- TryHackMe AttackBox  

---

# Commands, Syntax & Patterns to Remember

Database

CREATE DATABASE name;  
SHOW DATABASES;  
USE name;  

Tables

CREATE TABLE name (...);  
SHOW TABLES;  
DESCRIBE table;  

CRUD

INSERT INTO table VALUES (...);  
SELECT * FROM table;  
UPDATE table SET ... WHERE ...;  
DELETE FROM table WHERE ...;  

Filtering

WHERE  
LIKE  
BETWEEN  

Sorting

ORDER BY ASC/DESC  

Aggregation

COUNT()  
SUM()  
MAX()  
MIN()  

---

# Reflection

This module builds a critical foundation:

> **Most applications = database-backed systems**

Key takeaways:

- SQL is everywhere (apps, logs, SIEMs)  
- Poor query handling → SQL Injection  
- Data relationships = attack surface  
- Filtering & querying = core analyst skill  

This directly connects to:

- SQL Injection exploitation  
- SOC log querying  
- DFIR database analysis  
- Threat hunting using structured data
