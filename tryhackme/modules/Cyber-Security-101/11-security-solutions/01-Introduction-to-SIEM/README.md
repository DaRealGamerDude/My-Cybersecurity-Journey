# TryHackMe Room: Introduction to SIEM

**Path:** Security Solutions  
**Module Type:** Concept + Practical (SOC / SIEM)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **SIEM (Security Information and Event Management)** — the core tool used in SOC environments.

It covers:
- Log sources (host + network)  
- Log ingestion & normalization  
- Correlation of events  
- Detection rules & alerting  
- SIEM-based investigation  

> SIEM = **Logs → Correlation → Detection → Alerts**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | SIEM basics | ✔ |
| 2 | Logs Everywhere | Log challenges | ✔ |
| 3 | Why SIEM | SIEM features | ✔ |
| 4 | Log Sources | Ingestion methods | ✔ |
| 5 | Alerting | Detection rules | ✔ |
| 6 | Lab | Alert investigation | ✔ |
| 7 | Conclusion | Recap | ✔ |

---

# Key Concepts Covered

- Host vs Network logs  
- Log centralization  
- Parsing & normalization  
- Event correlation  
- Detection rules  
- Alert triage  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Room Objective:**  
Understand what SIEM is and why it is used.

---

### Q1: What does SIEM stand for?

`Security Information and Event Management system`

**Explanation:**  
A centralized solution for collecting, analyzing, and detecting threats from logs.

---

### Key Learning

- SIEM is the **core tool in SOC**
- Used for:
  - Monitoring  
  - Detection  
  - Investigation  

---

### Insight

> No SIEM = no scalable security monitoring

---

### Common Struggles

- Thinking SIEM = just logs  
- Ignoring detection capability  

---

## Task 2: Logs Everywhere, Answers Nowhere

**Room Objective:**  
Understand problems with raw logs.

---

### Q1: Registry activity type?

`host-centric`

**Explanation:**  
Occurs within the system.

---

### Q2: VPN activity type?

`network-centric`

**Explanation:**  
Occurs across network communication.

---

### Log Types

| Type | Example |
|------|--------|
| Host-Centric | File access, process execution |
| Network-Centric | VPN, HTTP traffic |

---

### Problems Without SIEM

- Too many logs  
- No centralization  
- No correlation  
- Format differences  
- Manual analysis impossible  

---

### Insight

> Logs alone ≠ visibility

---

### Common Struggles

- Looking at logs in isolation  
- Missing attack patterns  

---

## Task 3: Why SIEM?

**Room Objective:**  
Understand SIEM capabilities.

---

### Key Features

| Feature | Description |
|--------|------------|
| Centralization | Collect logs in one place |
| Normalization | Convert logs into standard format |
| Correlation | Link events across systems |
| Alerting | Detect suspicious behavior |
| Dashboards | Visual analysis |

---

### Key Learning

- Parsing = breaking logs into fields  
- Normalization = standard format  
- Correlation = linking events  

---

### Example Insight

Multiple small events → major attack:

- VPN login  
- File access  
- PowerShell execution  
- Outbound traffic  

→ **Data exfiltration**

---

### Insight

> SIEM connects the dots humans miss

---

### Common Struggles

- Not understanding correlation  
- Treating events independently  

---

## Task 4: Log Sources & Ingestion

**Room Objective:**  
Understand where logs come from.

---

### Q1: Linux HTTP log location?

`/var/log/httpd`

**Explanation:**  
Stores web server logs.

---

### Common Log Sources

| Source | Example |
|-------|--------|
| Windows | Event Viewer |
| Linux | /var/log |
| Web Server | Apache logs |
| Network Devices | Firewall, IDS |

---

### Log Ingestion Methods

| Method | Description |
|--------|------------|
| Agent | Installed on endpoints |
| Syslog | Standard protocol |
| Manual Upload | Offline logs |
| Port Forwarding | Direct transmission |

---

### Insight

> If logs aren’t ingested → they don’t exist for SOC

---

### Common Struggles

- Ignoring ingestion pipeline  
- Not understanding log sources  

---

## Task 5: Alerting Process & Analysis

**Room Objective:**  
Understand detection logic.

---

### Q1: Event ID for log deletion?

`104`

**Explanation:**  
Indicates logs were cleared.

---

### Q2: Which alert needs tuning?

`False Positive`

**Explanation:**  
Incorrect detection.

---

### Detection Rules

Examples:

- 5 failed logins → alert  
- Large outbound traffic → alert  
- USB inserted → alert  

---

### Rule Example

```

IF EventID = 4688 AND Process = whoami
→ ALERT

```

---

### Key Learning

- Rules = logic-based triggers  
- Based on:
  - Fields  
  - Values  

---

### Alert Investigation Flow

1. Alert triggered  
2. Check rule  
3. Analyze events  
4. Decide:
   - False Positive → tune  
   - True Positive → escalate  

---

### Insight

> Detection rules define SOC maturity

---

### Common Struggles

- Blindly trusting alerts  
- Not checking rule logic  

---

## Task 6: Lab — SIEM Investigation

**Room Objective:**  
Investigate a real alert.

---

### Answers

---

### Q1: Malicious process?

`cudominer.exe`

**Explanation:**  
Crypto miner detected.

---

### Q2: User?

`chris`

**Explanation:**  
Executed the process.

---

### Q3: Hostname?

`HR_02`

**Explanation:**  
Compromised system.

---

### Q4: Rule match term?

`miner`

**Explanation:**  
Keyword triggered detection.

---

### Q5: Alert type?

`True Positive`

**Explanation:**  
Actual malicious activity.

---

### Q6: Flag?

`THM{000_SIEM_INTRO}`

**Explanation:**  
Final validation.

---

### Insight

> SIEM = investigation platform, not just alert generator

---

### Common Struggles

- Not correlating fields  
- Missing key indicators  

---

## Task 7: Conclusion

- SIEM enables:
  - Centralized monitoring  
  - Detection  
  - Investigation  

---

# Tools / Technologies Introduced

- SIEM (Splunk-like systems)  
- Syslog  
- Windows Event Logs  
- Linux logs  

---

# SIEM Workflow Cheat Sheet

1. Logs generated  
2. Logs ingested  
3. Logs normalized  
4. Correlation  
5. Detection rule triggers  
6. Alert generated  
7. Analyst investigates  

---

# Reflection

This is **one of the most important modules for your career path**.

You now understand:

- How logs work  
- How detection works  
- How SOC actually operates  
