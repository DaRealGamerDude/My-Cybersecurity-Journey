# Build Your Cyber Security Career — Module Writeup

This module establishes the **theoretical foundation of cybersecurity** and connects it to **real-world SOC, DFIR, and organizational security practices**.

---

## Module Overview

| Room | Focus |
|------|------|
| Security Principles | Core security models & concepts |
| Careers in Cyber | Industry roles & responsibilities |
| Training Impact on Teams | Organizational security maturity |

---

# Security Principles

## Why This Matters (SOC/DFIR Context)

Every alert, incident, or investigation maps back to:
- **Confidentiality breach → Data leak**
- **Integrity breach → Tampering / malware**
- **Availability breach → DoS / ransomware**

---

## CIA Triad (Operational View)

| Component | Real SOC Example |
|----------|----------------|
| Confidentiality | Credential dumping (LSASS access) |
| Integrity | Log tampering / file modification |
| Availability | Service outage / ransomware |

**Flag:** `THM{CIA_TRIAD}`

---

## DAD Triad (Attacker Perspective)

| Attack Type | Example |
|------------|--------|
| Disclosure | Database breach |
| Alteration | Config/log modification |
| Destruction | System shutdown / encryption |

---

## Security Models (Why You Should Care)

| Model | Use in Real World |
|------|-----------------|
| Bell-LaPadula | Access control systems (clearance levels) |
| Biba | Data integrity pipelines |
| Clark-Wilson | Financial systems / transaction validation |

**Flag:** `THM{SECURITY_MODELS}`

---

## Core Principles in Practice

### Defence-in-Depth
- Firewall → EDR → SIEM → IAM  
- **Failure of one ≠ total compromise**

### Zero Trust
- Every request = verified  
- Common in:
  - Cloud environments
  - Enterprise networks  

### Trust but Verify
- Logging + monitoring  
- Example: SIEM alert validation  

---

## ISO/IEC 19249 (Real Mapping)

| Principle | SOC Example |
|----------|------------|
| Least Privilege | RBAC in SIEM |
| Attack Surface Reduction | Disable unused ports/services |
| Fail-Safe | Block traffic on failure |
| Centralized Security | Active Directory / IAM |

---

## Threat Modeling (Critical for DFIR)

| Term | Meaning | Example |
|------|--------|--------|
| Vulnerability | Weakness | Unpatched system |
| Threat | Possible attack | Public exploit released |
| Risk | Impact + likelihood | Active exploitation in wild |

---

## Key Insight

Security concepts are **not theory** — they are:
- Detection logic
- Incident classification
- Investigation mindset

---

# Careers in Cyber

## Role Mapping (Important for YOU)

You are not “learning cyber” — you are positioning for:

**SOC Analyst → Incident Responder → DFIR**

---

## Blue Team Roles (Your Path)

### Security Analyst (Entry Point)
- Alert triage
- Log analysis
- SIEM usage  

### Incident Responder
- Active attack handling  
- Root cause analysis  
- Containment  

### Digital Forensics Examiner
- Evidence collection  
- Timeline reconstruction  
- Disk/memory forensics  

### Malware Analyst
- Reverse engineering  
- Behavior analysis  
- IOC extraction  

---

## Offensive Roles (Context Only)

- Penetration Tester → Finds vulnerabilities  
- Red Teamer → Simulates real attackers  

Useful to understand attacker mindset, not your core path.

---

## Key Insight

- Blue Team roles are **investigation-heavy**
- Strong overlap with:
  - Logs
  - Memory
  - Network traffic
- This directly aligns with your **CTF + FlareVM work**

---

# Training Impact on Teams

## Why This Actually Matters

This is not HR theory — this is:
**Why companies hire trained candidates over raw beginners**

---

## Real Impact

- Faster detection (MTTD ↓)
- Faster response (MTTR ↓)
- Fewer successful attacks  

---

## ROI Example (Important for Interviews)

- Training → 4% productivity increase  
- Leads to **massive ROI (400–600%)**

Translation:
> Skilled analysts = cheaper than breaches

---

## Enterprise Perspective

### Large Teams Need:
- Standardized training  
- Skill tracking  
- Custom modules  

### Tools:
- TryHackMe (Content Studio)
- Internal labs  

---

## Key Insight

Training =  
- Better detection  
- Better response  
- Better hiring decisions  

---

# Real-World Mapping (THIS is the important section)

| Concept | Where You Used It |
|--------|------------------|
| CIA | First Shift CTF (data access, logs) |
| Integrity | Log analysis / tampering detection |
| Process Monitoring | FlareVM (Procmon, Procexp) |
| Network Analysis | Wireshark investigations |
| Malware Behavior | PEStudio + FLOSS |

---

# Final Takeaways

- Security = **principles applied to real systems**
- Blue Team = **analysis + investigation + context**
- Training = **career acceleration multiplier**

---

# Personal Reflection

This module strengthened my understanding of:
- Core security principles (CIA, models, risk)
- Real-world Blue Team roles and workflows
- Importance of structured training in cybersecurity

It directly supports my progression toward:
**SOC Analyst → DFIR → Threat Intelligence**

---
