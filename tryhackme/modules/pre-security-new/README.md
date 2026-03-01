# TryHackMe Module: Pre Security (New)

**Path:** Pre Security (New)  
**Module Type:** Theory + Hands-on Labs  
**Difficulty:** Beginner  
**Status:** Completed  

---

## Executive Summary

The Pre Security (New) path expands upon the Legacy path by integrating computer fundamentals, cloud exposure, cryptography mechanics, software logic, and practical offensive and defensive exercises.

While the Legacy version focused on understanding systems (networking, Linux, Windows, web protocols), the updated version transitions into:

- Applied security mindset (CIA triad as analytical framework)
- Cryptography foundations (symmetric, asymmetric, HTTPS hybrid model)
- Basic automation and scripting exposure
- Offensive enumeration and password attack tooling
- Defensive infrastructure mapping and layered security

This path marks the shift from “how systems work” to “how systems are attacked and protected.”

---

## Module Overview

This learning path is divided into 7 structured sections:

1. Introduction to Cyber Security  
2. Network Fundamentals  
3. How The Web Works  
4. Computer Fundamentals *(New)*  
5. Operating Systems Basics *(Re-structured)*  
6. Software Basics *(New)*  
7. Attacks and Defenses *(Major Upgrade)*  

Each section contains multiple rooms building progressively toward a foundational security mindset. This writeup covers all the new content that was added to this path.

---

## Rooms in This Module (that contained new stuff not previously covered in Pre Security (Legacy)

| Order | Room Name | Primary Focus | Status |
|------|------------|--------------|--------|
| 1 | Offensive Security Intro | Red Team Fundamentals | ✔ |
| 2 | Defensive Security Intro | Blue Team Fundamentals | ✔ |
| 3 | Careers in Cyber | Industry Overview | ✔ |
| 4 | What is Networking? | Network Basics | ✔ |
| 5 | Intro to LAN | Local Networks | ✔ |
| 6 | OSI Model | Layered Model | ✔ |
| 7 | Packets & Frames | Data Transmission | ✔ |
| 8 | Extending Your Network | NAT & Internet | ✔ |
| 9 | DNS in Detail | Domain Resolution | ✔ |
| 10 | HTTP in Detail | Web Protocol | ✔ |
| 11 | How Websites Work | Web Architecture | ✔ |
| 12 | Putting it all together | Request Lifecycle | ✔ |
| 13 | Inside a Computer System | Hardware Basics | ✔ |
| 14 | Computer Types | System Classifications | ✔ |
| 15 | Client-Server Basics | Infrastructure Model | ✔ |
| 16 | Virtualisation Basics | Hypervisors & VMs | ✔ |
| 17 | Cloud Computing Fundamentals | Cloud Models | ✔ |
| 18 | Operating Systems: Introduction | OS Concepts | ✔ |
| 19 | Windows Basics | Windows Overview | ✔ |
| 20 | Linux CLI Basics | Linux Command Line | ✔ |
| 21 | Windows CLI Basics | Windows Command Line | ✔ |
| 22 | Operating System Security | OS Security Controls | ✔ |
| 23 | Data Representation | Binary & Hex | ✔ |
| 24 | Data Encoding | ASCII & Unicode | ✔ |
| 25 | Python: Simple Demo | Programming Logic | ✔ |
| 26 | JavaScript: Simple Demo | Input Handling | ✔ |
| 27 | Database SQL Basics | Query Fundamentals | ✔ |
| 28 | The CIA Triad | Security Pillars | ✔ |
| 29 | Cryptography Concepts | Encryption Models | ✔ |
| 30 | Become a Hacker | Offensive Basics | ✔ |
| 31 | Become a Defender | Defensive Basics | ✔ |

---

# Key Concepts Covered (Module-Level)

- Computer architecture & cloud fundamentals  
- Cross-platform OS literacy  
- Data representation & encoding  
- Programming logic basics  
- SQL querying fundamentals  
- Cryptographic models  
- Enumeration & password attacks  
- Defensive infrastructure mapping  
- CIA triad as analytical framework  

---

# Section-by-Section Breakdown

---

# 🔹 Section 4 – Computer Fundamentals

### Rooms:
- Inside a Computer System  
- Computer Types  
- Client-Server Basics  
- Virtualisation Basics  
- Cloud Computing Fundamentals  

## What This Section Introduced (New vs Legacy)

This section did **not exist in the Legacy path**.

It established infrastructure awareness before security analysis.

### Core Knowledge Gained

- CPU, RAM, storage roles  
- Client vs server responsibilities  
- Hypervisors and virtual machines  
- IaaS, PaaS, SaaS models  
- Public, Private, Hybrid cloud  

### Security Relevance

- Understanding virtual machine isolation  
- Shared responsibility model in cloud  
- Misconfiguration risks  
- Cloud logging importance  
- Server exposure awareness  

For SOC/DFIR:
Cloud awareness is critical for modern investigations.

---

# 🔹 Section 5 – Operating Systems Basics

### Rooms:
- Operating Systems: Introduction  
- Windows Basics  
- Linux CLI Basics  
- Windows CLI Basics  
- Operating System Security  

## Upgrade vs Legacy

Legacy covered Linux & Windows separately in depth.

New path:
- Consolidated fundamentals
- Added CLI exposure for both OSs
- Reinforced cross-platform literacy

### Key Reinforced Areas

- File systems  
- Permissions  
- Processes  
- Services  
- Network inspection  
- Basic OS security controls  

### Security Relevance

- Process anomaly detection  
- Identifying suspicious connections  
- Log awareness  
- Permission abuse recognition  
- Service persistence detection  

---

# 🔹 Section 6 – Software Basics

### Rooms:
- Data Representation  
- Data Encoding  
- Python: Simple Demo  
- JavaScript: Simple Demo  
- Database SQL Basics  

## Major Upgrade from Legacy

Legacy barely covered programming logic.

New path introduced:

- Binary & hexadecimal understanding  
- ASCII vs Unicode encoding  
- Python control flow  
- JavaScript input handling  
- Basic SQL querying  

### Security Relevance

- Understanding hex dumps  
- Encoding bypass risks  
- Log data interpretation  
- Input validation weaknesses  
- SQL injection awareness  
- Query logic parallels SIEM logic  

This section strengthens analytical thinking for DFIR log review.

---

# 🔹 Section 7 – Attacks and Defenses

### Rooms:
- The CIA Triad  
- Cryptography Concepts  
- Become a Hacker  
- Become a Defender  

## Major Conceptual Shift

This section transitions from theory → security mindset.

---

## CIA Triad

- Confidentiality
- Integrity
- Availability

Used as classification framework for incidents.

SOC relevance:
Every alert impacts one of these pillars.

---

## Cryptography Concepts

Covered:

- Plaintext vs Ciphertext  
- Symmetric encryption  
- Asymmetric encryption  
- Key distribution problem  
- HTTPS hybrid model  

Security relevance:

- TLS understanding  
- Certificate validation  
- MITM awareness  
- Key compromise implications  

---

## Become a Hacker

Hands-on exposure:

- Manual endpoint discovery  
- Gobuster directory enumeration  
- Hydra dictionary attack  
- HTTP form brute forcing  
- Weak password exploitation  

### Tools Used

```bash
gobuster dir --url http://target -w wordlist.txt
hydra -l admin -P passlist.txt target http-post-form
```

Key lessons:

- Automation speed
- Authentication weaknesses
- Password hygiene importance
- Status code interpretation (200 vs 404)

---

## Become a Defender

Infrastructure mapping exercise:

Identified:
- Employee devices
- Web server
- Mail server
- Firewall
- Internet boundary

Applied:
- Prevention
- Detection
- Mitigation
- Analysis
- Improvement

This mirrors real SOC workflow.

---

# 🛠️ Tools / Technologies Used

- Gobuster — Directory enumeration  
- Hydra — Password dictionary attacks  
- Linux CLI utilities  
- Windows CMD utilities  
- Basic Python scripting  
- SQL query logic  
- HTTPS certificate inspection  

---

# 📌 Cross-Platform Command Comparison

| Function | Linux | Windows CMD / PowerShell |
|----------|--------|--------------------------|
| Show current directory | `pwd` | `cd` |
| List files | `ls` | `dir` |
| Show hidden files | `ls -la` | `dir /a` |
| Change directory | `cd` | `cd` |
| View file contents | `cat file.txt` | `type file.txt` |
| Current user | `whoami` | `whoami` |
| Hostname | `hostname` | `hostname` |
| Network config | `ip a` | `ipconfig /all` |
| Active connections | `netstat -tulnp` | `netstat -ano` |
| Running processes | `ps aux` | `tasklist` |
| Kill process | `kill PID` | `taskkill /PID` |
| Manage services | `systemctl status` | `sc query` |
| Clear screen | `clear` | `cls` |

---

# Upgrade from Legacy – Summary

| Area | Legacy | New Path Upgrade |
|------|--------|-----------------|
| System Basics | Networking + OS | Added computer architecture |
| Programming | Minimal | Python, JS, SQL |
| Crypto | Surface | Practical models |
| Offensive | Conceptual | Tool-based exposure |
| Defensive | Introductory | Layered defense model |
| Cloud | Not covered | Virtualisation + cloud models |

---

# Final Technical Takeaways

Pre Security (New) establishes:

- Infrastructure awareness
- Cross-platform literacy
- Basic scripting logic
- Encoding clarity
- Cryptographic fundamentals
- Offensive enumeration exposure
- Authentication attack understanding
- Defensive layered thinking

Most importantly, it builds the foundation for:

- SOC analysis
- Threat detection
- Incident classification
- Log reasoning
- Blue Team progression
- Future DFIR skill development
