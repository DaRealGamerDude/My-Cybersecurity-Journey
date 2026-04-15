# TryHackMe Room: Defensive Security — Introduction

**Path:** Start Your Cyber Security Journey  
**Module Type:** Conceptual (Blue Team Fundamentals)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Defensive Security (Blue Team)** and its role in protecting organisations.

It covers:
- SOC (Security Operations Centre)  
- Digital Forensics  
- Incident Response  
- SIEM-based monitoring  

> Defensive Security focuses on:
> **Prevention + Detection + Response**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Blue Team fundamentals | ✔ |
| 2 | SOC | Monitoring & detection | ✔ |
| 3 | Digital Forensics | Evidence analysis | ✔ |
| 4 | Incident Response | Handling attacks | ✔ |
| 5 | Practical | SIEM workflow | ✔ |

---

# Key Concepts Covered

- Blue Team operations  
- Security monitoring & alerting  
- Log analysis (system + network)  
- Digital evidence handling  
- Incident response lifecycle  
- SIEM fundamentals  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction to Defensive Security

**Room Objective:**  
Understand the purpose of defensive security.

---

### Q1: Which team focuses on defensive security?

`Blue Team`

**Explanation:**  
Blue Team is responsible for protecting systems and responding to threats.

---

### Key Learning

- Two main goals:
  - Prevent attacks  
  - Detect & respond to attacks  

---

### Core Activities

- Security awareness training  
- Asset management  
- Firewalls / IPS  
- Logging & monitoring  
- Policies & procedures  

---

### Insight

> You cannot defend what you don’t know exists (asset visibility)

---

### Common Struggles

- Ignoring logging importance  
- Over-focusing on tools instead of processes  

---

## Task 2: Security Operations Centre (SOC)

**Room Objective:**  
Understand SOC responsibilities.

---

### Q1: Team monitoring networks for threats?

`Security Operations Centre`

**Explanation:**  
SOC continuously monitors systems for suspicious activity.

---

### Key Learning

SOC responsibilities include:

- Threat intelligence awareness  
- Policy violation detection  
- Detecting unauthorized activity  
- Identifying breaches  

---

### Insight

> SOC = real-time defense layer

---

### Common Struggles

- Not understanding baseline behavior  
- Treating alerts without context  

---

## Task 3: Digital Forensics

**Room Objective:**  
Understand how evidence is analyzed.

---

### Q1: Malware running only in memory → what to analyze?

`System Memory`

**Explanation:**  
Memory forensics reveals in-memory malware.

---

### Key Learning

Evidence sources:

| Source | Purpose |
|-------|--------|
| File System | Files, artifacts, deleted data |
| Memory | In-memory malware |
| System Logs | System activity |
| Network Logs | Traffic analysis |

---

### Insight

> Logs + memory = truth of what happened

---

### Common Struggles

- Ignoring volatile data (memory)  
- Over-relying on disk artifacts  

---

## Task 4: Incident Response

**Room Objective:**  
Understand incident handling lifecycle.

---

### Q1: Phase involving cyber awareness training?

`Preparation`

**Explanation:**  
Preparation includes training, planning, and readiness.

---

### Incident Response Phases

| Phase | Purpose |
|------|--------|
| Preparation | Readiness & prevention |
| Detection & Analysis | Identify incidents |
| Containment, Eradication, Recovery | Stop & fix |
| Post-Incident | Learn & improve |

---

### Insight

> Detection without response = useless

---

### Common Struggles

- Skipping post-incident analysis  
- Weak preparation phase  

---

## Task 5: Practical — SIEM Simulation

**Room Objective:**  
Apply SOC workflow using SIEM.

---

### Scenario

- Monitor alerts  
- Investigate suspicious activity  
- Identify threat  

---

### Q1: Final flag?

`THREAT-BLOCKED`

**Explanation:**  
Detected and responded to malicious activity via SIEM.

---

### Key Learning

- SIEM aggregates logs  
- Alerts indicate anomalies  
- Analyst investigates + responds  

---

### Insight

> SIEM = central nervous system of SOC

---

### Common Struggles

- Alert fatigue  
- Not correlating events properly  

---

# Tools / Technologies Introduced

- SIEM (Security Information and Event Management)  
- Logging systems  
- Network monitoring tools  

---

# Workflow Summary (SOC Perspective)

1. Collect logs  
2. Detect anomalies  
3. Investigate alerts  
4. Contain threat  
5. Recover systems  
6. Document findings  

---

# Reflection

This module defines your **core career direction**:

> **Blue Team → SOC → DFIR**

Key takeaways:

- Defense is continuous, not reactive  
- Logs are the most valuable asset  
- Detection + response must work together  
- SIEM is central to modern security  
