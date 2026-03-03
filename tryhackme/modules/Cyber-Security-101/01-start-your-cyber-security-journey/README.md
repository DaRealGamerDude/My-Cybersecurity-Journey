# TryHackMe Module: Start Your Cyber Security Journey

**Path:** Cyber Security 101  
**Module Type:** Theory + Light Hands-on  
**Difficulty:** Beginner  
**Status:** Completed  

---

## Summary

This module establishes the research discipline and foundational mindset required to progress in cyber security. While the Offensive and Defensive Security rooms reinforce previously covered fundamentals, the Search Skills room expands practical research, OSINT awareness, vulnerability indexing, and documentation navigation.

Although technically simple, this module builds a critical professional skill: structured information retrieval and validation.

---

## Scope Context

**Reinforces:**
- Offensive Security fundamentals (ethical hacking mindset)
- Defensive Security lifecycle (SOC & Incident Response concepts)

**Introduces / Expands:**
- Structured evaluation of online information
- Advanced search engine operators
- Specialized cyber search engines (Shodan, Censys)
- Threat intelligence platforms (VirusTotal, HIBP)
- CVE indexing & exploit sourcing workflow
- Official technical documentation usage
- Social media as OSINT surface

This module primarily strengthens research capability rather than introducing complex technical depth.

---

## Module Overview

This module contains three rooms:

1. Offensive Security Intro  
2. Defensive Security Intro  
3. Search Skills  

The first two act as reinforcement.  
The third builds structured research and information-validation skills.

---

## Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|-------|------------|--------------|--------|
| 1 | Offensive Security Intro | Ethical Hacking Fundamentals | ✔ |
| 2 | Defensive Security Intro | Blue Team Fundamentals | ✔ |
| 3 | Search Skills | Research & Information Evaluation | ✔ |

---

# Room Notes & Key Learnings

---

# 🔹 Room: Offensive Security Intro

**Room Objective:**  
Reinforce how ethical hackers simulate attacks to identify vulnerabilities.

## Key Concepts Reinforced

- Ethical hacking boundaries
- Authorization requirements
- Vulnerability identification
- Enumeration importance

## Security Relevance

Revisiting this content reinforces:
- How exposed endpoints are discovered
- Why enumeration precedes exploitation
- The offensive mindset required to anticipate attacker behavior

This serves as conceptual reinforcement rather than new technical depth.

---

# 🔹 Room: Defensive Security Intro

**Room Objective:**  
Reinforce defensive security roles and structured incident response methodology.

## Core Concepts Reinforced

- Blue Team responsibilities
- SOC monitoring
- Digital Forensics
- Incident Response lifecycle:
  - Preparation
  - Detection & Analysis
  - Containment
  - Recovery
  - Post-Incident Review

## Security Relevance

This aligns directly with SOC and DFIR progression.

Reinforces:
- Log monitoring discipline
- Detection vs prevention distinction
- Structured incident handling processes

---

# 🔹 Room: Search Skills

**Room Objective:**  
Develop structured research techniques and specialized cyber-security search workflows.

---

## What This Room Covered

---

### 1️⃣ Evaluation of Search Results

Not all online content is authoritative.

Evaluation framework:
- Source credibility
- Evidence & logical reasoning
- Bias detection
- Corroboration across independent sources

Key terminology:
- **Snake Oil** → Fraudulent or bogus cryptographic/security product

### Security Relevance

Critical for:
- Avoiding misinformation
- Validating exploit reliability
- Evaluating tool legitimacy

---

### 2️⃣ Advanced Search Operators

## 🔎 Google Search Operators

| Operator | Function | Example |
|----------|----------|----------|
| `"exact phrase"` | Exact phrase match | `"passive reconnaissance"` |
| `site:` | Restrict to domain | `site:tryhackme.com writeups` |
| `-` | Exclude term | `pyramids -tourism` |
| `filetype:` | Restrict file format | `filetype:pdf cyber warfare report` |

Example from lab:
```
filetype:pdf cyber warfare report
```

### Security Relevance

Used for:
- Discovering exposed documents
- Finding technical reports
- Targeted reconnaissance
- OSINT document hunting

---

### 3️⃣ Specialized Search Engines

---

## 🛰 Shodan

Search engine for internet-connected devices.

Example query:
```
apache 2.4.1
```

Used to:
- Identify exposed services
- Detect outdated software
- Map global exposure

---

## Censys

Focuses on:
- Hosts
- Certificates
- Domains
- Internet assets

Used for:
- Port auditing
- Certificate enumeration
- Infrastructure mapping

---

## VirusTotal

Capabilities:
- File hash lookup
- Multi-engine malware scanning
- Community threat insight

Security Use Case:
- IOC validation
- Malware triage
- Threat enrichment

---

## Have I Been Pwned (HIBP)

Purpose:
- Check email exposure in breaches

Security relevance:
- Credential exposure tracking
- Password reuse risk awareness

---

### 4️⃣ Vulnerabilities & Exploit Research

---

## CVE (Common Vulnerabilities and Exposures)

Standardized format:
```
CVE-YYYY-XXXX
```

Maintained by:
- MITRE

Used for:
- Vulnerability tracking
- Cross-team communication
- Alert correlation

Example:
- CVE-2024-3094 (xz backdoor)

---

## Exploit Database

Provides:
- Public exploit code
- Verified PoCs

Security importance:
- Red team research
- Blue team threat modeling

---

## GitHub

Contains:
- Proof-of-concept scripts
- CVE exploit implementations
- Security tooling

Security implication:
Attack techniques are publicly accessible.

---

### 5️⃣ Technical Documentation

---

## Linux Manual Pages

Command:
```
man <command>
```

Exit manual:
```
q
```

Example:
```
man ip
```

Learned:
- Official documentation is authoritative
- Commands often have overlooked flags

---

## Windows Technical Documentation

Example:
```
netstat -b
```

Displays:
- Executable associated with active connections

---

### 6️⃣ Social Media & News as OSINT

Platforms:
- LinkedIn
- Facebook
- Security news outlets

Security relevance:
- Employee OSINT
- Oversharing risk
- Threat intelligence monitoring
- Credential recovery question exposure

---

# Tools & Resources Introduced

- Google Advanced Search Operators
- Shodan
- Censys
- VirusTotal
- Have I Been Pwned
- CVE Database (MITRE)
- Exploit Database
- GitHub (PoCs)
- Linux `man` pages
- Microsoft Technical Docs

---

# 📌 Commands & Key Terms to Remember

```text
man <command>        # View Linux manual
q                    # Exit manual
netstat -b           # Windows: show executable tied to connections
ss                   # Linux replacement for netstat
cat                  # Stands for "concatenate"
filetype:pdf         # Google file search
site:domain.com      # Restrict search
"exact phrase"       # Exact match search
CVE-YYYY-XXXX        # Vulnerability identifier format
```

---

# Overall Module Reflection

Difficulty: Very Easy  
Conceptual Weight: Foundational Reinforcement  

The majority of the module reinforced previously understood offensive and defensive principles. The primary value lies in formalizing search discipline and introducing specialized cyber security information sources.

Key outcome:

Cyber security professionals must master not only tools and exploits but also structured research, validation, and documentation navigation.

This module strengthens:
- Information validation discipline
- Vulnerability tracking workflow
- Threat intelligence sourcing
- OSINT awareness
- Research efficiency

---
