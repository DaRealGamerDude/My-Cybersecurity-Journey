# TryHackMe: Pre Security (New)

**Path:** Pre Security (New)  
**Platform:** TryHackMe  
**Module Type:** Theory + Hands-on Labs  
**Difficulty:** Beginner  
**Status:** Completed  

---

## 🧾 Executive Summary

The **Pre Security (New)** path expands significantly upon the legacy foundation by integrating deeper technical context, structured security thinking, and practical exposure to both offensive and defensive workflows.

While the Legacy path established system literacy (networking, web protocols, Linux, Windows), the updated path:

- Introduces computer architecture and cloud fundamentals  
- Builds foundational programming awareness (Python, JavaScript, SQL)  
- Integrates cryptography beyond surface-level definitions  
- Provides structured offensive tooling exposure (Gobuster, Hydra)  
- Establishes a defensive mindset aligned with prevention, detection, and analysis  
- Reinforces the CIA triad as a practical incident classification model  

This version transitions from **“how systems work”** to **“how systems are attacked and protected.”**

For a SOC / DFIR trajectory, this path establishes foundational thinking in:

- Infrastructure awareness  
- Authentication attack patterns  
- Log visibility  
- Layered defense  
- Key distribution and encryption mechanisms  
- Operational tooling familiarity  

---

# 📘 Module Overview

The updated path consists of 7 modules:

1. Introduction to Cyber Security  
2. Network Fundamentals  
3. How The Web Works  
4. Computer Fundamentals *(New)*  
5. Operating Systems Basics *(Re-structured & Expanded)*  
6. Software Basics *(New)*  
7. Attacks and Defenses *(Major Expansion)*  

Unlike Legacy, this version integrates:

- Virtualisation & cloud exposure  
- Encoding & data representation  
- Programming fundamentals  
- Cryptographic mechanisms  
- Practical attack simulation  
- Defensive infrastructure mapping  

---

# 🔐 Module 1 – Introduction to Cyber Security

## Core Concepts

- Offensive Security (Red Team)
- Defensive Security (Blue Team)
- Ethical boundaries
- Scope and authorization
- Career pathways

## Analytical Upgrade from Legacy

Legacy introduced these concepts theoretically.

The new path reinforces:

- The necessity of defined scope
- Legal boundaries of testing
- Structured methodology in offensive engagements
- Security as a discipline, not just tool usage

Security is framed as:
- A controlled discipline
- A layered defense model
- A mindset rather than a collection of tools

---

# 🌐 Module 2 – Network Fundamentals

## Core Concepts

- IP addressing (Public vs Private)
- MAC addressing
- Ports and services
- OSI Model
- TCP vs UDP
- Packet encapsulation
- NAT
- DNS

## Security Relevance

Understanding networking enables:

- Identifying lateral movement
- Detecting suspicious outbound connections
- Recognizing port abuse
- Understanding firewall boundaries
- Analyzing packet-level attacks

## Upgrade Context

Content overlaps with Legacy but reinforces:

- Encapsulation flow clarity
- Layer-based attack mapping
- Internet exposure awareness

This strengthens packet-level reasoning needed for SOC analysis.

---

# 🌍 Module 3 – How The Web Works

## Core Concepts

- DNS resolution
- HTTP request/response structure
- Status codes
- Headers
- Cookies
- Frontend vs Backend architecture
- Full request lifecycle

## Security Relevance

Web-based attacks depend on:

- Understanding HTTP structure
- Identifying authentication logic flaws
- Recognizing status code anomalies
- Tracking session cookies

Understanding the full lifecycle:

User → DNS → TCP handshake → HTTP → Server → Response

This is critical for:

- Web log analysis
- Proxy log review
- Identifying brute force attempts
- Recognizing 200 vs 404 enumeration differences

---

# 💻 Module 4 – Computer Fundamentals *(New)*

## Core Concepts

- Inside a computer system
- CPU, RAM, storage
- Client-server architecture
- Virtualisation basics
- Cloud computing fundamentals
- IaaS, PaaS, SaaS
- Public vs Private vs Hybrid cloud

## Analytical Upgrade

This did not exist in Legacy.

This module builds infrastructure awareness:

### Virtualisation
- Hypervisors
- Virtual machines
- Resource isolation

Security implication:
- VM escape risks
- Snapshot abuse
- Misconfigured virtual networks

### Cloud Fundamentals

Service Models:

- IaaS → Infrastructure control
- PaaS → Platform abstraction
- SaaS → Fully managed service

Deployment Models:

- Public cloud
- Private cloud
- Hybrid cloud

Security implications:

- Shared responsibility model
- Misconfigured storage buckets
- Identity & access mismanagement
- Cloud logging importance

For SOC / DFIR:
Understanding cloud models is mandatory in modern incident response.

---

# 🖥 Module 5 – Operating Systems Basics

Re-structured version of Linux & Windows from Legacy.

## Linux CLI Basics

- File navigation
- Permissions
- User context
- Process monitoring
- Service management

Security Implication:

- Investigating auth logs
- Identifying suspicious processes
- Recognizing privilege escalation attempts

## Windows CLI Basics

- User accounts
- Network configuration
- Active connections
- Event Viewer basics
- Firewall awareness

Security Implication:

- Monitoring netstat output
- Identifying abnormal connections
- Reviewing security logs
- Analyzing startup persistence

---

# 🧠 Module 6 – Software Basics *(New)*

## Data Representation

- Binary
- Hexadecimal
- Bytes
- RGB color encoding

Security relevance:

- Packet analysis
- Hash comparisons
- Hex dump analysis
- Log data interpretation

## Data Encoding

- ASCII
- Unicode
- UTF-8
- Encoding schemes

Security implication:

- Log corruption detection
- Encoding bypass attacks
- Input validation awareness

## Python (Basic Demo)

- Variables
- Input handling
- Conditional logic
- Loops

Security implication:

- Automation scripting
- Log parsing
- Basic response scripting

## JavaScript (Basic Demo)

- Input validation
- Regex filtering
- Web input handling

Security implication:

- Client-side validation weaknesses
- Input manipulation risks

## SQL Basics

- SELECT
- WHERE
- ORDER BY
- Basic query logic

Security implication:

- Understanding SQL injection
- Log query reasoning
- SIEM query structuring

---

# 🔥 Module 7 – Attacks and Defenses

## CIA Triad

- Confidentiality
- Integrity
- Availability

Security mindset shift:

Every incident now classified as violation of:

- Unauthorized disclosure
- Unauthorized modification
- Service disruption

This becomes the analytical lens for SOC investigations.

---

## Cryptography Concepts

### Plaintext → Algorithm + Key → Ciphertext

### Symmetric Encryption
- One shared key
- Fast
- Key distribution problem

### Asymmetric Encryption
- Public key
- Private key
- Solves key distribution

### HTTPS Hybrid Model
- Asymmetric handshake
- Symmetric session encryption

Security relevance:

- TLS inspection
- Certificate validation
- MITM attack awareness
- Key compromise implications

---

## Become a Hacker – Offensive Exposure

### Enumeration

Manual:
- Checking hidden endpoints

Automated:
```bash
gobuster dir --url http://target -w wordlist.txt
````

Purpose:

* Directory discovery
* Hidden endpoint exposure

### Dictionary Attack

```bash
hydra -l admin -P passlist.txt target http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect"
```

Concepts learned:

* Authentication abuse
* Weak password exploitation
* Automation speed advantage
* Credential brute forcing

Security implication:

* Importance of strong passwords
* Account lockout mechanisms
* Rate limiting necessity

---

## Become a Defender – Blue Team Exposure

### Infrastructure Mapping

Identified components:

* Employee Devices
* Web Server
* Mail Server
* Firewall
* Internet Boundary

### Defensive Layers

* Antivirus
* Spam filtering
* Firewall rules
* Monitoring
* Traffic filtering

Defensive lifecycle:

* Prevention
* Detection
* Mitigation
* Analysis
* Improvement

SOC Alignment:
This structure mirrors real SOC workflow.

---

# 📊 Legacy vs New – Concept Upgrade Comparison

| Area              | Legacy          | New Upgrade                           |
| ----------------- | --------------- | ------------------------------------- |
| System Basics     | OS + Networking | Added Computer Architecture & Cloud   |
| Programming       | Minimal         | Python, JS, SQL exposure              |
| Crypto            | Surface         | Symmetric, Asymmetric, HTTPS flow     |
| Offensive         | Intro theory    | Gobuster + Hydra hands-on             |
| Defensive         | Basic overview  | Structured prevention/detection model |
| Security Thinking | Conceptual      | Applied incident classification       |

---

# 🧾 Consolidated Command Reference

## 🔹 Core OS Commands (Cross-Platform Comparison)

| Function               | Linux              | Windows CMD / PowerShell |
| ---------------------- | ------------------ | ------------------------ |
| Show current directory | `pwd`              | `cd`                     |
| List files             | `ls`               | `dir`                    |
| Show hidden files      | `ls -la`           | `dir /a`                 |
| Change directory       | `cd`               | `cd`                     |
| Display file contents  | `cat file.txt`     | `type file.txt`          |
| Current user           | `whoami`           | `whoami`                 |
| Hostname               | `hostname`         | `hostname`               |
| Network configuration  | `ip a`             | `ipconfig /all`          |
| Active connections     | `netstat -tulnp`   | `netstat -ano`           |
| Running processes      | `ps aux`           | `tasklist`               |
| Real-time processes    | `top`              | `taskmgr`                |
| Kill process           | `kill PID`         | `taskkill /PID`          |
| Manage services        | `systemctl status` | `sc query`               |
| View logs              | `/var/log/`        | `eventvwr.msc`           |
| Clear screen           | `clear`            | `cls`                    |

---

## 🔹 Offensive Tooling

| Purpose               | Command                                            |
| --------------------- | -------------------------------------------------- |
| Directory enumeration | `gobuster dir --url http://target -w wordlist.txt` |
| Dictionary attack     | `hydra -l user -P wordlist target http-post-form`  |

---

# 🧠 Technical Takeaways

Pre Security (New) establishes:

* Infrastructure awareness
* Web protocol clarity
* Encryption mechanics understanding
* Authentication attack patterns
* Enumeration methodology
* Defensive layering strategy
* Cloud exposure awareness
* Basic scripting logic

Most importantly:

It transitions learning from passive system understanding to active security reasoning.

For SOC / DFIR progression, this path strengthens:

* Incident classification capability
* Log reasoning ability
* Network visibility understanding
* Credential attack recognition
* Defensive control mapping
* Cross-platform system literacy

This marks the shift from “learning systems” to “thinking like a security analyst.”

---
