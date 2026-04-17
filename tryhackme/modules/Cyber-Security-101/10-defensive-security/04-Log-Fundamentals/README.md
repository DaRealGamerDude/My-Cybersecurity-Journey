# TryHackMe Room: Logs Fundamentals

**Path:** Defensive Security  
**Module Type:** Concept + Practical (SOC / Log Analysis)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Logs**, the primary source of evidence in cybersecurity investigations.

It covers:
- Types of logs across systems  
- Windows Event Log analysis  
- Web server access log analysis  
- Manual log investigation techniques  

> Logs represent:
> **Activity → Evidence → Investigation**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Role of logs | ✔ |
| 2 | Types of Logs | Log categorization | ✔ |
| 3 | Windows Logs | Event Viewer analysis | ✔ |
| 4 | Web Logs | Access log investigation | ✔ |
| 5 | Conclusion | Summary | ✔ |

---

# Key Concepts Covered

- Log sources and types  
- Event correlation  
- Windows Event IDs  
- Web access log structure  
- Manual log analysis (Linux tools)  
- DFIR investigation workflow  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction to Logs

**Room Objective:**  
Understand what logs are and why they are critical.

---

### Q1: Where can we find most attack traces?

`Logs`

**Explanation:**  
Logs store digital footprints of all activities (normal + malicious).

---

### Key Learning

- Logs = primary investigation data source  
- Used in:
  - Monitoring  
  - Forensics  
  - Debugging  
  - Compliance  

---

### Use Cases of Logs

| Use Case | Purpose |
|----------|--------|
| Security Monitoring | Detect anomalies |
| Incident Response | Investigate attacks |
| Troubleshooting | Diagnose issues |
| Performance Monitoring | System insights |
| Auditing | Compliance tracking |

---

### Insight

> No logs = no investigation

---

### Common Struggles

- Ignoring logs during incidents  
- Not knowing where to look  

---

## Task 2: Types of Logs

**Room Objective:**  
Understand different categories of logs.

---

### Q1: Logs for network traffic?

`Network Logs`

---

### Q2: Logs for authentication/authorization?

`Security Logs`

---

### Log Categories

| Log Type | Purpose |
|----------|--------|
| System Logs | OS events (startup, drivers) |
| Security Logs | Auth, user actions |
| Application Logs | App-specific events |
| Audit Logs | Compliance & tracking |
| Network Logs | Traffic data |
| Access Logs | Resource access (web/API) |

---

### Key Learning

- Logs are **segregated for efficiency**
- Focus only on **relevant log type**

---

### Insight

> Good analysts don’t read all logs — they read the right logs

---

### Common Struggles

- Looking at wrong log source  
- Getting overwhelmed by volume  

---

## Task 3: Windows Event Logs Analysis

**Room Objective:**  
Analyze Windows logs using Event Viewer.

---

### Windows Log Types

| Log | Purpose |
|-----|--------|
| Application | App events |
| System | OS activity |
| Security | Authentication & user actions |

---

### Important Event IDs

| Event ID | Meaning |
|---------|--------|
| 4624 | Successful login |
| 4625 | Failed login |
| 4634 | Logoff |
| 4720 | User created |
| 4724 | Password reset |
| 4722 | Account enabled |
| 4725 | Account disabled |
| 4726 | Account deleted |

---

### Investigation Scenario

- Data exfiltration incident  
- Goal: Track attacker activity  

---

### Q1: Last created account?

`hacked`

---

### Q2: Who created it?

`Administrator`

---

### Q3: When enabled?

`6/7/2024`

---

### Q4: Password reset?

`Yes`

---

### Explanation

- Event ID 4720 → Account creation  
- Event ID 4722 → Account enabled  
- Event ID 4724 → Password reset  

These events indicate:
- Account created → enabled → modified → suspicious activity chain  

---

### Key Learning

- Event IDs = investigation shortcuts  
- Timeline reconstruction is critical  

---

### Insight

> Logs tell a story — your job is to connect events

---

### Common Struggles

- Not using filters (Event Viewer)  
- Ignoring timeline correlation  

---

### DFIR Perspective

- Detect:
  - Unauthorized account creation  
  - Privilege escalation  
- Correlate:
  - User → Action → Time  

---

## Task 4: Web Server Access Logs Analysis

**Room Objective:**  
Analyze Apache access logs using CLI tools.

---

### Log Format Fields

| Field | Meaning |
|------|--------|
| IP Address | Request source |
| Timestamp | Time of request |
| Method | GET / POST |
| URL | Resource accessed |
| Status Code | Server response |
| User-Agent | Client details |

---

### Example Log Entry

```

192.168.1.1 - - [06/Jun/2024:13:56:44] "GET /about HTTP/1.1" 200 "-"

```

---

### Key Commands

View logs:
```

cat access.log

```

Search logs:
```

grep "IP" access.log

```

Paginated view:
```

less access.log

```

Combine logs:
```

cat file1.log file2.log > combined.log

```

---

### Q1: Last GET request to /contact?

`10.0.0.1`

---

### Q2: Last POST by 172.16.0.1?

`06/Jun/2024:13:55:44`

---

### Q3: URL accessed?

`/contact`

---

### Explanation

- Used `grep` to filter IP  
- Checked timestamps for latest request  
- Identified HTTP method and endpoint  

---

### Key Learning

- Logs = structured data → easy filtering  
- CLI tools are powerful for investigation  

---

### Insight

> grep is your best friend in log analysis

---

### Common Struggles

- Not filtering logs properly  
- Missing patterns in large datasets  

---

### SOC Perspective

Look for:
- Repeated failed requests  
- Suspicious endpoints  
- Unusual IP behavior  
- Abnormal request frequency  

---

## Task 5: Conclusion

**Room Objective:**  
Summarize log analysis importance.

---

### Key Learning

- Logs are critical for:
  - Detection  
  - Investigation  
  - Attribution  

- Manual + automated analysis both required  

---

### Insight

> Logs = ground truth of any incident

---

# Tools Used

- Windows Event Viewer  
- Linux CLI:
  - cat  
  - grep  
  - less  

---

# Commands Cheat Sheet

View logs:
```

cat file.log

```

Search:
```

grep "keyword" file.log

```

Paginate:
```

less file.log

```

---

# DFIR Workflow Summary

1. Identify relevant logs  
2. Filter data  
3. Correlate events  
4. Build timeline  
5. Identify anomalies  
6. Conclude attack behavior  

---

# Reflection

This room is **foundational for SOC and DFIR roles**.

Key takeaways:

- Logs are the backbone of investigations  
- Event IDs simplify Windows analysis  
- Web logs reveal attacker behavior  
- Filtering is more important than reading everything  
