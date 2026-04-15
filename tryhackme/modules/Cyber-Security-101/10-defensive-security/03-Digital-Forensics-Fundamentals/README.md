# TryHackMe Room: Digital Forensics Fundamentals

**Path:** Defensive Security  
**Module Type:** Concept + Practical (DFIR)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Digital Forensics**, the process of investigating cyber incidents by collecting and analyzing digital evidence.

It covers:
- Forensic methodology (NIST model)  
- Evidence acquisition  
- Windows forensics  
- Metadata analysis (PDF + EXIF)  

> Digital Forensics focuses on:
> **Evidence → Analysis → Attribution**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Forensics fundamentals | ✔ |
| 2 | Methodology | NIST framework | ✔ |
| 3 | Evidence Acquisition | Data integrity | ✔ |
| 4 | Windows Forensics | Disk & memory analysis | ✔ |
| 5 | Practical | Metadata investigation | ✔ |

---

# Key Concepts Covered

- Digital evidence handling  
- Chain of custody  
- Forensic imaging  
- Memory vs disk analysis  
- Metadata analysis (PDF + EXIF)  
- DFIR workflow  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction to Digital Forensics

**Room Objective:**  
Understand role of digital forensics in investigations.

---

### Q1: Which team handled the case?

`digital forensics`

**Explanation:**  
Specialized team responsible for investigating digital evidence.

---

### Key Learning

- Digital forensics = cybercrime investigation  
- Evidence comes from:
  - Computers  
  - Phones  
  - Storage devices  

---

### Insight

> Every digital action leaves a trace

---

### Common Struggles

- Thinking logs = only evidence  
- Ignoring device-level artifacts  

---

## Task 2: Digital Forensics Methodology (NIST)

**Room Objective:**  
Understand structured forensic workflow.

---

### Q1: Phase for correlating data?

`Analysis`

**Explanation:**  
Draw conclusions from collected evidence.

---

### Q2: Phase for filtering data?

`Examination`

**Explanation:**  
Extract relevant data from large datasets.

---

### NIST Phases

| Phase | Purpose |
|------|--------|
| Collection | Gather evidence |
| Examination | Filter data |
| Analysis | Correlate findings |
| Reporting | Document results |

---

### Key Learning

- Investigations must follow structured process  
- Raw data ≠ useful evidence  

---

### Insight

> DFIR = structured reasoning, not guesswork

---

### Common Struggles

- Skipping examination phase  
- Jumping directly to conclusions  

---

## Task 3: Evidence Acquisition

**Room Objective:**  
Understand how to safely collect evidence.

---

### Q1: Tool ensuring data integrity?

`write blocker`

**Explanation:**  
Prevents modification of original evidence.

---

### Q2: Evidence tracking document?

`chain of custody`

**Explanation:**  
Tracks ownership and handling of evidence.

---

### Key Learning

- Always maintain:
  - Authorization  
  - Integrity  
  - Documentation  

---

### Chain of Custody Includes

- Evidence description  
- Collector  
- Timestamp  
- Storage location  
- Access logs  

---

### Insight

> If integrity is broken → evidence is useless in court

---

### Common Struggles

- Not preserving original data  
- Missing documentation  

---

## Task 4: Windows Forensics

**Room Objective:**  
Understand forensic imaging.

---

### Q1: Image for volatile data?

`Memory Image`

**Explanation:**  
Captures RAM (lost after shutdown).

---

### Types of Forensic Images

| Type | Data |
|------|------|
| Disk Image | Files, history, persistent data |
| Memory Image | Processes, connections, runtime data |

---

### Key Tools

| Tool | Purpose |
|------|--------|
| FTK Imager | Disk acquisition |
| Autopsy | Disk analysis |
| DumpIt | Memory acquisition |
| Volatility | Memory analysis |

---

### Insight

> Memory first, disk second (volatile data priority)

---

### Common Struggles

- Forgetting volatile data  
- Using wrong tools for analysis  

---

## Task 5: Practical — Metadata Investigation

**Room Objective:**  
Extract forensic evidence from files.

---

### Case Overview

- Kidnapper sent ransom note  
- Evidence:
  - PDF document  
  - Image file  

---

### Evidence Preview

:contentReference[oaicite:0]{index=0}  

---

### PDF Metadata Analysis

Command:

pdfinfo ransom-letter.pdf

---

### Q1: Author?

`Ann Gree Shepherd`

**Explanation:**  
Extracted from PDF metadata.

---

### EXIF Analysis

Command:

exiftool image.jpg

---

### Q2: Location?

`Milk Street`

**Explanation:**  
Derived from GPS coordinates.

---

### Q3: Camera model?

`Canon EOS R6`

**Explanation:**  
Found in EXIF metadata.

---

### Key Learning

- Files contain hidden metadata  
- Metadata reveals:
  - Author  
  - Location  
  - Device used  

---

### Insight

> Metadata = silent evidence

---

### Common Struggles

- Ignoring metadata completely  
- Not using proper tools (pdfinfo, exiftool)  

---

# Tools Used

- pdfinfo (PDF metadata)  
- exiftool (image metadata)  
- FTK Imager  
- Autopsy  
- Volatility  

---

# Commands Cheat Sheet

PDF metadata

pdfinfo file.pdf

EXIF metadata

exiftool image.jpg

---

# DFIR Workflow Summary

1. Identify evidence  
2. Acquire safely (write blocker)  
3. Maintain chain of custody  
4. Examine data  
5. Analyze findings  
6. Report conclusions  

---

# Reflection

This module is **directly aligned with your long-term goal (DFIR)**.

Key takeaways:

- Evidence integrity is critical  
- Metadata is powerful  
- Memory forensics is essential  
- Investigations must be structured
