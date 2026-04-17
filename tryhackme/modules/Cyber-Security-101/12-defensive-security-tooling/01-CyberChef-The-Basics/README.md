# TryHackMe Room: CyberChef: The Basics

**Path:** Defensive Security Tooling  
**Module Type:** Tooling (Data Analysis / Decoding)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **CyberChef**, a powerful web-based tool used for data transformation, decoding, and analysis.

It covers:
- CyberChef interface  
- Data transformation operations  
- Recipe-based workflows  
- Encoding/decoding techniques  
- Practical data extraction  

> CyberChef = **Swiss Army knife for data manipulation in cybersecurity**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Intro | Tool overview | ✔ |
| 2 | Access | Usage methods | ✔ |
| 3 | Interface | Tool navigation | ✔ |
| 4 | Workflow | Thinking process | ✔ |
| 5 | Practice | Data extraction | ✔ |
| 6 | Lab | Real transformations | ✔ |
| 7 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered

- Encoding & decoding  
- Data extraction  
- Recipe-based processing  
- Base64 / Base85 / URL decoding  
- UNIX timestamps  
- Binary transformations  

---

# Tool Overview

CyberChef works using:

- **Operations** → tools  
- **Recipe** → workflow  
- **Input** → raw data  
- **Output** → processed data  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Objective:**  
Understand CyberChef purpose.

---

### Key Learning

- Handles:
  - Encoding/decoding  
  - Encryption transformations  
  - Data extraction  

---

### Insight

> If data looks like gibberish → CyberChef is your first tool

---

---

## Task 2: Accessing the Tool

**Methods:**

- Online (browser)
- Offline (local file)

---

### Key Learning

- No installation required (web-based)

---

---

## Task 3: Navigating the Interface

---

### Q1: Where is "From Base64"?

`Operations`

---

### Q2: Heart of the tool?

`Recipe`

---

### Core Components

| Area | Function |
|------|--------|
| Operations | Tools list |
| Recipe | Workflow builder |
| Input | Raw data |
| Output | Result |

---

### Common Operations

| Operation | Purpose |
|----------|--------|
| From Base64 | Decode Base64 |
| URL Decode | Decode URLs |
| ROT13 | Simple cipher |
| To Hex | Convert to hex |
| To Base64 | Encode data |

---

### Key Learning

- Recipe = sequence of operations  

---

### Insight

> Order of operations matters

---

---

## Task 4: Thought Process

---

### Q1: Define objective step?

`1`

---

### Workflow

1. Define goal  
2. Input data  
3. Select operations  
4. Analyze output  

---

### Key Learning

- Don’t randomly try operations  
- Think → then apply  

---

### Insight

> CyberChef is logic-driven, not trial-and-error

---

---

## Task 5: Practice

---

### Categories Used

#### Extractors

- Extract IPs  
- Extract Emails  
- Extract URLs  

---

#### Data Formats

- Base64  
- Base85  
- Base58  
- URL encoding  

---

#### Time Conversion

- UNIX ↔ Datetime  

---

### Key Learning

- Quickly extract useful data from messy input  

---

### Insight

> Logs = noise → CyberChef extracts signal

---

---

## Task 6: Practical Lab

---

### Q1: IP starting/ending with 10?

`10.10.2.10`

---

### Q2: Base64 of "Nice Room!"?

`TmljZSBSb29tIQ==`

---

### Q3: URL Decoded value?

`https://tryhackme.com/r/room/cyberchefbasics`

---

### Q4: UNIX → Datetime?

`Sun 1 September 2024 00:40:58 UTC`

---

### Q5: Base85 decoded?

`This is fun!`

---

### Key Learning

- Multi-step transformations  
- Combining operations  

---

### Insight

> Real investigations require chaining operations

---

### Common Struggles

- Not knowing which encoding is used  
- Wrong operation order  

---

---

## Task 7: Conclusion

---

### Key Takeaways

- CyberChef simplifies:
  - Decoding  
  - Data extraction  
  - Transformation  

---

# CyberChef Cheat Sheet

---

## Common Use Cases

| Scenario | Operation |
|---------|----------|
| Suspicious string | Base64 decode |
| Logs | Extract IPs |
| URLs | URL decode |
| Timestamps | UNIX conversion |
| Obfuscation | ROT13 / Base85 |

---

## Example Workflow


Input → Extract → Decode → Analyze


---

# Reflection

This tool is **extremely important for DFIR + SOC**.

You now know how to:
- Decode suspicious data  
- Extract indicators (IOCs)  
- Analyze encoded payloads  

---

### From a SOC / DFIR POV

- Used in:
  - Log analysis  
  - Malware decoding  
  - Threat intelligence
