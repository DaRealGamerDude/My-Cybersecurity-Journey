# TryHackMe — First Shift CTF

**Date Completed:**  
**Difficulty:** Medium  
**Platform:** TryHackMe  
**Focus Areas:** SOC Operations, Threat Intelligence, Malware Analysis

---

## 📌 Scenario Overview

This room simulates a SOC analyst’s first shift, starting with a suspicious VPN login alert and escalating into a full malware and threat intelligence investigation.

The objective was to validate alerts, analyze infrastructure, investigate a suspicious binary, and map attacker behavior using real-world SOC workflows.

---

## 🎯 Investigation Objectives

- Validate a suspicious VPN login using threat intelligence
- Assess IP reputation and associated services
- Analyze a suspicious Windows binary
- Identify malware family and affiliate behavior
- Correlate infrastructure via domains and certificates
- Map attacker behavior to MITRE ATT&CK

---

## 🧭 Investigation Walkthrough

### 🔹 Task 3: Initial Alert Triage — Suspicious VPN Login

**Alert:**  
Unusual VPN login for `susan.martin@probablyfine.thm` from Singapore.

**Actions Taken:**
- Verified user travel claims
- Investigated login IP using threat intelligence platform

**Key Findings:**
- IP reputation was mixed but associated with suspicious activity
- ASN and hosting context suggested infrastructure abuse

**SOC Insight:**  
User confirmation is critical — false assumptions lead to missed incidents.

---

### 🔹 Task 4: IP Intelligence & Infrastructure Context

**Tools Used:**
- TryDetectThis (Threat Intelligence)

**Findings:**
- ASN: `212238`
- Hosting provider linked to infrastructure commonly abused by malware
- Passive DNS revealed suspicious domains

**Why This Matters:**  
Infrastructure reuse is often more reliable than single IP reputation.

---

### 🔹 Task 5: Malware Identification (Binary Analysis)

**Suspicious File:**
- Filename: `zY9sqWs.exe`
- SHA-256: `b8e02f2bc0ffb42e8cf28e37a26d8d825f639079bf6d948f8debab6440ee5630`

**Results:**
- Identified as **Lumma Stealer (LummaC2)**
- Confirmed via vendor detections and YARA rules

**YARA Insight:**
- Rule author: `kevoreilly`
- Condition included PE file magic check (`uint16(0) == 0x5a4d`)

---

### 🔹 Task 6: Infrastructure & Campaign Correlation

**Observed Domains:**
- `joyfulhezart.tech`
- `gadgethgfub.icu`
- `hardswarehub.today`

**Analysis:**
- Shared TLS certificate patterns
- Large-scale malicious infrastructure cluster
- Campaign-level reuse rather than single-domain usage

**SOC Insight:**  
Certificates are powerful for identifying malware campaigns.

---

### 🔹 Task 7: Threat Intelligence Report Correlation

**Report Identified:**
> *Behind the Curtain: How Lumma Affiliates Operate*

**Key Takeaways:**
- Lumma operates as Malware-as-a-Service (MaaS)
- Affiliates often run multiple scams in parallel
- Heavy reliance on proxy services, VPS providers, and crypting services

---

### 🔹 Task 8: Affiliate Behavior & MITRE ATT&CK Mapping

**Notable Affiliate Activity:**
- Mexican-based affiliate using multiple infostealers
- Android-targeting malware identified: **CraxsRAT**

**MITRE ATT&CK Mapping:**
- **T1583.003 — Acquire Infrastructure: Virtual Private Server**

**Reasoning:**  
Affiliates used AnonRDP to acquire anonymous VPS infrastructure for operations.

---

## 🔧 Tools & Platforms Used

- TryHackMe
- TryDetectThis
- Threat Intelligence Reports
- YARA Rules
- MITRE ATT&CK Framework

---

## 🧠 Key Lessons Learned

1. Threat intel is about **patterns**, not single indicators
2. Malware ecosystems are **collaborative**, not isolated
3. MITRE mapping depends on **attacker intent**, not tool names
4. CTFs reward **source-faithful answers**, SOC work rewards reasoning

---

## 📚 Concepts to Revisit

- Malware-as-a-Service (MaaS)
- Certificate-based infrastructure clustering
- Affiliate-based threat models
- SOC alert validation workflows

---

## 🔗 References

- TryHackMe — First Shift CTF
- Recorded Future — Lumma Affiliate Analysis
- MITRE ATT&CK Framework

