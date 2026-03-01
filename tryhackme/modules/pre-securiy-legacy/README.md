 # TryHackMe: Pre Security (Legacy)

**Path:** Pre Security (Legacy)  
**Module Type:** Theory + Hands-on Labs  
**Difficulty:** Beginner  
**Status:** Completed  

---

## Executive Summary

The **Pre Security (Legacy)** path establishes foundational knowledge required to understand modern cybersecurity operations. It provides structured exposure to five core domains:

- Cyber security fundamentals
- Networking principles
- Web technologies
- Linux operating system fundamentals
- Windows operating system fundamentals

The module focuses on understanding how systems function before analyzing how they are attacked or defended. It introduces the CIA triad, networking models, DNS resolution, HTTP protocol mechanics, Linux file systems and permissions, Windows NTFS architecture, system utilities, and built-in security mechanisms.

This path builds technical literacy necessary for further progression into SOC operations, DFIR, threat analysis, and incident response workflows.

---

## Module Overview

The Pre Security (Legacy) path is divided into five structured sections:

1. Introduction to Cyber Security  
2. Network Fundamentals  
3. How The Web Works  
4. Linux Fundamentals  
5. Windows Fundamentals  

Each section contains rooms broken into tasks that combine theory and practical virtual machine interaction.

The primary goal of this module is to ensure:

- Understanding of how data moves across networks  
- Understanding of how operating systems manage users and processes  
- Understanding of how web applications communicate  
- Familiarity with system tools used in real-world environments  

---

## Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|--------|------------|----------------|--------|
| 1 | Offensive Security Intro | Red Team Fundamentals | ✔ |
| 2 | Defensive Security Intro | Blue Team Fundamentals | ✔ |
| 3 | Careers in Cyber | Industry Roles | ✔ |
| 4 | What is Networking? | Core Networking Concepts | ✔ |
| 5 | Intro to LAN | Local Area Networks | ✔ |
| 6 | OSI Model | Layered Network Model | ✔ |
| 7 | Packets & Frames | Data Transmission | ✔ |
| 8 | Extending Your Network | Internet Connectivity | ✔ |
| 9 | DNS in Detail | Domain Resolution | ✔ |
| 10 | HTTP in Detail | Web Protocol | ✔ |
| 11 | How Websites Work | Web Architecture | ✔ |
| 12 | Putting it all together | Web Communication Flow | ✔ |
| 13 | Linux Fundamentals Part 1 | CLI & File System | ✔ |
| 14 | Linux Fundamentals Part 2 | Permissions & SSH | ✔ |
| 15 | Linux Fundamentals Part 3 | Processes & Logs | ✔ |
| 16 | Windows Fundamentals 1 | OS Structure | ✔ |
| 17 | Windows Fundamentals 2 | System Utilities | ✔ |
| 18 | Windows Fundamentals 3 | Windows Security | ✔ |

---

# Section 1 – Introduction to Cyber Security

---

## 🔹 Offensive Security Intro

### Room Objective
Introduce the concept of offensive security and ethical hacking.

### Key Concepts Covered

- Ethical hacking
- Penetration testing
- Vulnerability assessment
- Exploitation
- Authorization and legal boundaries

### Core Understanding

Offensive security simulates attacks on systems to identify vulnerabilities before malicious actors exploit them. Activities include:

- Network scanning
- Exploiting misconfigurations
- Identifying weak authentication mechanisms
- Testing web applications

Ethical constraints are critical. All testing must be authorized.

---

## 🔹 Defensive Security Intro

### Room Objective
Understand defensive security and Blue Team operations.

### Key Concepts Covered

- Monitoring
- Incident response
- Threat detection
- Log analysis
- SIEM systems

### Core Understanding

Defensive security focuses on:

- Monitoring system logs
- Detecting anomalies
- Responding to incidents
- Preventing recurrence

Common Blue Team responsibilities:

- Reviewing authentication logs
- Investigating suspicious IP connections
- Monitoring firewall alerts
- Analyzing endpoint alerts

Defensive operations rely heavily on logs and telemetry.

---

## 🔹 Careers in Cyber

### Room Objective
Explore cybersecurity career paths.

### Roles Introduced

- SOC Analyst
- Penetration Tester
- Security Engineer
- Threat Intelligence Analyst
- DFIR Analyst
- Security Consultant
- Malware Analyst

### Key Insight

Cybersecurity roles broadly fall into:

- Offensive (Red Team)
- Defensive (Blue Team)
- Hybrid (Purple Team)
- Governance, Risk & Compliance (GRC)

---

# Section 2 – Network Fundamentals

---

## 🔹 What is Networking?

### Core Concepts

- IP Address
- Public vs Private IP
- MAC Address
- Router
- Switch
- Port numbers

### IP Address

An IP address uniquely identifies a device on a network.

- Private IP ranges:
  - 10.0.0.0/8
  - 172.16.0.0–172.31.255.255
  - 192.168.0.0/16

Public IP addresses are routable on the internet.

---

## 🔹 Intro to LAN

### LAN (Local Area Network)

A LAN connects devices within a limited area such as:

- Office
- School
- Home

Key components:

- Switches (Layer 2)
- Routers (Layer 3)
- Access points

---

## 🔹 OSI Model

7-Layer Model:

1. Physical – Cables, electrical signals  
2. Data Link – MAC addressing, frames  
3. Network – IP addressing, routing  
4. Transport – TCP/UDP, ports  
5. Session – Session management  
6. Presentation – Encryption, encoding  
7. Application – HTTP, FTP, DNS  

Security analysis often maps attacks to OSI layers.

Example:
- ARP spoofing → Layer 2  
- IP spoofing → Layer 3  
- Port scanning → Layer 4  

---

## 🔹 Packets & Frames

### Encapsulation Process

Data moves down the OSI stack and gets wrapped in headers.

Application data → TCP header → IP header → Frame header

### TCP vs UDP

TCP:
- Connection-oriented
- Reliable
- Uses handshake (3-way handshake)

UDP:
- Connectionless
- Faster
- No reliability guarantee

---

## 🔹 Extending Your Network

### Key Concepts

- NAT (Network Address Translation)
- DNS role
- Internet Service Provider (ISP)

NAT allows multiple private devices to share one public IP.

Routers connect LANs to the internet.

---

# Section 3 – How The Web Works

---

## 🔹 DNS in Detail

### DNS Purpose

Translate domain names into IP addresses.

Example:
example.com → 93.184.216.34

### DNS Record Types

- A – IPv4 address
- AAAA – IPv6 address
- MX – Mail exchange
- CNAME – Canonical name
- TXT – Text record (often used for verification or abused for exfiltration)

### Recursive vs Authoritative

Recursive resolver:
- Queries other DNS servers.

Authoritative server:
- Holds official domain records.

### TTL (Time To Live)

Determines how long DNS responses are cached.

Security relevance:
- Fast-flux malware infrastructure
- Data exfiltration via TXT records
- Domain Generation Algorithms (DGA)

---

## 🔹 HTTP in Detail

### HTTP Structure

Request:

GET /index.html HTTP/1.1
Host: example.com
User-Agent: browser

Response:

HTTP/1.1 200 OK
Content-Type: text/html

### HTTP Methods

- GET – Retrieve data
- POST – Submit data
- PUT – Update data
- DELETE – Remove data

### Status Codes

- 200 – OK
- 301/302 – Redirect
- 401 – Unauthorized
- 403 – Forbidden
- 404 – Not Found
- 500 – Internal Server Error
- 503 – Service Unavailable

### Headers

- Host
- User-Agent
- Cookie
- Set-Cookie
- Content-Type
- Content-Length

HTTP is stateless. Sessions rely on cookies.

---

## 🔹 How Websites Work

### Frontend

- HTML
- CSS
- JavaScript

### Backend

- PHP
- Python
- Node.js
- Database (SQL)

### Supporting Infrastructure

- Load balancers
- CDN (Content Delivery Network)
- WAF (Web Application Firewall)

Security exposure areas:

- Input validation flaws
- Authentication logic
- Misconfigured headers
- Sensitive data exposure

---

## 🔹 Putting It All Together

Full request flow:

1. User enters domain
2. DNS resolves IP
3. TCP handshake occurs
4. HTTP request sent
5. Server processes request
6. Response returned
7. Browser renders page

Understanding this complete lifecycle is critical for analyzing web-based attacks.

---

# Section 4 – Linux Fundamentals

Linux is foundational in cybersecurity. A large percentage of servers, cloud infrastructure, and security tools operate on Linux-based systems.

This section builds command-line literacy and system-level understanding.

---

## 🔹 Linux Fundamentals Part 1 – CLI & File System

### Core Concepts

- Terminal usage
- Directory structure
- File navigation
- Manual pages
- Basic commands

---

### Linux File System Hierarchy

Root directory: `/`

Key directories:

- `/bin` → Essential user binaries
- `/boot` → Boot loader files
- `/dev` → Device files
- `/etc` → Configuration files
- `/home` → User directories
- `/lib` → System libraries
- `/opt` → Optional software
- `/root` → Root user home
- `/tmp` → Temporary files
- `/usr` → User programs
- `/var` → Logs & variable data

Understanding `/etc`, `/var`, and `/home` is especially important for security analysis.

---

### Core Navigation Commands

| Command | Function |
|----------|-----------|
| `pwd` | Print working directory |
| `ls` | List files |
| `ls -la` | Show hidden files & permissions |
| `cd` | Change directory |
| `cat` | Display file contents |
| `clear` | Clear terminal |

Hidden files start with `.`

---

### Manual Pages

`man <command>`

Manual pages provide documentation for commands.

Example:

man ls

---

## 🔹 Linux Fundamentals Part 2 – Permissions & SSH

### Users & Permissions

Linux permission structure:

-rwxr-xr–

Breakdown:
- First character → File type
- Next 3 → Owner permissions
- Next 3 → Group permissions
- Last 3 → Others permissions

Permission meanings:

- r → Read
- w → Write
- x → Execute

---

### Changing Permissions

`chmod`

Example:

chmod 755 script.sh

Numeric breakdown:
- 4 → Read
- 2 → Write
- 1 → Execute

7 = 4+2+1 (rwx)

---

### Ownership

`chown`

Example:

chown user:group file.txt

---

### SSH (Secure Shell)

Used for remote access.

ssh user@ip_address

Security relevance:
- SSH brute-force attacks
- Key-based authentication
- Log analysis via `/var/log/auth.log`

---

## 🔹 Linux Fundamentals Part 3 – Processes & Logs

### Processes

Every running program is a process.

Key commands:

| Command | Function |
|----------|-----------|
| `ps` | List processes |
| `ps aux` | Detailed process list |
| `top` | Real-time process monitoring |
| `kill <PID>` | Terminate process |
| `systemctl` | Manage services |

---

### Services

Managed via:

systemctl status apache2
systemctl start apache2
systemctl stop apache2

Services may auto-start at boot.

Persistence mechanisms often abuse services.

---

### Log Files

Located in `/var/log`

Common logs:

- `/var/log/auth.log` → Authentication logs
- `/var/log/syslog` → System events
- `/var/log/apache2/` → Web logs

Log analysis is critical in SOC and DFIR.

---

# Section 5 – Windows Fundamentals

Windows dominates enterprise environments. Understanding its structure is essential for endpoint monitoring and incident response.

---

## 🔹 Windows Fundamentals 1 – Core OS Structure

---

### Windows Editions

- Home
- Pro
- Server Editions

Pro includes BitLocker (not available in Home).

---

### Desktop & GUI

Key components:

- Start Menu
- Taskbar
- Notification Area
- Action Center

GUI provides user interaction layer over system processes.

---

### NTFS (New Technology File System)

Features:

- File permissions (ACLs)
- Encryption (EFS)
- Journaling
- Alternate Data Streams (ADS)

ADS allows hidden data storage:

file.txt:hiddenstream

Malware may hide payloads in ADS.

---

### System32 Folder

Path:

C:\Windows\System32

Contains critical system files and executables.

Environment variable:

%windir%

System32 is commonly abused in:
- Living Off The Land attacks
- DLL hijacking
- Persistence mechanisms

---

### User Accounts & Groups

Account types:

- Administrator
- Standard User
- Guest

Management tool:

lusrmgr.msc

User profiles located at:

C:\Users<username>

---

### UAC (User Account Control)

Purpose:
Prevent unauthorized privilege escalation.

Security levels:
- Always notify
- Default notify
- Notify without dimming
- Never notify

UAC bypass attempts are common in malware campaigns.

---

### Task Manager

Shortcut:

Ctrl + Shift + Esc

Functions:
- View running processes
- Monitor CPU, Memory
- Startup programs

Critical for:
- Process anomaly detection
- Identifying suspicious executables

---

## 🔹 Windows Fundamentals 2 – System Utilities

---

### MSConfig (System Configuration)

Command:

msconfig

Tabs:
- General
- Boot
- Services
- Startup
- Tools

Startup items may indicate persistence.

---

### Computer Management

Command:

compmgmt.msc

Includes:

- Task Scheduler
- Event Viewer
- Shared Folders
- Device Manager
- Services

---

### Task Scheduler

Persistence method:
Malware creates scheduled tasks.

Investigate triggers:
- At startup
- At logon
- Specific time

---

### Event Viewer

Command:

eventvwr.msc

Log categories:

- Application
- Security
- System
- Setup
- Forwarded Events

Security log is essential for:
- Logon attempts
- Privilege escalation
- Account modifications

---

### Resource Monitor

Command:

resmon.exe

Monitors:
- CPU
- Memory
- Disk
- Network

Useful for identifying:
- Beaconing malware
- Resource spikes

---

### Command Prompt

Commands:

| Command | Purpose |
|----------|-----------|
| `hostname` | Machine name |
| `whoami` | Current user |
| `ipconfig` | Network config |
| `ipconfig /all` | Detailed config |
| `netstat -ano` | Active connections |
| `net user` | User accounts |
| `cls` | Clear screen |

Netstat reveals C2 communication attempts.

---

### System Information

Command:

msinfo32.exe

Displays:
- Hardware
- Components
- Software environment
- Environment variables

Example variable:

ComSpec = %SystemRoot%\system32\cmd.exe

---

## 🔹 Windows Fundamentals 3 – Security Mechanisms

---

### Windows Update

Command:

control /name Microsoft.WindowsUpdate

Patch Tuesday releases.

Unpatched systems are high-risk.

---

### Windows Security

Protection areas:

- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

Status indicators:
- Green → Protected
- Yellow → Warning
- Red → Immediate action required

---

### Microsoft Defender

Features:

- Real-time protection
- Cloud-delivered protection
- Controlled folder access
- Exclusions list
- Threat history

Security concern:
Defender exclusions can hide malware.

---

### Firewall

Host-based firewall.
Controls inbound/outbound traffic.

Misconfigurations can allow lateral movement.

---

### TPM (Trusted Platform Module)

Hardware crypto-processor.

Used for:
- BitLocker
- Secure boot

Provides hardware-based protection.

---

### BitLocker

Full disk encryption.

Without TPM:
Requires startup key.

Protects data at rest.

---

### Volume Shadow Copy Service (VSS)

Creates restore snapshots.

Command often abused by ransomware:

vssadmin delete shadows

Deleting shadow copies prevents recovery.

---

# Consolidated Command Reference

## Linux

- pwd
- ls -la
- chmod
- chown
- ssh
- ps aux
- top
- systemctl
- cat

## Windows

- taskmgr
- msconfig
- compmgmt.msc
- eventvwr.msc
- resmon.exe
- msinfo32.exe
- control.exe
- ipconfig /all
- netstat -ano
- net user

---

# Technical Takeaways

Pre Security (Legacy) established:

- Networking literacy (OSI, TCP/IP, DNS, HTTP)
- Web request lifecycle understanding
- Linux CLI competence
- Windows system familiarity
- Endpoint security awareness
- Log analysis exposure
- Process monitoring fundamentals

The module focused on understanding how systems function before progressing to exploitation or advanced detection.

This foundational understanding supports further study in:

- SOC analysis
- Threat detection
- Incident response
- Forensics
- Vulnerability research
