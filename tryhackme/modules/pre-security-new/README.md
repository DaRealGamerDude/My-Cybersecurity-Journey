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

### Rooms Covered:
- Inside a Computer System
- Computer Types
- Client-Server Basics
- Virtualisation Basics
- Cloud Computing Fundamentals

---

## Section Overview

This section introduced foundational infrastructure knowledge that was not present in the Legacy path. Instead of jumping directly into operating systems, this module focused on how computers function internally and how modern infrastructure is structured.

---

## What I Learned from Each Room

### Inside a Computer System

**Focus:**
- CPU, RAM, storage roles
- Input/output devices
- How data flows through hardware

**Key Learning:**
- CPU executes instructions.
- RAM stores temporary working data.
- Storage retains persistent data.
- Performance bottlenecks often stem from resource limitations.

**Security Relevance:**
Understanding system internals is critical when analyzing:
- Memory-based malware
- Disk artifacts in forensics
- Resource exhaustion attacks

---

### Computer Types

**Focus:**
- Desktops, servers, embedded systems
- Differences between personal and enterprise systems

**Key Learning:**
- Servers prioritize availability and reliability.
- Embedded systems may lack security hardening.
- Infrastructure diversity affects attack surface.

**Security Relevance:**
Different device classes require different security strategies.

---

### Client-Server Basics

**Focus:**
- Client requests
- Server responses
- Centralized service architecture

**Key Learning:**
- Servers host resources.
- Clients consume services.
- Authentication and authorization typically occur server-side.

**Security Relevance:**
Most attacks target the server side.
Understanding this model helps in:
- Log correlation
- Identifying lateral movement
- Authentication abuse detection

---

### Virtualisation Basics

**Focus:**
- Hypervisors
- Virtual machines
- Resource abstraction

**Key Learning:**
- Type 1 vs Type 2 hypervisors
- Multiple VMs can run on one physical host
- Isolation depends on hypervisor security

**Security Relevance:**
- VM escape risks
- Snapshot misuse
- Virtual network misconfiguration

---

### Cloud Computing Fundamentals

**Focus:**
- IaaS, PaaS, SaaS
- Public vs Private vs Hybrid cloud

**Key Learning:**
- Shared responsibility model
- Cloud misconfiguration is a major risk
- Identity management is critical in cloud environments

**Security Relevance:**
Modern SOC & DFIR investigations often involve:
- Cloud audit logs
- Identity misuse
- Misconfigured storage buckets

---

# 🔹 Section 5 – Operating Systems Basics

### Rooms Covered:
- Operating Systems: Introduction
- Windows Basics
- Linux CLI Basics
- Windows CLI Basics
- Operating System Security

---

## Section Overview

This section consolidated OS fundamentals from the Legacy path but reinforced command-line literacy and security mechanisms more explicitly.

---

## What I Learned from Each Room

### Operating Systems: Introduction

**Focus:**
- Kernel vs user space
- Process management
- Memory handling

**Key Learning:**
- OS manages hardware resources.
- Processes run in isolation.
- Access control is enforced by OS permissions.

**Security Relevance:**
OS structure understanding is essential for:
- Privilege escalation analysis
- Process injection detection

---

### Windows Basics

**Focus:**
- File system (NTFS)
- User accounts
- System utilities

**Key Learning:**
- ACL-based permissions
- User roles and privilege levels
- Importance of Windows Event Logs

**Security Relevance:**
Enterprise environments heavily rely on Windows.
Event logs are central to investigations.

---

### Linux CLI Basics

**Focus:**
- File navigation
- Permissions
- Process inspection

**Key Learning:**
- File permission model (rwx)
- Ownership management
- Process visibility using CLI

**Security Relevance:**
Linux servers dominate cloud infrastructure.
CLI fluency is required for incident analysis.

---

### Windows CLI Basics

**Focus:**
- Command prompt usage
- Network inspection
- Process monitoring

**Key Learning:**
- `ipconfig`, `netstat`, `tasklist`
- Identifying active connections
- Understanding service states

**Security Relevance:**
Critical for:
- Detecting beaconing
- Identifying suspicious processes

---

### Operating System Security

**Focus:**
- Firewalls
- Antivirus
- OS hardening

**Key Learning:**
- Importance of patching
- Host-based firewall controls
- Built-in OS protections

**Security Relevance:**
Defense starts at endpoint level.

---

# 🔹 Section 6 – Software Basics

### Rooms Covered:
- Data Representation
- Data Encoding
- Python: Simple Demo
- JavaScript: Simple Demo
- Database SQL Basics

---

## Section Overview

This section introduced logical thinking and data-level awareness not deeply covered in Legacy.

---

## What I Learned from Each Room

### Data Representation

**Focus:**
- Binary
- Hexadecimal
- Bytes

**Key Learning:**
- 8 bits = 1 byte
- Hex simplifies binary
- Color encoding (RGB)

**Security Relevance:**
- Packet inspection
- Hash comparison
- Hex dump reading

---

### Data Encoding

**Focus:**
- ASCII
- Unicode
- UTF-8

**Key Learning:**
- Encoding defines character mapping
- Unicode solves multi-language limitations

**Security Relevance:**
- Encoding bypass attacks
- Log corruption detection

---

### Python: Simple Demo

**Focus:**
- Variables
- Loops
- Conditionals

**Key Learning:**
- Control flow logic
- Input validation basics

**Security Relevance:**
Foundation for:
- Log parsing
- Automation scripts

---

### JavaScript: Simple Demo

**Focus:**
- Web input handling
- Basic validation

**Key Learning:**
- Client-side validation is not secure
- Regex filtering basics

**Security Relevance:**
Understanding:
- Input manipulation
- Web-based attack vectors

---

### Database SQL Basics

**Focus:**
- SELECT
- WHERE
- ORDER BY

**Key Learning:**
- Query filtering logic
- Structured data retrieval

**Security Relevance:**
- SQL injection awareness
- SIEM query logic parallels

---

# 🔹 Section 7 – Attacks and Defenses

### Rooms Covered:
- The CIA Triad
- Cryptography Concepts
- Become a Hacker
- Become a Defender

---

## Section Overview

This section marked the transition from theory to applied security thinking.

---

## What I Learned from Each Room

### The CIA Triad

**Focus:**
- Confidentiality
- Integrity
- Availability

**Key Learning:**
Every security incident impacts one of these pillars.

**Security Relevance:**
Forms the foundation of incident classification.

---

### Cryptography Concepts

**Focus:**
- Symmetric encryption
- Asymmetric encryption
- HTTPS handshake
- Key distribution problem

**Key Learning:**
- Public vs private keys
- Hybrid encryption model
- Certificates and trust chains

**Security Relevance:**
- TLS inspection
- Certificate validation
- MITM awareness

---

### Become a Hacker

**Focus:**
- Enumeration
- Directory discovery
- Dictionary attacks

**Tools Used:**
```bash
gobuster dir --url http://target -w wordlist.txt
hydra -l admin -P passlist.txt target http-post-form
```

**Key Learning:**
- Automation speed advantage
- Weak password risks
- Endpoint exposure

---

### Become a Defender

**Focus:**
- Infrastructure mapping
- Prevention vs detection
- Layered security

**Key Learning:**
- Identify assets
- Apply security controls
- Monitor and respond

**SOC Alignment:**
Mirrors real-world blue team workflows.

---

# Tools / Technologies Used

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
