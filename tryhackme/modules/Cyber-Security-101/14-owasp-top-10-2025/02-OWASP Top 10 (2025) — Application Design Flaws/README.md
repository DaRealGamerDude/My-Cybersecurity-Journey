# TryHackMe Room: OWASP Top 10 (2025) — Application Design Flaws

**Path:** Web Security Fundamentals
**Module Type:** Concept + Practical (Design-Level Vulnerabilities)
**Difficulty:** Beginner–Intermediate
**Status:** Completed

---

# Summary

This room explores OWASP Top 10 (2025) vulnerabilities caused by **poor system design, unsafe configurations, and weak dependencies**.

Covered categories:

* AS02: Security Misconfigurations
* AS03: Software Supply Chain Failures
* AS04: Cryptographic Failures
* AS06: Insecure Design

---

# Rooms in This Module

| Order | Section      | Primary Focus              | Status |
| ----- | ------------ | -------------------------- | ------ |
| 1     | Introduction | Setup & overview           | ✔      |
| 2     | AS02         | Security Misconfigurations | ✔      |
| 3     | AS03         | Supply Chain Failures      | ✔      |
| 4     | AS04         | Cryptographic Failures     | ✔      |
| 5     | AS06         | Insecure Design            | ✔      |
| 6     | Conclusion   | Key takeaways              | ✔      |

---

# Key Concepts Covered

* Configuration-based vulnerabilities
* Dependency and supply chain risks
* Cryptographic misimplementation
* Design-level security flaws
* Real-world exploitation scenarios

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Room Objective:**
Understand how poor design and configuration lead to exploitable vulnerabilities.

---

### Key Learning

* Not all vulnerabilities are coding bugs
* Many originate from:

  * Misconfiguration
  * Poor architecture
  * Weak assumptions

---

### Insight

> Security must be built into design, not added later

---

## Task 2: AS02 — Security Misconfigurations

**Room Objective:**
Identify risks caused by unsafe system configurations.

---

### Vulnerability Concept

* Systems deployed with:

  * Default settings
  * Exposed services
  * Misconfigured permissions

---

### Common Issues

* Default credentials
* Public cloud storage
* Verbose error messages
* Exposed APIs/admin panels

---

### Q1: What's the flag?

`THM{V3RB0S3_3RR0R_L34K}`

---

### Explanation

* Application leaked **internal details via verbose error messages**
* Indicates improper production configuration

---

### Key Learning

* Misconfigurations are often the **easiest attack vector**
* No exploit needed — just observation

---

### SOC / DFIR Relevance

* Repeated error-triggering requests
* API probing activity
  → Indicators of reconnaissance

---

## Task 3: AS03 — Software Supply Chain Failures

**Room Objective:**
Understand risks from third-party dependencies.

---

### Vulnerability Concept

* Application relies on:

  * Outdated
  * Unverified
  * Compromised components

---

### Attack Scenario

* Found vulnerable dependency:

  * `vulnerable_utils.py`

---

### Q1: What's the flag?

`THM{SUPPLY_CH41N_VULN3R4B1L1TY}`

---

### Explanation

* Vulnerability existed in **dependency, not main code**
* Exploiting supply chain bypasses traditional defenses

---

### Key Learning

* Dependencies expand attack surface significantly
* Trusting third-party code blindly is dangerous

---

### SOC / DFIR Relevance

* Indicators:

  * Suspicious behavior from trusted apps
  * Unexpected outbound connections
  * Malicious updates

---

## Task 4: AS04 — Cryptographic Failures

**Room Objective:**
Identify improper use of encryption mechanisms.

---

### Vulnerability Concept

* Weak or incorrect cryptographic implementation

---

### Common Issues

* Hardcoded keys
* Weak algorithms
* No encryption
* Poor key management

---

### Q1: What's the flag?

`THM{CRYPTO_FAILURE_H4RDCOD3D_K3Y}`

---

### Explanation

* Encryption key was **hardcoded in application**
* Allowed easy decryption of sensitive data

---

### Key Learning

* Encryption is useless if keys are exposed
* Key management is as important as encryption itself

---

### SOC / DFIR Relevance

* Look for:

  * Exposed secrets
  * Plaintext sensitive data
  * Abnormal decryption activity

---

## Task 5: AS06 — Insecure Design

**Room Objective:**
Understand vulnerabilities caused by flawed architecture.

---

### Vulnerability Concept

* Security flaws built into system logic

---

### Attack Scenario

* Application assumed:

  * Only mobile clients would access API

* Bypassed restriction via direct requests

---

### Q1: What's the flag?

`THM{1NS3CUR3_D35IGN_4SSUMPT10N}`

---

### Explanation

* Security relied on **assumption instead of enforcement**
* No proper validation or access control

---

### Key Learning

* Design flaws cannot be patched easily
* Require rethinking system architecture

---

### SOC / DFIR Relevance

* Requires behavioral detection
* Indicators:

  * Unexpected access patterns
  * Abuse of backend APIs

---

## Task 6: Conclusion

---

### Key Takeaways

* **AS02:** Secure configurations are critical
* **AS03:** Dependencies must be verified
* **AS04:** Cryptography must be implemented correctly
* **AS06:** Secure design is foundational

---

# Real-World Mapping

| Vulnerability          | Real Scenario                |
| ---------------------- | ---------------------------- |
| Misconfiguration       | Public cloud data leaks      |
| Supply Chain           | Compromised software updates |
| Cryptographic Failures | Hardcoded API keys           |
| Insecure Design        | Logic-based API bypass       |

---

# Reflection

This room highlights that:

* Many vulnerabilities originate from **design and deployment mistakes**
* Attackers often exploit **simple misconfigurations and assumptions**
* Secure architecture is essential for long-term defense

It directly supports progression toward:

**SOC Analyst → DFIR → Threat Intelligence**
