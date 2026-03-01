# TryHackMe Module: Pre Security (New)

**Path:** Pre Security (New)  
**Module Type:** Theory + Hands-on Labs  
**Difficulty:** Beginner  
**Status:** Completed  

---

## Executive Summary

The Pre Security (New) path significantly expands on the Legacy version by integrating:

- Computer architecture fundamentals  
- Cloud & virtualisation exposure  
- Programming basics (Python, JavaScript, SQL)  
- Applied cryptography concepts  
- Practical offensive tooling (Gobuster, Hydra)  
- Structured defensive security mindset  

While the Legacy path focused on understanding how systems work, the updated version shifts toward understanding:

- How systems are attacked  
- How authentication mechanisms fail  
- How encryption protects data  
- How infrastructure is defended  
- How incidents are classified using the CIA Triad  

This path bridges foundational IT literacy with early SOC / DFIR analytical thinking.

---

## Module Overview

This module teaches foundational cybersecurity from the ground up. It begins with networking and operating systems, expands into software and encoding concepts, and culminates in applied offensive and defensive exercises.

It consists of multiple rooms organized into 7 modules:

1. Introduction to Cyber Security  
2. Network Fundamentals  
3. How The Web Works  
4. Computer Fundamentals  
5. Operating Systems Basics  
6. Software Basics  
7. Attacks and Defenses  

---

## Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|------|------------|--------------|--------|
| 1 | Offensive Security Intro | Red Team Fundamentals | ✔ |
| 2 | Defensive Security Intro | Blue Team Fundamentals | ✔ |
| 3 | Careers in Cyber | Industry Roles | ✔ |
| 4 | What is Networking? | Core Networking Concepts | ✔ |
| 5 | Intro to LAN | Local Area Networks | ✔ |
| 6 | OSI Model | Layered Network Model | ✔ |
| 7 | Packets & Frames | Data Transmission | ✔ |
| 8 | Extending Your Network | NAT & Internet Connectivity | ✔ |
| 9 | DNS in Detail | Domain Resolution | ✔ |
| 10 | HTTP in Detail | Web Protocol Mechanics | ✔ |
| 11 | How Websites Work | Web Architecture | ✔ |
| 12 | Putting It All Together | Full Web Flow | ✔ |
| 13 | Inside a Computer System | Hardware & Processing | ✔ |
| 14 | Computer Types | System Categories | ✔ |
| 15 | Client-Server Basics | Service Architecture | ✔ |
| 16 | Virtualisation Basics | VM & Hypervisors | ✔ |
| 17 | Cloud Computing Fundamentals | Cloud Models | ✔ |
| 18 | Operating Systems: Introduction | OS Concepts | ✔ |
| 19 | Windows Basics | Windows CLI & Structure | ✔ |
| 20 | Linux CLI Basics | Linux Commands | ✔ |
| 21 | Windows CLI Basics | Windows CLI | ✔ |
| 22 | Operating System Security | OS-Level Protection | ✔ |
| 23 | Data Representation | Binary & Hex | ✔ |
| 24 | Data Encoding | ASCII & Unicode | ✔ |
| 25 | Python: Simple Demo | Programming Basics | ✔ |
| 26 | JavaScript: Simple Demo | Input Validation | ✔ |
| 27 | Database SQL Basics | Query Logic | ✔ |
| 28 | The CIA Triad | Security Model | ✔ |
| 29 | Cryptography Concepts | Encryption Fundamentals | ✔ |
| 30 | Become a Hacker | Enumeration & Brute Force | ✔ |
| 31 | Become a Defender | Infrastructure Protection | ✔ |

---

## Key Concepts Covered (Module-Level)

- CIA Triad — Classification of security incidents  
- Symmetric vs Asymmetric Encryption — Key distribution & HTTPS  
- Enumeration & Dictionary Attacks — Authentication abuse  
- Cloud & Virtualisation — Modern infrastructure exposure  
- Data Representation & Encoding — Binary literacy for analysis  
- Cross-platform CLI usage — Linux & Windows parity  
- Prevention, Detection, Mitigation lifecycle  

---

# Room Notes & Task Breakdown

---

## 🔹 Room: Cloud Computing Fundamentals

**Room Objective:**  
Understand cloud service models and deployment models.

### Key Learning:

- IaaS, PaaS, SaaS
- Public vs Private vs Hybrid cloud
- Shared responsibility model

**Security Relevance:**

- Misconfigured cloud storage risks  
- IAM mismanagement  
- Importance of centralized logging in cloud  

**Upgrade from Legacy:**  
Cloud concepts were absent in the Legacy path.

---

## 🔹 Room: Data Representation

**Room Objective:**  
Understand binary, hex, and data storage.

### Key Learning:

- Binary to decimal conversion  
- Hex grouping (4-bit mapping)  
- Bytes = 8 bits  

**Security Relevance:**

- Packet analysis  
- Hash comparisons  
- Log-level interpretation  

---

## 🔹 Room: Data Encoding

**Room Objective:**  
Understand how characters are encoded.

### Key Learning:

- ASCII  
- Unicode  
- UTF-8  

**Security Relevance:**

- Encoding bypass vulnerabilities  
- Log corruption awareness  
- Input sanitization importance  

---

## 🔹 Room: Cryptography Concepts

**Room Objective:**  
Understand encryption fundamentals and HTTPS.

### Key Learning:

- Plaintext vs Ciphertext  
- Algorithm vs Key  
- Symmetric encryption  
- Asymmetric encryption  
- Key distribution problem  
- HTTPS hybrid encryption  

**Important Notes:**

Encryption Process:
plaintext + algorithm + key → ciphertext

HTTPS Flow:
Asymmetric handshake → symmetric session key

**Security Relevance:**

- TLS inspection  
- Certificate validation  
- MITM awareness  

---

## 🔹 Room: Become a Hacker

**Room Objective:**  
Perform basic enumeration and password attacks.

### Task 1: Directory Enumeration

**Tool Used:** Gobuster

```bash
gobuster dir --url http://target -w wordlist.txt
````

Purpose:

* Discover hidden endpoints
* Identify exposed authentication pages

### Task 2: Dictionary Attack

**Tool Used:** Hydra

```bash
hydra -l admin -P passlist.txt target http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect"
```

**Concepts Learned:**

* Weak passwords remain common
* Automation significantly increases attack speed
* Authentication logic weaknesses can be chained

**Security Relevance:**

* Importance of rate limiting
* Account lockout policies
* Password complexity enforcement

---

## 🔹 Room: Become a Defender

**Room Objective:**
Map infrastructure and apply layered defenses.

### Key Learning:

* Infrastructure visibility
* Prevention
* Detection
* Mitigation
* Analysis
* Risk prioritization

Mapped components:

* Employee Devices
* Web Server
* Mail Server
* Firewall
* Internet

Applied controls:

* Antivirus
* Spam filtering
* Firewall rules
* Traffic monitoring

**SOC Alignment:**

This mirrors real-world SOC workflows and layered security models.

---

# Tools / Technologies Used in This Module

* Gobuster — Directory enumeration
* Hydra — Dictionary attack automation
* Linux CLI — System navigation & inspection
* Windows CLI — System inspection
* HTTPS — Secure communication protocol
* Virtualisation — VM isolation
* Cloud service models — Infrastructure abstraction

---

# 📌 Commands, Syntax & Patterns to Remember

## Cross-Platform Command Comparison

| Function              | Linux            | Windows CMD / PowerShell |
| --------------------- | ---------------- | ------------------------ |
| Current directory     | `pwd`            | `cd`                     |
| List files            | `ls`             | `dir`                    |
| Hidden files          | `ls -la`         | `dir /a`                 |
| Change directory      | `cd`             | `cd`                     |
| Show file contents    | `cat file.txt`   | `type file.txt`          |
| Current user          | `whoami`         | `whoami`                 |
| Hostname              | `hostname`       | `hostname`               |
| Network configuration | `ip a`           | `ipconfig /all`          |
| Active connections    | `netstat -tulnp` | `netstat -ano`           |
| Running processes     | `ps aux`         | `tasklist`               |
| Kill process          | `kill PID`       | `taskkill /PID`          |
| Clear screen          | `clear`          | `cls`                    |

---

## Offensive Tooling

```bash
# Directory Enumeration
gobuster dir --url http://target -w wordlist.txt

# Dictionary Attack
hydra -l username -P wordlist target http-post-form
```

---

# Concept Upgrade Comparison (Legacy → New)

| Area                | Legacy          | New                                   |
| ------------------- | --------------- | ------------------------------------- |
| System Fundamentals | OS & Networking | + Computer Architecture               |
| Cloud               | Not covered     | Cloud models & virtualisation         |
| Programming         | Minimal         | Python, JS, SQL exposure              |
| Cryptography        | Surface level   | Symmetric, Asymmetric, HTTPS          |
| Offensive           | Intro theory    | Practical enumeration & brute force   |
| Defensive           | Overview        | Structured prevention/detection model |

---

# Technical Takeaways

Pre Security (New) transitions learning from:

Understanding systems → Thinking like a security analyst.

It builds:

* Infrastructure awareness
* Authentication attack recognition
* Encryption mechanics clarity
* Defensive layering mindset
* Cross-platform operational literacy

For SOC / DFIR progression, this module strengthens:

* Incident classification (CIA model)
* Log reasoning foundations
* Attack chain awareness
* Credential abuse detection
* Cloud exposure awareness
---

```
