# TryHackMe Room: OWASP Top 10 (2025) — Insecure Data Handling

**Path:** Web Security Fundamentals
**Module Type:** Concept + Practical (Input Handling & Exploitation)
**Difficulty:** Beginner–Intermediate
**Status:** Completed

---

# Summary

This room focuses on vulnerabilities caused by **unsafe handling of user input and data**.

Covered categories:

* A04: Cryptographic Failures
* A05: Injection
* A08: Software or Data Integrity Failures

---

# Rooms in This Module

| Order | Section      | Primary Focus          | Status |
| ----- | ------------ | ---------------------- | ------ |
| 1     | Introduction | Overview               | ✔      |
| 2     | A04          | Cryptographic Failures | ✔      |
| 3     | A05          | Injection              | ✔      |
| 4     | A08          | Integrity Failures     | ✔      |

---

# Key Concepts Covered

* Weak cryptographic implementations
* Injection vulnerabilities (SSTI focus)
* Insecure deserialization
* Unsafe trust in user-controlled data
* Exploitation and detection workflows

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Room Objective:**
Understand how improper data handling leads to exploitable vulnerabilities.

---

### Key Learning

* Data is the core attack surface in web applications
* Improper validation or trust leads to compromise

---

### Insight

> Never trust user input — always validate and sanitize

---

## Task 2: A04 — Cryptographic Failures

**Room Objective:**
Identify weaknesses in encryption and data protection.

---

### Vulnerability Concept

* Weak or improper use of cryptography

---

### Common Issues

* Weak hashing (MD5, SHA1)
* Hardcoded or reused keys
* No encryption for sensitive data

---

### Q1: Decrypt the notes. What is the flag?

`THM{WEAK_CRYPTO_FLAG}`

---

### Explanation

* Application used a **shared weak key** for encryption
* Allowed predictable decryption of stored notes

---

### Key Learning

* Encryption is ineffective if keys are weak or reused
* Implementation matters more than presence of encryption

---

### SOC / DFIR Relevance

* Look for:

  * Exposed secrets
  * Weak encryption patterns
  * Sensitive data leaks

---

## Task 3: A05 — Injection (SSTI)

**Room Objective:**
Understand how improper input handling leads to code execution.

---

### Vulnerability Concept

* Application processes user input as executable code

---

### Attack Type

* Server-Side Template Injection (SSTI)

---

### Q1: Retrieve the contents of flag.txt

`THM{SSTI_FLAG_OBTAINED}`

---

### Explanation

* Input passed into template engine without sanitization
* Malicious payload executed on server
* Allowed reading of local files

---

### Key Learning

* Injection vulnerabilities can lead to full system compromise
* Input must always be treated as untrusted

---

### SOC / DFIR Relevance

* Indicators:

  * Template payload patterns (`{{ }}`, `${}`)
  * Unexpected file access
  * Server-side execution traces

---

## Task 4: A08 — Software or Data Integrity Failures

**Room Objective:**
Understand risks of trusting unverified data and code.

---

### Vulnerability Concept

* Application trusts serialized or external data without validation

---

### Attack Type

* Insecure Deserialization (Python Pickle)

---

### Q1: Contents of flag.txt?

`THM{INSECURE_DESERIALIZATION}`

---

### Explanation

* Malicious serialized payload executed during deserialization
* Allowed arbitrary code execution
* Used to read sensitive file

---

### Key Learning

* Deserialization can directly lead to RCE
* Never trust serialized input

---

### SOC / DFIR Relevance

* Look for:

  * Suspicious serialized payloads
  * Unexpected execution behavior
  * Indicators of remote code execution

---

# Real-World Mapping

| Vulnerability          | Real Scenario                    |
| ---------------------- | -------------------------------- |
| Cryptographic Failures | Weak password storage → breaches |
| Injection              | SQLi / SSTI → data exfiltration  |
| Integrity Failures     | Deserialization → RCE            |

---

# Key Takeaways

* A04: Weak cryptography exposes sensitive data
* A05: Injection enables execution of malicious input
* A08: Trusting data leads to code execution

---

# Reflection

This room reinforces that:

* Most critical vulnerabilities arise from **trusting unsafe data**
* Input validation and secure handling are essential
* Many attacks originate from simple logic flaws

It directly supports progression toward:

**SOC Analyst → DFIR → Threat Intelligence**
