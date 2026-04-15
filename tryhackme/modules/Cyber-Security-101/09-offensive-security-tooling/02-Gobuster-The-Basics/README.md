# TryHackMe Room: Gobuster: The Basics

**Path:** Offensive Security Tooling  
**Module Type:** Hands-on (Enumeration / Recon)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Gobuster**, a fast enumeration tool used to discover:

- Hidden directories & files  
- Subdomains  
- Virtual hosts  

It focuses on:
- Brute-force based enumeration  
- Wordlist-driven discovery  
- Understanding web infrastructure  

> Gobuster sits between **Reconnaissance → Scanning phase** in pentesting :contentReference[oaicite:0]{index=0}  

---

# Rooms in This Module

| Order | Section | Focus | Status |
|------|--------|------|--------|
| 1 | Introduction | Enumeration basics | ✔ |
| 2 | Setup | Environment config | ✔ |
| 3 | Gobuster Intro | Tool + syntax | ✔ |
| 4 | Dir Mode | Directories & files | ✔ |
| 5 | DNS Mode | Subdomains | ✔ |
| 6 | VHost Mode | Virtual hosts | ✔ |
| 7 | Conclusion | Recap | ✔ |

---

# Key Concepts Covered

- Enumeration vs Brute Force  
- Wordlists & attack surface discovery  
- Directory discovery  
- DNS subdomain enumeration  
- Virtual host discovery  
- HTTP response analysis  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Objective:**  
Understand what Gobuster is used for.

---

### Key Learning

- Gobuster = **enumeration tool using brute force**
- Used in:
  - Pentesting  
  - Bug bounty  
  - Recon  

---

### Insight

> You don’t hack what you don’t know exists

---

### Common Struggles

- Underestimating enumeration  
- Jumping straight to exploitation  
- Ignoring hidden endpoints  

---

## Task 2: Environment Setup

**Objective:**  
Prepare environment for enumeration.

---

### Key Learning

- DNS resolution required for subdomains  
- Configured via `/etc/resolv-dnsmasq`  

---

### Insight

> Enumeration fails silently if DNS is broken

---

### Common Struggles

- Forgetting DNS setup  
- Misconfigured resolver  
- Assuming tool is broken  

---

## Task 3: Gobuster Introduction

**Objective:**  
Understand Gobuster commands and modes.

---

### Key Learning

Gobuster modes:
- `dir` → directories/files  
- `dns` → subdomains  
- `vhost` → virtual hosts  

---

### Important Flags

| Flag | Purpose |
|------|--------|
| -u | Target URL |
| -w | Wordlist |
| -t | Threads |
| -o | Output file |

---

### Q1: Target URL flag?

`-u`  

**Explanation:**  
Specifies the base URL for enumeration.

---

### Q2: Subdomain mode command?

`dns`  

**Explanation:**  
Used for DNS-based enumeration.

---

### Insight

> Wordlist quality > tool power

---

### Common Struggles

- Using wrong mode  
- Bad wordlists  
- Not tuning threads  

---

## Task 4: Directory & File Enumeration

**Objective:**  
Discover hidden directories and files.

---

### Command

gobuster dir -u http://target -w wordlist.txt

---

### Key Flags

| Flag | Purpose |
|------|--------|
| -x | File extensions |
| -r | Follow redirects |
| --no-tls-validation | Skip TLS check |

---

### Q1: Skip TLS verification flag?

`--no-tls-validation`  

**Explanation:**  
Used when HTTPS cert is invalid/self-signed.

---

### Q2: Interesting directory?

`secret`  

**Explanation:**  
Found via directory brute-force.

---

### Q3: Flag in JS file?

`THM{ReconWasASuccess}`  

**Explanation:**  
Hidden file discovered inside enumerated directory.

---

### Insight

> Hidden directories = biggest attack surface

---

### Common Struggles

- Not checking discovered directories recursively  
- Ignoring status codes  
- Missing file extensions  

---

## Task 5: Subdomain Enumeration

**Objective:**  
Discover subdomains via DNS brute force.

---

### Command

gobuster dns -d domain.thm -w wordlist.txt

---

### Key Flags

| Flag | Purpose |
|------|--------|
| -d | Domain |
| -i | Show IPs |
| -r | Custom resolver |

---

### Q1: Required shorthand flag?

`-d`  

**Explanation:**  
Defines target domain.

---

### Q2: Number of subdomains?

`4`  

**Explanation:**  
Found via DNS enumeration.

---

### Insight

> Subdomains often have weaker security than main domain

---

### Common Struggles

- DNS misconfiguration  
- Using wrong wordlists  
- Not verifying results  

---

## Task 6: VHost Enumeration

**Objective:**  
Discover virtual hosts on same server.

---

### Command

gobuster vhost -u http://IP -w wordlist.txt --domain domain.thm --append-domain

---

### Key Concept

- **VHosts ≠ Subdomains**
  - VHosts → server-side  
  - Subdomains → DNS  

---

### Q1: Number of valid vhosts (200 OK)?

`4`  

**Explanation:**  
Filtered valid responses using status codes.

---

### Insight

> Same IP ≠ Same application

---

### Common Struggles

- Confusing vhost vs subdomain  
- Not filtering false positives  
- Ignoring response size filtering  

---

## Task 7: Conclusion

- Learned all 3 modes:
  - dir  
  - dns  
  - vhost  
- Applied real enumeration techniques  

---

# Tools Used

- Gobuster  
- Wordlists (SecLists, dirbuster)  
- HTTP/DNS  

---

# Commands Cheat Sheet

Directory

gobuster dir -u http://target -w wordlist.txt

With extensions

gobuster dir -u http://target -w wordlist.txt -x php,js

Subdomains

gobuster dns -d domain.thm -w wordlist.txt

VHosts

gobuster vhost -u http://IP -w wordlist.txt --domain domain.thm --append-domain

---

# Reflection

This module builds:

> **Discovery before exploitation mindset**

Key takeaways:

- Enumeration = most important phase  
- Hidden endpoints = real vulnerabilities  
- Wordlists drive success  
- Automation scales recon  

From a **Blue Team / SOC POV**:

- High request spikes → detection signal  
- Enumeration patterns → alert indicators  
- Directory brute-force → log anomalies  
