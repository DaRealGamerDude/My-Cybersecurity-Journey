# TryHackMe Room: FlareVM: Arsenal of Tools

**Path:** Defensive Security Tooling  
**Module Type:** Malware Analysis + Reverse Engineering Environment  
**Difficulty:** Beginner–Intermediate  
**Status:** Completed  

---

# Summary

This room introduces **FlareVM**, a Windows-based malware analysis environment designed for:

- Reverse engineering  
- Malware analysis  
- Incident response  
- Digital forensics  

It focuses on:
- Tool familiarity  
- Static + dynamic analysis  
- Process monitoring  
- Network behavior analysis  

> FlareVM = **Windows-based malware analysis + reverse engineering lab**

---

# Room Sections

| Order | Section | Focus | Status |
|------|--------|------|--------|
| 1 | Introduction | FlareVM overview | ✔ |
| 2 | Arsenal | Tool ecosystem | ✔ |
| 3 | Tools Overview | Core investigation tools | ✔ |
| 4 | Analysis | Hands-on malware analysis | ✔ |
| 5 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered

- Static analysis (PE files)  
- Dynamic analysis (process + network behavior)  
- API analysis  
- Malware indicators  
- Process relationships  
- C2 detection  

---

# Tool Categories (FlareVM)

---

## Reverse Engineering

- Ghidra  
- x64dbg  
- OllyDbg  
- Radare2  
- Binary Ninja  

---

## Static Analysis

- PEStudio  
- CFF Explorer  
- DIE  

---

## Dynamic Analysis

- Process Explorer  
- Process Monitor  
- Wireshark  

---

## Forensics

- Volatility  
- FTK Imager  

---

## File Analysis

- HxD  
- FileInsight  

---

## String Analysis

- FLOSS  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

---

### Key Learning

- FlareVM = Windows DFIR + malware lab  
- Built by FireEye FLARE team  

---

### Insight

> Windows malware → analyze in Windows environment (FlareVM)

---

---

## Task 2: Arsenal of Tools

---

### Key Tools (Important Ones)

| Tool | Purpose |
|------|--------|
| x64dbg | Debugging binaries |
| CFF Explorer | PE file analysis |
| Process Hacker | Process monitoring |
| FTK Imager | Disk forensics |
| HxD | Hex editing |

---

### Key Learning

- Tools are **task-specific**
- No single tool solves everything  

---

### Insight

> Real analysts switch tools constantly

---

---

## Task 3: Core Investigation Tools

---

### 1. Process Monitor (Procmon)

---

### Purpose

- Monitor:
  - File activity  
  - Registry  
  - Process/thread activity  

---

### DFIR Use

- Detect abnormal behavior  
- Track malware actions  

---

### Key Example

- Monitoring `lsass.exe` access  
- Possible credential dumping  

---

---

### 2. Process Explorer

---

### Purpose

- View:
  - Running processes  
  - Parent-child relationships  
  - Loaded DLLs  

---

### Key Learning

- Identify suspicious process chains  

---

### Example

```

explorer.exe → cobaltstrike.exe

```

---

### Insight

> Parent-child relationship = VERY important in SOC

---

---

### 3. HxD (Hex Editor)

---

### Purpose

- View raw binary data  

---

### Key Finding

```

4D 5A → Executable (MZ header)

```

---

### Insight

> File extension can lie, headers don’t

---

---

### 4. CFF Explorer

---

### Purpose

- Analyze PE file structure  
- Generate hashes  

---

### Key Learning

- Verify:
  - File integrity  
  - Authenticity  

---

---

### 5. Wireshark

---

### Purpose

- Analyze network traffic  

---

### Key Observations

- Protocols  
- IPs  
- Ports  
- Encrypted traffic (TLS)  

---

---

### 6. PEStudio

---

### Purpose

- Static malware analysis  

---

### Key Indicators

- Entropy  
- Imports (APIs)  
- Metadata  
- Suspicious behavior  

---

---

### 7. FLOSS

---

### Purpose

- Extract strings from binaries  

---

### Key Learning

- Finds:
  - URLs  
  - IPs  
  - Commands  
  - Keys  

---

---

## Task 4: Malware Analysis (Hands-On)

---

## Step 1: Static Analysis (PEStudio)

---

### File

```

windows.exe

````

---

### Key Findings

| Indicator | Value |
|----------|------|
| Entropy | 7.999 |
| Execution Level | requireAdministrator |
| MD5 | 9FDD4767DE5AEC8E577C1916ECC3E1D6 |

---

### Red Flags

- High entropy → packed/obfuscated  
- Fake metadata (REGEDIT impersonation)  
- Russian strings (suspicious context)  
- Not in System32  

---

### Key APIs

| API | Purpose |
|-----|--------|
| set_UseShellExecute | Execute processes |
| RijndaelManaged | AES encryption |

---

### Insight

> Crypto APIs = possible ransomware / obfuscation

---

---

## Step 2: String Analysis (FLOSS)

---

### Command

```bash
FLOSS.exe .\windows.exe > windows.txt
````

---

### Findings

* Extracted strings confirm:

  * API usage
  * Behavior indicators

---

### Insight

> Strings = quick intel before deep analysis

---

---

## Step 3: Dynamic Analysis

---

### Target

```
cobaltstrike.exe
```

---

---

### Process Explorer

---

### Findings

| Attribute      | Value        |
| -------------- | ------------ |
| Parent Process | explorer.exe |
| Process Type   | Child        |

---

---

### Network Analysis

---

### Findings

| Indicator | Value               |
| --------- | ------------------- |
| C2 IP     | 47[.]120[.]46[.]210 |
| Port      | 81                  |

---

---

### Process Monitor (Procmon)

---

### Purpose

* Confirm behavior
* Filter by process

---

### Key Learning

* Always verify using multiple tools

---

---

## Key Indicators Identified

---

### Malware Traits

* Process spawning
* Network communication
* Encryption usage
* Elevated privileges

---

### Attack Pattern

```
User → Download → Execution → Process Spawn → C2 Connection
```

---

---

# FlareVM Cheat Sheet

---

## Static Analysis Flow

```
File → PEStudio → FLOSS → CFF Explorer
```

---

## Dynamic Analysis Flow

```
Execute → Process Explorer → Procmon → Wireshark
```

---

## Investigation Flow

```
File → Behavior → Network → Indicators → Conclusion
```

---

# Reflection

This room builds on REMnux and introduces:

* Windows-focused malware analysis
* Real process monitoring
* C2 detection
