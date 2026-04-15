# TryHackMe Room: SOC Fundamentals

**Path:** Defensive Security  
**Module Type:** Concept + Practical (SOC Operations)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces the **Security Operations Center (SOC)** and how it functions using the three pillars:

- People  
- Process  
- Technology  

It focuses on:
- Detection & Response  
- Alert triage  
- SOC roles & responsibilities  
- Real-world SOC workflow  

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | SOC fundamentals | ✔ |
| 2 | Purpose & Components | Detection & response | ✔ |
| 3 | People | SOC roles | ✔ |
| 4 | Process | Alert triage & workflow | ✔ |
| 5 | Technology | Security tools | ✔ |
| 6 | Practical | SOC investigation | ✔ |
| 7 | Conclusion | Recap | ✔ |

---

# Key Concepts Covered

- SOC architecture  
- Detection vs Response  
- Alert triage (5 Ws)  
- SOC hierarchy (L1 → L3)  
- SIEM / EDR / Firewall roles  
- Real-world alert investigation  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction to SOC

**Room Objective:**  
Understand what a SOC is and why it exists.

---

### Q1: What does SOC stand for?

`Security Operations Center`

**Explanation:**  
A dedicated team that monitors and protects organizational systems 24/7.

---

### Key Learning

- SOC monitors:
  - Networks  
  - Systems  
  - Security events  

---

### Insight

> SOC = continuous monitoring + rapid response

---

### Common Struggles

- Thinking SOC = tool (it’s a team + system)  
- Ignoring 24/7 operational nature  

---

## Task 2: Purpose & Components

**Room Objective:**  
Understand SOC’s core function.

---

### Q1: Unauthorized login detection → which capability?

`Detection`

**Explanation:**  
Identifying suspicious or unauthorized activity.

---

### Q2: Three SOC pillars?

`People, Process, Technology`

**Explanation:**  
All three are required for a mature SOC.

---

### Key Learning

SOC focuses on:

- Detect vulnerabilities  
- Detect unauthorized activity  
- Detect policy violations  
- Detect intrusions  
- Support incident response  

---

### Insight

> Detection without response = failure

---

### Common Struggles

- Mixing vulnerability management with SOC  
- Not understanding detection vs response  

---

## Task 3: People (SOC Roles)

**Room Objective:**  
Understand SOC team structure.

---

### Q1: Who performs alert triage?

`SOC Analyst (Level 1)`

**Explanation:**  
First responders to alerts.

---

### Q2: Who builds detection rules?

`Detection Engineer`

**Explanation:**  
Creates logic for identifying threats.

---

### SOC Hierarchy

| Role | Responsibility |
|------|---------------|
| L1 Analyst | Alert triage |
| L2 Analyst | Deep investigation |
| L3 Analyst | Threat hunting + IR |
| Security Engineer | Tool deployment |
| Detection Engineer | Rule creation |
| SOC Manager | Oversight |

---

### Insight

> L1 = filter noise, L2 = analyze, L3 = hunt/respond

---

### Common Struggles

- Underestimating L1 role  
- Not understanding escalation flow  

---

## Task 4: Process (SOC Workflow)

**Room Objective:**  
Understand how alerts are handled.

---

### Q1: Insider data theft → which W?

`Who`

**Explanation:**  
Identifies the actor.

---

### Q2: Data exfiltration → which W?

`What`

**Explanation:**  
Describes the activity.

---

### Alert Triage (5 Ws)

| W | Purpose |
|--|--------|
| What | Activity |
| When | Time |
| Where | Location |
| Who | Actor |
| Why | Reason |

---

### Example

Malware detected on host:

- What → Malicious file  
- When → Timestamp  
- Where → Host  
- Who → User  
- Why → Root cause  

---

### Insight

> 5 Ws = structured investigation mindset

---

### Common Struggles

- Skipping structured analysis  
- Jumping to conclusions  

---

## Task 5: Technology

**Room Objective:**  
Understand tools used in SOC.

---

### Q1: Tool monitoring network traffic?

`Firewall`

**Explanation:**  
Controls incoming/outgoing traffic.

---

### Q2: Does SIEM focus on detection?

`yea`

**Explanation:**  
SIEM primarily detects and alerts.

---

### Key Technologies

| Tool | Function |
|------|---------|
| SIEM | Log collection + detection |
| EDR | Endpoint monitoring + response |
| Firewall | Network filtering |
| IDS/IPS | Intrusion detection/prevention |

---

### Insight

> SIEM = detection, EDR = response

---

### Common Struggles

- Thinking SIEM does response  
- Ignoring correlation logic  

---

## Task 6: Practical SOC Investigation

**Room Objective:**  
Apply SOC workflow to real alert.

---

### Scenario

Alert: Port scanning activity detected

---

### Answers

---

### Q1: What?

`Port Scan`

**Explanation:**  
Detected suspicious network scanning.

---

### Q2: When?

`June 12, 2024 17:24`

**Explanation:**  
Timestamp from logs.

---

### Q3: Where?

`10.0.0.3`

**Explanation:**  
Target host.

---

### Q4: Who?

`Nessus`

**Explanation:**  
Source host (scanner tool).

---

### Q5: Why?

`Intended`

**Explanation:**  
Legitimate vulnerability scan.

---

### Q6: Response sent?

`yea`

**Explanation:**  
System responded to scan.

---

### Q7: Flag?

`THM{000_INTRO_TO_SOC}`

**Explanation:**  
Final validation after investigation.

---

### Insight

> Not all alerts = malicious (context matters)

---

### Common Struggles

- Treating all alerts as attacks  
- Ignoring context (e.g., Nessus scan)  
- Not correlating logs  

---

## Task 7: Conclusion

- SOC relies on:
  - People  
  - Process  
  - Technology  

---

# Tools / Technologies Introduced

- SIEM  
- EDR  
- Firewall  
- Vulnerability scanners (Nessus)  

---

# SOC Workflow Cheat Sheet

1. Alert generated  
2. L1 triage (5 Ws)  
3. Escalation (if needed)  
4. Investigation (L2/L3)  
5. Response  
6. Documentation  

---

# Reflection

This module is **directly aligned with your career path**:

> **SOC → Threat Analysis → DFIR**

Key takeaways:

- SOC is process-driven, not tool-driven  
- Alert triage is foundational  
- Context determines severity  
- Detection + response must work together

→ Deep dive into:
- SIEM (Splunk)  
- Log analysis  
- Detection engineering  
