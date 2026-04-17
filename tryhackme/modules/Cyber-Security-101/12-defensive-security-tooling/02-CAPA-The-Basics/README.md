# TryHackMe Room: CAPA: The Basics

**Path:** Defensive Security Tooling  
**Module Type:** Malware Analysis (Static Analysis)  
**Difficulty:** Beginner–Intermediate  
**Status:** Completed  

---

# Summary

This room introduces **CAPA**, a static malware analysis tool used to identify **capabilities of executables**.

It covers:
- Static vs Dynamic analysis  
- CAPA usage & workflow  
- Interpreting CAPA outputs  
- MITRE ATT&CK + MAEC mapping  
- Malware Behavior Catalogue (MBC)  
- Capabilities, Namespaces, and Rules  

> CAPA = **Automated reverse engineering knowledge**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Intro | Static analysis + CAPA | ✔ |
| 2 | Tool Usage | Running CAPA | ✔ |
| 3 | Results Part 1 | Hashes + MITRE + MAEC | ✔ |
| 4 | Results Part 2 | MBC (Behavior) | ✔ |
| 5 | Results Part 3 | Namespaces | ✔ |
| 6 | Results Part 4 | Capabilities | ✔ |
| 7 | Deep Dive | Rule-level analysis | ✔ |
| 8 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered

- Static malware analysis  
- Capability-based detection  
- MITRE ATT&CK mapping  
- MAEC classification  
- MBC (Malware Behavior Catalogue)  
- Namespace-based rule grouping  

---

# Tool Overview

CAPA analyzes binaries to detect:

- Network communication  
- File system interaction  
- Persistence mechanisms  
- Process injection  
- Obfuscation techniques  

---

# Supported Inputs

- PE (Windows executables)  
- ELF (Linux binaries)  
- .NET modules  
- Shellcode  
- Sandbox reports  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

---

### Key Learning

- Two analysis types:
  - Static → analyze without execution  
  - Dynamic → run and observe  

- CAPA = static capability detection  

---

### Insight

> CAPA tells you **what malware can do**, not just what it is

---

---

## Task 2: Tool Usage

---

### Commands

```bash
capa.exe .\cryptbot.bin
capa.exe .\cryptbot.bin -v
capa.exe .\cryptbot.bin -vv
``` 

---

### Key Options

| Option | Purpose |
|------|--------|
| -h | Help |
| -v | Verbose |
| -vv | Very verbose |
| -j | JSON output |

---

### PowerShell

```powershell
Get-Content .\cryptbot.txt
```

---

### Key Learning

- Use pre-generated reports for faster analysis  

---

### Insight

> Real DFIR rarely runs tools live → mostly analyze outputs

---

---

## Task 3: General Info + MITRE + MAEC

---

### File Metadata

- MD5 / SHA1 / SHA256  
- OS → Windows  
- Format → PE  
- Arch → i386  

---

### MITRE ATT&CK

Example:

````

Defense Evasion → Obfuscated Files → T1027

```

---

### Key Techniques Identified

- Obfuscation → T1027  
- Sandbox Evasion → T1497  
- PowerShell Execution → T1059  
- Persistence → Scheduled Tasks  

---

### MAEC

| Value | Meaning |
|------|--------|
| Launcher | Executes actions |
| Downloader | Fetches payloads |

---

### Key Learning

- MITRE → attacker behavior  
- MAEC → malware classification  

---

### Insight

> This is where malware analysis becomes **threat intelligence**

---

---

## Task 4: Malware Behavior Catalogue (MBC)

---

### Structure

```

OBJECTIVE → BEHAVIOR → METHOD → IDENTIFIER

```

---

### Example

```

DATA → Encode Data → Base64 → C0026.001

```

---

### Objectives

- Execution  
- Persistence  
- Discovery  
- Defense Evasion  
- Communication  

---

### Micro-Behaviors

| Behavior | ID |
|--------|----|
| Create Process | C0017 |
| HTTP Communication | C0002 |
| Encode Data | C0026 |

---

### Key Learning

- MBC = standardized malware behavior mapping  

---

### Insight

> MBC = bridge between raw analysis and structured reporting

---

---

## Task 5: Namespaces

---

### Format

```

Capability → TLN → Namespace

```

---

### Example

```

reference anti-VM strings → anti-analysis → anti-vm/vm-detection

```

---

### Important TLNs

| TLN | Purpose |
|----|--------|
| anti-analysis | Evasion techniques |
| communication | Network activity |
| persistence | Long-term access |
| host-interaction | File/process actions |
| data-manipulation | Encoding/encryption |
| impact | Damage / crypto |

---

### Key Learning

- Namespaces group similar behaviors  

---

### Insight

> Namespace = context → helps fast triage

---

---

## Task 6: Capability Analysis

---

### Example Capabilities

- Anti-VM detection  
- HTTP communication  
- Base64 encoding  
- XOR encoding  
- File read/write  
- Process creation  
- PowerShell execution  
- Scheduled tasks  

---

### Example Mapping

```

Capability: schedule task via schtasks
→ TLN: persistence
→ Namespace: scheduled-tasks
→ Rule: schedule-task-via-schtasks.yml

````

---

### Key Learning

- Capability = rule match  
- Rule name = capability name  

---

### Insight

> CAPA is literally telling you **malware playbook**

---

---

## Task 7: Deep Analysis (-vv + JSON)

---

### Command

```bash
capa -j -vv .\cryptbot.bin > cryptbot_vv.json
```

---

### Tool

- CAPA Web Explorer  

---

### Features

- Rule inspection  
- Regex matching  
- Global search filtering  

---

### Example Detection Logic

````

string: /schtasks/i
string: //create /i

```

---

### Key Learning

- Rules = pattern matching + logic  

---

### Insight

> This is where you transition into **reverse engineering mindset**

---

---

## Task 8: Conclusion

---

### Key Takeaways

- CAPA automates malware capability detection  
- Bridges:
  - Reverse engineering  
  - Threat intelligence  
  - DFIR workflows  

---

# CAPA Cheat Sheet

---

## What CAPA Detects

| Category | Examples |
|---------|--------|
| Persistence | Scheduled tasks |
| Execution | PowerShell |
| Evasion | Anti-VM |
| Communication | HTTP |
| Data | Base64/XOR |
| Impact | Crypto mining |

---

## Workflow

```

Binary → CAPA → Capabilities → MITRE → Investigation

```

---

# Reflection

CAPA is **critical for DFIR + Threat Intel**

You now know how to:
- Analyze malware statically  
- Map behavior to MITRE  
- Understand capabilities without reversing  

---

### From a SOC / DFIR POV

- Used in:
  - Malware triage  
  - Incident response  
  - Threat hunting  
