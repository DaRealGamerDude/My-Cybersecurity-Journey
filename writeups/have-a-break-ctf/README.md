# [Have a Break — KitKat Heist (TryHackMe)](https://tryhackme.com/room/haveabreak)

**Date Completed:** April 2026  
**Difficulty:** Easy–Medium  
**Platform:** TryHackMe  
**Focus Areas:** DFIR, SOC Analysis, Insider Threat Investigation, OSINT  

---

## Executive Summary

This write-up documents my investigation of the *Have a Break* CTF on TryHackMe, a scenario simulating a real-world cargo theft case involving insider involvement.

Unlike traditional CTFs focused on exploitation or isolated puzzles, this challenge required **multi-source correlation across email forensics, log analysis, image-based OSINT, and open-source intelligence pivoting**. The objective was not just to find answers, but to reconstruct an incident narrative — similar to how a SOC analyst or DFIR investigator would approach a real case.

Through this investigation, I:
- Performed **email header analysis** to identify anonymization infrastructure (VPN usage)
- Used **visual OSINT** to geolocate a real-world service station
- Conducted **log analysis** to detect insider data exfiltration
- Correlated **internal communications and system logs**
- Performed **OSINT pivoting** to uncover the real identity of the attacker

This CTF felt significantly closer to real investigative work compared to my previous experiences and highlighted both my strengths in structured analysis and my tendency to initially overlook secondary pivots.

<img width="1600" height="684" alt="image" src="ADD_SCREENSHOT_ROOM_OVERVIEW_HERE" />

---

## Personal Context — Why I Attempted This CTF

After completing a SOC-focused CTF earlier and identifying gaps in SIEM and log-based workflows, I wanted to attempt another investigation-style challenge — but this time one that emphasized **correlation across multiple data sources rather than tool-heavy analysis**.

This room stood out because it simulated a **real-world insider threat scenario**, something directly relevant to my long-term goal of working in **Blue Team / DFIR roles**.

I approached this CTF with a stricter mindset:
- No guessing
- No skipping reasoning
- Every answer must be backed by evidence

This write-up reflects that approach — including where I made incorrect assumptions and how I corrected them.

---

## Scenario Overview

The challenge revolves around the disappearance of a high-value Nestlé shipment during transit across Europe.

Initial intelligence suggests:
- The theft was **not opportunistic**
- The attackers had **prior knowledge of shipment details**
- The likely cause was **insider involvement within a logistics company**

As an investigator, the task was to analyze:
- An internal memo
- An anonymous email
- A dashcam image
- Employee records
- Access logs
- Internal communications

The goal: **identify the insider responsible for the leak and uncover their real identity**.

---

## Investigation Workflow

---

## Step 1 — Email Forensics (Exhibit A)

The first actionable artifact was an `.eml` file containing an anonymous tip.

Instead of reading the content, I focused on **email headers**, as they provide origin-level metadata.

### Key Finding

Received: from [193.32.249.132]

This revealed the **true sender IP address**.

### Analysis

- The IP did not belong to:
  - Google
  - A residential ISP
- WHOIS lookup showed:
  - **31173 Services Netherlands**

This infrastructure is commonly associated with **privacy-focused VPN providers**.

### Conclusion

The sender used:

**Mullvad VPN**

---

### Evidence

[ADD IMAGE: Email header showing origin IP]

---

## Step 2 — Image-Based OSINT (Exhibit B)

The next artifact was a dashcam image showing a petrol station.

### Key Observations

- Signboard:

Olomouc 27 km
Brno 45 km
D1

- Branding:
→ ORLEN petrol station  
- Language:
→ Czech  

### Analysis

- Located on **D1 highway (Czech Republic)**
- Between **Olomouc and Brno**
- Memo referenced:
→ Hulín region

Using these clues, I triangulated the exact location.

### Conclusion

**Kroměřížská 1281, 768 24 Hulín, Czechia**

---

### Evidence

[ADD IMAGE: Original dashcam image with annotations]

---

## Step 3 — Log Analysis (Insider Activity Detection)

The `access_log.csv` file was critical for identifying suspicious behavior.

### Focus

- Date: **March 25, 2026**
- Clue from memo:
→ unusual activity “night before departure”

### Key Log Entry

22:14:09  BR-0291  ROUTE_IT_PL_Q1_2026.pdf  EXPORT

### Analysis

- Late-night access → unusual
- Action:
  → **EXPORT (not VIEW)**
- File:
  → shipment route details

This strongly indicates **data exfiltration**.

---

### Conclusion

- Suspicious action time:
  **22:14:09**
- Primary suspect:
  **BR-0291**

---

### Evidence

[ADD IMAGE: Log snippet highlighting export event]

---

## Step 4 — Insider Attribution

Initially, I made an incorrect assumption:
- I thought the email sender = route planner (BR-0204)

This was wrong.

### Correction

From logs:
- **BR-0312** (Dispatch Operator)
  - Active late at night
  - Likely to observe anomalies

### Conclusion

- **Whistleblower:** BR-0312  
- **Leaker:** BR-0291  

---

### Key Lesson

> The observer of suspicious activity is not always the attacker.

---

## Step 5 — OSINT Pivot (Identity Discovery)

This was the hardest and most important part of the CTF.

### Initial Mistake

I focused only on:

notmyname2847@gmail.com

- OSINT tools → no results
- GitLab → dead end (login required)

### Breakthrough

From internal communications:

kraliknovak09@gmail.com

This was the **real pivot**.

---

### OSINT Process

- Searched:

kraliknovak09@gmail.com

- Found:
→ Google Maps profile

### Result

**Radovan Blšťák**

---

### Why This Worked

- Attacker used:
- VPN → anonymization
- Throwaway Gmail → anonymity
- But:
- Reused identity elsewhere → **weak link**

---

### Evidence

[ADD IMAGE: Google Maps profile showing name]

---

## Final Attribution

- **Whistleblower:** BR-0312  
- **Leaker:** BR-0291  
- **Culprit:**  

**Radovan Blšťák**

---

## Key Lessons Learned

- Email headers provide **true origin**, not the visible sender  
- Logs reveal behavior — **actions matter more than access**  
- Insider threats require **role + behavior correlation**  
- OSINT is about **pivoting when one path fails**  
- Most investigations fail due to **missed pivots, not lack of data**

---

## Where I Struggled

- Initially assumed:
→ attacker = email sender  
- Over-relied on:
→ external OSINT tools (Epieos)
- Ignored:
→ secondary pivot (second email in comms)

This led to a wrong answer before correcting course.

---

## What I’ll Improve Before the Next CTF

- Practice **multi-pivot OSINT workflows**
- Improve ability to:
→ identify **hidden clues inside datasets**
- Reduce reliance on tools when:
→ reasoning is sufficient
- Continue strengthening:
→ DFIR-style timeline reconstruction

---

## Tools & Techniques Used

- Email header analysis  
- WHOIS / IP intelligence  
- Visual OSINT (geolocation)  
- Log analysis  
- Username & email OSINT  
- Google Maps intelligence  

---

## Closing Note

This CTF felt significantly closer to real-world investigation than my previous challenges.

It reinforced that:
> Attackers don’t need to make big mistakes — just one small one.

And the investigator’s job is to find it.

This write-up reflects not just what I solved, but how I thought, where I failed, and how I corrected those mistakes — which is ultimately more valuable for my progression toward SOC and DFIR roles.
