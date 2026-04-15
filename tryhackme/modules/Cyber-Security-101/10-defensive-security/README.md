# TryHackMe Module: Start Your Cyber Security Journey

**Path:** Cyber Security 101  
**Module Type:** Foundational (Concept + Hands-on)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This module introduces the **core domains of cybersecurity**:

- Offensive Security (Attacking systems)
- Defensive Security (Protecting systems)
- Search Skills (Finding information effectively)

It provides:
- First hands-on hacking experience  
- Introduction to SOC & DFIR  
- Research & OSINT fundamentals  

---

# Rooms in This Module

| Order | Room | Focus | Status |
|------|------|------|--------|
| 1 | Offensive Security Intro | Basic exploitation | ✔ |
| 2 | Defensive Security Intro | Blue team fundamentals | ✔ |
| 3 | Search Skills | Research & OSINT | ✔ |

---

# Key Concepts Covered (Module-Level)

- Ethical hacking fundamentals  
- Web enumeration basics  
- SOC operations  
- Digital forensics basics  
- Incident response lifecycle  
- OSINT & search techniques  
- Technical documentation usage  

---

# Room Notes & Breakdown

---

# 1. Offensive Security Intro

**Room Objective:**  
Understand how attackers think and perform basic exploitation.

---

## Task 1: What is Offensive Security?

### Q: Simulating hacker actions?

`Offensive Security`

**Explanation:**  
Involves attacking systems to find vulnerabilities.

---

### Key Learning

- Think like an attacker  
- Exploitation reveals weaknesses  
- Ethical hacking improves defense  

---

### Insight

> “To defend systems, you must understand how they are attacked.”

---

### Common Struggles

- Confusing ethical vs malicious hacking  
- Not understanding purpose of exploitation  

---

## Task 2: Lab Setup

### Q: Bank account number?

`8881`

**Explanation:**  
Provided test credential in FakeBank lab.

---

### Key Learning

- Labs simulate real environments  
- Safe to experiment freely  

---

## Task 3: Your First Hack

### Command Used

dirb http://fakebank.thm

---

### Q: Hidden URL?

`http://fakebank.thm/bank-deposit`

**Explanation:**  
Discovered via directory brute-forcing.

---

### Key Learning

- Enumeration = first step in hacking  
- Hidden endpoints expose functionality  

---

### Insight

> Attackers don’t guess — they enumerate

---

### Common Struggles

- Not understanding wordlists  
- Ignoring enumeration phase  

---

## Task 4: Exploitation

### Q: Final flag?

`BANK-HACKED`

**Explanation:**  
Used hidden endpoint to manipulate balance.

---

### Key Learning

- Exploitation uses discovered weaknesses  
- Business logic flaws can be abused  

---

### Common Struggles

- Not connecting enumeration → exploitation  
- Missing simple attack paths  

---

# 2. Defensive Security Intro

**Room Objective:**  
Understand how organizations defend against attacks.

---

## Task 1: Defensive Security Basics

### Q: Which team handles defense?

`Blue Team`

**Explanation:**  
Responsible for protection and monitoring.

---

### Key Learning

- Two main goals:
  - Prevent attacks  
  - Detect & respond  

---

### Key Areas

- Awareness training  
- Asset management  
- Firewalls & IPS  
- Logging & monitoring  

---

## Task 2: Security Operations Centre (SOC)

### Q: Team monitoring systems?

`Security Operations Centre`

**Explanation:**  
SOC monitors, detects, and responds to threats.

---

### Key Learning

- SOC focuses on:
  - Alerts  
  - Anomalies  
  - Policy violations  

---

### Insight

> SOC = frontline defense

---

### Common Struggles

- Not understanding SOC workflow  
- Ignoring logs importance  

---

## Task 3: Digital Forensics

### Q: Malware running only in memory?

`System Memory`

**Explanation:**  
Memory forensics detects fileless malware.

---

### Key Learning

- Evidence sources:
  - Disk  
  - Memory  
  - Logs  
  - Network  

---

### Insight

> Attackers leave traces — even if hidden

---

## Task 4: Incident Response

### Q: Phase for training?

`Preparation`

**Explanation:**  
Includes awareness and readiness.

---

### Incident Response Phases

| Phase | Purpose |
|------|--------|
| Preparation | Readiness |
| Detection | Identify threats |
| Containment | Limit damage |
| Recovery | Restore systems |
| Review | Improve process |

---

### Key Learning

- Structured response reduces damage  

---

### Common Struggles

- Not understanding lifecycle  
- Treating incidents reactively  

---

## Task 5: Practical SOC Simulation

### Q: Flag?

`THREAT-BLOCKED`

**Explanation:**  
Identified malicious activity via SIEM.

---

### Key Learning

- SIEM aggregates logs  
- Alerts indicate suspicious behavior  

---

### Insight

> Detection = pattern recognition

---

# 3. Search Skills

**Room Objective:**  
Develop efficient research and OSINT skills.

---

## Task 2: Evaluating Sources

### Q1: Fake crypto/security product?

`Snake oil`

**Explanation:**  
Fraudulent or ineffective solutions.

---

### Q2: Replacement for netstat?

`ss`

**Explanation:**  
Modern Linux networking tool.

---

### Key Learning

- Evaluate:
  - Source credibility  
  - Evidence  
  - Bias  

---

### Common Struggles

- Trusting random blogs  
- Not verifying info  

---

## Task 3: Search Engines

### Q1: Limit to PDFs?

`filetype:pdf cyber warfare report`

---

### Q2: ss stands for?

`socket statistics`

---

### Key Learning

- Use operators:
  - "exact phrase"  
  - site:  
  - filetype:  
  - -exclude  

---

### Insight

> Better queries = better results

---

## Task 4: Specialized Search Engines

### Q1: Top country (lighttpd)?

`United States`

---

### Q2: Malware detection?

`Android.Riskware.Agent.LHH`

---

### Tools Covered

- Shodan  
- Censys  
- VirusTotal  
- HaveIBeenPwned  

---

### Key Learning

- OSINT tools reveal:
  - Exposed systems  
  - Breaches  
  - Malware  

---

## Task 5: Vulnerabilities & Exploits

### Q: CVE-2024-3094 affects?

`xz`

---

### Key Learning

- CVE = vulnerability identifier  
- Exploit DB = exploit source  

---

### Insight

> Vulnerability ≠ exploit (but often linked)

---

## Task 6: Technical Documentation

### Q1: cat stands for?

`concatenate`

---

### Q2: netstat flag for executable?

`-b`

---

### Key Learning

- Official docs = most reliable source  

---

## Task 7: Social Media

### Q1: Professional background?

`LinkedIn`

---

### Q2: Personal info (security questions)?

`Facebook`

---

### Key Learning

- Social media = OSINT goldmine  
- Risk of oversharing  

---

### Insight

> Humans = weakest security layer

---

# Tools & Technologies Used

- Dirb (enumeration)  
- SIEM (simulation)  
- Search engines (Google, etc.)  
- OSINT tools (Shodan, VirusTotal)  

---

# Commands & Patterns

Directory enumeration

dirb http://target

Google search operators

filetype:pdf  
site:example.com  
"exact phrase"  

---

# Reflection

This module builds the **foundation of cybersecurity**:

> Attack → Defend → Investigate → Research

Key takeaways:

- Offensive teaches how attacks work  
- Defensive teaches how to detect/respond  
- Search skills enable continuous learning
