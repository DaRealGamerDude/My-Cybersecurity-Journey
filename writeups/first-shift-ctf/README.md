# TryHackMe — First Shift CTF (First CTF Attempt)

**Date Completed:**  
**Difficulty:** Medium  
**Platform:** TryHackMe  
**Focus Areas:** SOC Operations, Threat Intelligence, Malware Analysis  


## Executive Summary

This write-up documents my first attempt at a SOC-focused Capture The Flag (CTF) on TryHackMe. At the time, my cybersecurity experience was limited to foundational learning (networking, Linux, Windows security, and web fundamentals), and this CTF was an intentional step into unguided, real-world-style problem solving.

I successfully investigated Tasks 3–5, which focused on alert triage, infrastructure-based threat intelligence, and malware identification, applying SOC-style reasoning rather than exploit-driven approaches. Tasks 6–8 were not attempted due to insufficient hands-on experience with tools such as SIEMs and packet analysis, which were identified as clear skill gaps.

This CTF served as a baseline assessment of my current capabilities and confirmed my interest in defensive security and incident response, while clearly highlighting the areas I need to strengthen before progressing further.

---

## Personal Context — Why I Attempted This CTF

This was my first Capture The Flag (CTF) challenge.

At the time of attempting this room, my cybersecurity experience was still at a foundational stage. I had completed TryHackMe’s Pre-Security path and had just started Cyber Security 101. Most of my learning so far had focused on understanding core concepts—networking, Linux, Windows security, and web fundamentals—rather than hands-on work with SIEMs, packet analysis tools, or advanced threat intelligence platforms.

I chose to attempt a medium-difficulty, SOC-focused CTF deliberately. I wanted to experience what cybersecurity feels like when the learning wheels come off: when problems are ambiguous, tools are unfamiliar, and answers require reasoning rather than step-by-step guidance.

This write-up reflects that first exposure honestly. It documents what I was able to investigate, where I struggled, and what this experience clarified about my current skill level and learning priorities as I move toward SOC and DFIR-oriented roles.

---

## Scenario Overview

This room simulates a SOC analyst’s first shift, beginning with a suspicious VPN login alert and gradually expanding into a broader investigation involving infrastructure analysis and malware identification.

The investigation emphasizes real-world SOC workflows such as alert validation, infrastructure context building, and threat intelligence correlation, rather than exploit development or offensive techniques.

---

## Scope of Attempt

- **Tasks Attempted:** 3, 4, and 5  
- **Tasks Not Attempted:** 6, 7, and 8  

Tasks 3–5 aligned with my current knowledge level and allowed me to reason through alerts, infrastructure patterns, and malware context. Tasks 6–8 required hands-on proficiency with tools such as Splunk and Wireshark, which I had not yet learned in sufficient depth. Rather than guessing or copying answers, I chose to stop and treat these as clear skill gaps to address.

---

## Task 3 — Initial Alert Triage (Suspicious VPN Login)

The investigation began with a SOC alert indicating an unusual VPN login for a legitimate user from an unexpected geographic location. While this initially resembled a classic compromised-credentials scenario, the task required careful validation rather than immediate escalation.

The analysis focused on understanding whether the login context was plausible, validating the user’s activity, and examining the source IP to determine whether the infrastructure showed signs of abuse. This task highlighted how alerts represent *signals*, not conclusions, and how premature assumptions can lead to incorrect incident classification.

The most important takeaway from this task was learning that effective alert triage depends on eliminating false positives as much as identifying real threats. User confirmation, infrastructure ownership, and contextual indicators all play a role before labeling activity as malicious.

---

## Task 4 — IP Intelligence and Infrastructure Context

Task 4 expanded the investigation into infrastructure-level analysis using threat intelligence concepts. Instead of relying on a single IP reputation score, the task emphasized examining broader patterns such as ASN ownership, hosting provider behavior, and passive DNS relationships.

This task shifted my perspective from asking whether an IP was “bad” to understanding whether the underlying infrastructure showed consistent signs of malicious reuse. It became clear that attackers often rely on the same hosting environments, domain registration patterns, and ASNs across multiple campaigns.

The key learning here was that infrastructure context provides stronger investigative signals than isolated indicators. Threat intelligence adds value by offering historical and relational context, not definitive answers.

---

## Task 5 — Malware Identification and Contextual Analysis

Task 5 transitioned the investigation into malware analysis, but in a way that closely mirrors real SOC workflows. Rather than reverse engineering the binary, the task focused on identifying the malware through hash-based analysis, vendor detections, and threat intelligence correlation.

Using the file’s cryptographic hash, the malware was identified as **Lumma Stealer (LummaC2)**, a widely used information stealer commonly distributed through a Malware-as-a-Service (MaaS) model. This introduced the concept that modern malware campaigns are often run by affiliates operating within shared ecosystems rather than single threat actors.

This task reinforced that malware identification is not an isolated activity. Understanding the malware’s distribution model, affiliate behavior, and infrastructure reuse is critical for detection engineering, incident scoping, and long-term defensive strategy.

---

## Tasks 6–8 — Not Attempted (Identified Skill Gaps)

Tasks 6, 7, and 8 required active use of advanced tools and datasets, including SIEM querying with Splunk, packet analysis with Wireshark, and deeper threat intelligence report correlation.

At the time of this CTF, I did not have sufficient hands-on experience with these tools to perform meaningful analysis under time constraints. Rather than forcing incorrect conclusions, I chose to stop and treat these tasks as indicators of what I need to learn next.

This decision itself was a learning outcome: recognizing when tool fluency, rather than analytical reasoning, is the limiting factor.

---

## Tools & Platforms Used

- TryHackMe  
- Built-in threat intelligence tooling within the room  
- Malware hash analysis and vendor detection platforms  
- MITRE ATT&CK Framework  

---

## Key Lessons Learned

- SOC investigations are driven by questions, not tools  
- Infrastructure patterns often provide stronger signals than single indicators  
- Malware analysis in SOC contexts is about context and behavior, not reverse engineering  
- Tool fluency (SIEMs, packet analysis) is critical and cannot be skipped  
- Knowing when to stop is better than forcing incorrect answers  

---

## What Will Change Before the Next CTF

Before attempting another SOC-focused CTF, I plan to focus on:
- Building a clear mental model of SIEM workflows and query-driven investigation  
- Gaining hands-on experience with Wireshark and basic PCAP analysis  
- Practicing timeline reconstruction and log correlation in controlled lab environments  

This CTF confirmed my interest in defensive security and incident response, while clearly highlighting the areas I need to strengthen before progressing further.

---

## References

- TryHackMe — First Shift CTF  
- MITRE ATT&CK Framework  
- Threat intelligence reports referenced within the room  
