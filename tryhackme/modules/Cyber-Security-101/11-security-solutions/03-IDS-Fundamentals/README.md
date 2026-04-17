# TryHackMe Room: IDS Fundamentals

**Path:** Security Solutions  
**Module Type:** Concept + Practical (Detection / Network Security)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Intrusion Detection Systems (IDS)**, a key defensive security solution used to detect malicious activity inside a network.

It covers:
- IDS purpose and limitations  
- Types of IDS (HIDS vs NIDS)  
- Detection methods (Signature vs Anomaly)  
- Snort IDS (rules + modes)  
- Real-world traffic analysis (PCAP)  

> IDS = **Detection only (NOT prevention)**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | IDS basics | ✔ |
| 2 | Types | IDS classifications | ✔ |
| 3 | Snort | IDS example | ✔ |
| 4 | Usage | Rules & commands | ✔ |
| 5 | Lab | PCAP investigation | ✔ |

---

# Key Concepts Covered

- IDS vs Firewall  
- HIDS vs NIDS  
- Signature vs anomaly detection  
- Snort rule structure  
- PCAP analysis  
- Detection logic  

---

# Room Notes & Task Breakdown

---

## Task 1: What Is an IDS

**Room Objective:**  
Understand the role of IDS.

---

### Q1: Can IDS prevent threats?

`Nay`

**Explanation:**  
IDS only detects and alerts — it does not block attacks.

---

### Key Learning

- Firewall = prevention  
- IDS = detection  

---

### Insight

> Firewall stops threats, IDS finds what slipped through

---

### Common Struggles

- Confusing IDS with IPS  
- Expecting IDS to block traffic  

---

## Task 2: Types of IDS

**Room Objective:**  
Understand IDS classifications.

---

### Q1: Detects across network?

`Network Intrusion Detection System`

**Explanation:**  
Monitors entire network traffic.

---

### Q2: Uses both detection methods?

`Hybrid IDS`

**Explanation:**  
Combines signature + anomaly detection.

---

### Deployment Types

| Type | Description |
|------|------------|
| HIDS | Host-level monitoring |
| NIDS | Network-wide monitoring |

---

### Detection Types

| Type | Description |
|------|------------|
| Signature-Based | Known attack patterns |
| Anomaly-Based | Deviations from baseline |
| Hybrid | Combination |

---

### Key Learning

- Signature = fast but limited  
- Anomaly = detects unknown but noisy  
- Hybrid = balanced approach  

---

### Insight

> Detection = trade-off between accuracy and coverage

---

### Common Struggles

- Not understanding false positives  
- Ignoring baseline behavior  

---

## Task 3: IDS Example — Snort

**Room Objective:**  
Understand Snort functionality.

---

### Q1: Mode for PCAP logging?

`Packet Logging Mode`

**Explanation:**  
Stores traffic for later analysis.

---

### Q2: Primary mode?

`Network Intrusion Detection System Mode`

**Explanation:**  
Real-time detection mode.

---

### Snort Modes

| Mode | Purpose |
|------|--------|
| Sniffer | View traffic |
| Logging | Save traffic |
| NIDS | Detect attacks |

---

### Key Learning

- Snort uses:
  - Rules  
  - Signatures  

---

### Insight

> Snort = rule-based detection engine

---

### Common Struggles

- Using wrong mode  
- Not understanding rule files  

---

## Task 4: Snort Usage

**Room Objective:**  
Understand rule creation and execution.

---

### Q1: Main Snort directory?

`/etc/snort`

**Explanation:**  
Stores configs and rules.

---

### Q2: Field for revision?

`rev`

**Explanation:**  
Tracks rule version.

---

### Q3: Protocol in sample rule?

`icmp`

**Explanation:**  
Used for ping detection.

---

### Q4: Custom rule file?

`local.rules`

**Explanation:**  
Used for user-defined rules.

---

### Rule Structure

```

action protocol src_ip src_port -> dest_ip dest_port (options)

````

---

### Example Rule

```bash
alert icmp any any -> 127.0.0.1 any (msg:"Ping Detected"; sid:10001; rev:1;)
````

---

### Rule Components

| Component   | Description   |
| ----------- | ------------- |
| Action      | alert/log     |
| Protocol    | TCP/UDP/ICMP  |
| Source      | IP/port       |
| Destination | IP/port       |
| msg         | Alert message |
| sid         | Unique ID     |
| rev         | Revision      |

---

### Run Snort

```bash
sudo snort -q -l /var/log/snort -i lo -A console -c /etc/snort/snort.conf
```

---

### Run on PCAP

```bash
sudo snort -q -l /var/log/snort -r file.pcap -A console -c /etc/snort/snort.conf
```

---

### Insight

> Rules = detection logic (like SIEM queries)

---

### Common Struggles

* Incorrect rule syntax
* Not understanding fields
* Ignoring rule tuning

---

## Task 5: Practical Lab

**Room Objective:**
Analyze PCAP traffic.

---

### Q1: SSH attacker IP?

`10.11.90.211`

**Explanation:**
Source of malicious SSH attempt.

---

### Q2: Other detected activity?

`Ping Detected`

**Explanation:**
ICMP traffic triggered rule.

---

### Q3: SID for SSH rule?

`1000002`

**Explanation:**
Unique identifier for detection rule.

---

### Key Learning

* IDS can analyze:

  * Real-time traffic
  * Historical PCAP

---

### Insight

> PCAP = goldmine for DFIR investigations

---

### Common Struggles

* Not correlating alerts
* Ignoring multiple detections

---

# Tools / Technologies Introduced

* Snort IDS
* PCAP files
* Network interfaces

---

# IDS Workflow Cheat Sheet

1. Traffic captured
2. Rules applied
3. Pattern match
4. Alert generated
5. Analyst investigates

---

# Reflection

This module is **critical for SOC + DFIR path**.

You now understand:

* How detection works
* How alerts are generated
* How network traffic is analyzed

---

### From a SOC / DFIR POV

* IDS alerts = early warning signals
* PCAP = evidence
* Rules = detection logic
