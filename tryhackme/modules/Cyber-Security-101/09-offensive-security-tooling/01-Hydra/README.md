# TryHackMe Room: Hydra

**Path:** Offensive Security Tooling  
**Module Type:** Hands-on (Password Attacks / Brute Force)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Hydra**, a fast and flexible brute-force tool used to crack login credentials across multiple protocols.

It focuses on:
- Password brute-forcing concepts  
- Hydra command syntax  
- Attacking SSH and web login forms  
- Understanding authentication weaknesses  

Hydra enables:
> **Automated credential attacks against exposed services**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | What Hydra is | ✔ |
| 2 | Using Hydra | Practical attacks | ✔ |

---

# Key Concepts Covered (Module-Level)

- Brute-force attacks  
- Credential stuffing basics  
- Authentication protocols (SSH, HTTP)  
- Wordlists and password security  
- Parallel execution (threads)  
- Web form attack structure  

---

# Room Notes & Task Breakdown

---

## Task 1: Hydra Introduction

**Room Objective:**  
Understand Hydra and its capabilities.

---

### Key Learning

- Hydra = **online password cracking tool**  
- Automates login attempts across:
  - SSH  
  - FTP  
  - HTTP  
  - SMB  
  - Many more protocols  

---

### Supported Protocols

Examples:
- SSH  
- FTP  
- HTTP/HTTPS  
- SMB  
- RDP  
- MySQL  

---

### Key Insight

> Weak passwords = trivial to brute-force

---

### Security Implication

- Default creds (admin:admin) → high risk  
- Short/simple passwords → easily cracked  
- No rate limiting → critical vulnerability  

---

### Common Struggles

- Thinking brute-force = outdated (it’s not)  
- Ignoring password policy importance  
- Not understanding protocol differences  

---

## Task 2: Using Hydra

**Room Objective:**  
Perform brute-force attacks using Hydra.

---

### Key Learning

Hydra syntax depends on:
- Target protocol  
- Username(s)  
- Password list  
- Service configuration  

---

### Basic Command Structure

hydra -l <username> -P <wordlist> <target> <protocol>

---

### Example: FTP Attack

hydra -l user -P passlist.txt ftp://MACHINE_IP

---

### SSH Brute Force

hydra -l <username> -P <wordlist> MACHINE_IP -t 4 ssh

---

### Important Options

| Option | Purpose |
|--------|--------|
| -l | Username |
| -P | Password list |
| -t | Threads (parallel attempts) |

---

### Insight

- More threads = faster attack  
- But too many → detection risk  

---

### Web Form Brute Force (POST)

hydra -l <username> -P <wordlist> MACHINE_IP http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V

---

### Breakdown

| Component | Meaning |
|----------|--------|
| ^USER^ | Replaced with username |
| ^PASS^ | Replaced with password |
| F=incorrect | Failure response indicator |

---

### Key Insight

> Hydra needs **failure condition**, not success

---

### Q1: Molly web password flag?

THM{2673a7dd116de68e85c48ec0b1f2612e}  

**Explanation:**  
Brute-forced web login using `http-post-form`.

---

### Q2: Molly SSH password flag?

THM{c8eeb0468febbadea859baeb33b2541b}  

**Explanation:**  
Used Hydra with SSH protocol and password list.

---

### Common Struggles

- Incorrect form parameters (very common)  
- Not identifying failure message  
- Wrong endpoint path  
- Using wrong protocol (HTTP vs HTTPS)  
- Too many threads → blocked  

---

# Tools / Technologies Used in This Module

- Hydra  
- SSH  
- HTTP POST forms  
- Wordlists (password lists)  

---

# Commands, Syntax & Patterns to Remember

Basic

hydra -l user -P pass.txt <target> <protocol>

SSH

hydra -l user -P pass.txt MACHINE_IP ssh

Web POST

hydra -l user -P pass.txt MACHINE_IP http-post-form "/:username=^USER^&password=^PASS^:F=incorrect"

Threads

-t 4

Verbose

-V

---

# Reflection

This module introduces:

> **credential attacks as a real-world threat**

Key takeaways:

- Authentication = weakest link  
- Brute-force still works on misconfigured systems  
- Web forms require **structure understanding**  
- Automation massively scales attacks  

This directly connects to:

- Password spraying  
- Credential stuffing  
- SOC detection (login anomalies)  
- DFIR analysis (failed login spikes)  
