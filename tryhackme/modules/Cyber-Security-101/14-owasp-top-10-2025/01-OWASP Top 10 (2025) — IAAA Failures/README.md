# TryHackMe Room: OWASP Top 10 (2025) — IAAA Failures

**Path:** Web Security Fundamentals
**Module Type:** Concept + Practical (Web Exploitation & Detection)
**Difficulty:** Beginner
**Status:** Completed

---

# Summary

This room explores key OWASP Top 10 (2025) vulnerabilities related to failures in the **IAAA model**:

* Identity
* Authentication
* Authorisation
* Accountability

It demonstrates how misconfigurations in these areas lead to real-world vulnerabilities and how they can be exploited and detected.

---

# Rooms in This Module

| Order | Section      | Primary Focus               | Status |
| ----- | ------------ | --------------------------- | ------ |
| 1     | Introduction | Overview of IAAA failures   | ✔      |
| 2     | IAAA Model   | Core concepts               | ✔      |
| 3     | A01          | Broken Access Control       | ✔      |
| 4     | A07          | Authentication Failures     | ✔      |
| 5     | A09          | Logging & Alerting Failures | ✔      |
| 6     | Conclusion   | Key takeaways               | ✔      |

---

# Key Concepts Covered

* IAAA Model (Identity, Authentication, Authorisation, Accountability)
* Broken Access Control (IDOR, privilege escalation)
* Authentication flaws (logic issues, weak validation)
* Logging & monitoring failures
* Detection and investigation workflows

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Room Objective:**
Understand how failures in IAAA lead to critical vulnerabilities.

---

### Key Learning

* IAAA controls how users are verified and tracked
* Failure at any stage compromises the system

---

### Insight

> If identity or access control fails, security collapses downstream

---

## Task 2: What is IAAA?

**Room Objective:**
Understand the four core components of access control.

---

### Q1: What does IAAA stand for?

`Identity, Authentication, Authorisation, Accountability`

---

### Explanation

* **Identity:** Who the user is (username/email)
* **Authentication:** Verifying identity (password, OTP)
* **Authorisation:** What they can access
* **Accountability:** Logging actions

---

### Key Learning

* Each stage depends on the previous one
* Skipping one breaks the entire chain

---

## Task 3: A01 — Broken Access Control

**Room Objective:**
Understand access control failures and privilege escalation.

---

### Vulnerability Concept

* Server fails to enforce permissions
* Application trusts user input

---

### Example Attack (IDOR)

```
/account?id=7 → /account?id=6
```

Accessing another user's data indicates broken access control.

---

### Q1: If you can view another user's data without changing roles?

`Horizontal`

---

### Explanation

* No privilege level change
* Access to another user's data
  → Horizontal privilege escalation

---

### Q2: Note found in millionaire account?

`THM{Found.the.Millionare!}`

---

### Explanation

* ID manipulation exposed sensitive account
* Confirms lack of object-level access control

---

### Key Learning

* IDOR is one of the most common web vulnerabilities
* Client-side control = insecure

---

### SOC / DFIR Relevance

* Look for:

  * Sequential ID access attempts
  * Multiple resource access patterns
    → Indicates enumeration attack

---

## Task 4: A07 — Authentication Failures

**Room Objective:**
Understand weaknesses in identity verification.

---

### Vulnerability Concept

* Weak authentication logic
* Improper input handling
* Lack of validation

---

### Attack Performed

* Registered user as `aDmiN`
* Exploited case-insensitive handling
* Logged in as admin

---

### Q1: Flag on admin dashboard?

`THM{Account.confusion.FTW!}`

---

### Explanation

* System failed to normalize usernames
* Allowed duplicate identity representation
  → Account confusion vulnerability

---

### Key Learning

* Authentication logic flaws can lead to full account takeover
* Case sensitivity issues are critical

---

### SOC / DFIR Relevance

* Indicators:

  * Similar usernames (`admin`, `Admin`, `aDmiN`)
  * Multiple account creations
  * Suspicious login patterns

---

## Task 5: A09 — Logging & Alerting Failures

**Room Objective:**
Understand the importance of logging in detection and investigation.

---

### Vulnerability Concept

* Missing or weak logging
* No alerting mechanisms
* Poor visibility

---

### Investigation Findings

* Brute-force attack detected
* Account compromise identified
* Post-compromise actions traced

---

### Q1: Attacker IP?

`203.0.113.45`

---

### Explanation

* Multiple login attempts from same IP
  → Brute-force source

---

### Q2: Compromised username?

`admin`

---

### Explanation

* Successful login recorded
  → Account takeover confirmed

---

### Q3: Endpoint accessed?

`/supersecretadminstuff`

---

### Explanation

* Post-compromise action
  → Attempt to access privileged functionality

---

### Key Learning

* Logs are critical for:

  * Detection
  * Investigation
  * Attribution

---

### SOC / DFIR Relevance

This task directly simulates:

* Log analysis
* Incident reconstruction
* Attack timeline building

---

## Task 6: Conclusion

---

### Key Takeaways

* **A01:** Enforce server-side access control
* **A07:** Strengthen authentication logic
* **A09:** Ensure proper logging and monitoring

---

# Real-World Mapping

| Concept               | Application              |
| --------------------- | ------------------------ |
| IDOR                  | Unauthorized data access |
| Auth bypass           | Account takeover         |
| Logging failures      | Missed incidents         |
| Brute-force detection | SIEM alerts              |

---

# Reflection

This room demonstrates how:

* Simple logic flaws lead to major vulnerabilities
* Access control and authentication are critical security layers
* Logging enables effective detection and response

It directly supports progression toward:

**SOC Analyst → DFIR → Threat Intelligence**
