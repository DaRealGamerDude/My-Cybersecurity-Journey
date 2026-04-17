# TryHackMe Room: Firewall Fundamentals

**Path:** Security Solutions  
**Module Type:** Concept + Practical (Network Security)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Firewalls**, a core defensive security solution used to control network traffic.

It covers:
- Firewall purpose  
- Types of firewalls  
- Rule structure and logic  
- Windows Defender Firewall  
- Linux firewall (iptables / ufw)  

> Firewall = **Traffic Control → Allow / Deny / Forward**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Purpose | Firewall basics | ✔ |
| 2 | Types | Firewall types | ✔ |
| 3 | Rules | Rule structure | ✔ |
| 4 | Windows | Defender Firewall | ✔ |
| 5 | Linux | iptables / ufw | ✔ |

---

# Key Concepts Covered

- Packet filtering  
- OSI layer-based firewalls  
- Stateful vs stateless filtering  
- Firewall rule components  
- Traffic direction (inbound/outbound)  
- Practical firewall configuration  

---

# Room Notes & Task Breakdown

---

## Task 1: Purpose of Firewall

**Room Objective:**  
Understand what a firewall does.

---

### Q1: Which solution inspects traffic?

`Firewall`

**Explanation:**  
Controls incoming and outgoing network traffic based on rules.

---

### Key Learning

- Firewall acts like:
  - Security guard for network  
- Controls:
  - Incoming traffic  
  - Outgoing traffic  

---

### Insight

> Firewall = first line of defense

---

### Common Struggles

- Thinking firewall = antivirus  
- Ignoring outbound traffic control  

---

## Task 2: Types of Firewalls

**Room Objective:**  
Understand different firewall types.

---

### Q1: Tracks connection state?

`stateful firewall`

**Explanation:**  
Maintains session information.

---

### Q2: Uses heuristic analysis?

`next-generation firewall`

**Explanation:**  
Detects advanced threats.

---

### Q3: Inspects application-level traffic?

`proxy firewall`

**Explanation:**  
Works at Layer 7.

---

### Firewall Types

| Type | Characteristics |
|------|---------------|
| Stateless | Fast, no memory |
| Stateful | Tracks connections |
| Proxy | Inspects content |
| NGFW | Advanced detection |

---

### Key Learning

- Stateless = fast but limited  
- Stateful = smarter filtering  
- Proxy = deep inspection  
- NGFW = enterprise-level security  

---

### Insight

> More inspection = more security (but slower)

---

### Common Struggles

- Confusing stateless vs stateful  
- Ignoring OSI layer differences  

---

## Task 3: Firewall Rules

**Room Objective:**  
Understand how rules work.

---

### Q1: Action to permit traffic?

`allow`

**Explanation:**  
Permits defined traffic.

---

### Q2: Rule for outgoing traffic?

`outbound`

**Explanation:**  
Applies to traffic leaving network.

---

### Rule Components

| Component | Description |
|----------|------------|
| Source | Sender IP |
| Destination | Receiver IP |
| Port | Service port |
| Protocol | TCP/UDP |
| Action | Allow / Deny / Forward |
| Direction | Inbound / Outbound |

---

### Rule Actions

| Action | Meaning |
|--------|--------|
| Allow | Permit traffic |
| Deny | Block traffic |
| Forward | Redirect traffic |

---

### Example Rule

Allow HTTP traffic:

| Action | Source | Destination | Port | Direction |
|--------|--------|------------|------|----------|
| Allow | Internal | Any | 80 | Outbound |

---

### Insight

> Misconfigured rules = security failure

---

### Common Struggles

- Not understanding rule priority  
- Over-permissive configurations  

---

## Task 4: Windows Defender Firewall

**Room Objective:**  
Understand Windows firewall configuration.

---

### Key Concepts

- Built-in firewall in Windows  
- Uses:
  - Inbound rules  
  - Outbound rules  

---

### Network Profiles

| Profile | Usage |
|--------|------|
| Private | Home network |
| Public | Untrusted network |

---

### Lab Answers

---

### Q1: Rule blocking SSH?

`Core Op`

**Explanation:**  
Blocks incoming SSH traffic.

---

### Q2: Rule allowing SSH?

`Infra team`

**Explanation:**  
Allows SSH from specific IP.

---

### Q3: Allowed IP?

`192.168.13.7`

**Explanation:**  
Whitelisted source.

---

### Key Learning

- Rules can:
  - Block all traffic  
  - Allow specific exceptions  

---

### Insight

> Default deny + allow exceptions = best practice

---

### Common Struggles

- Allowing too much traffic  
- Not using profiles properly  

---

## Task 5: Linux Firewall (iptables / ufw)

**Room Objective:**  
Understand Linux firewall basics.

---

### Q1: Successor of iptables?

`nftables`

**Explanation:**  
Modern firewall utility.

---

### Q2: Deny all outgoing rule?

`ufw default deny outgoing`

**Explanation:**  
Blocks all outbound traffic by default.

---

### Key Tools

| Tool | Description |
|------|------------|
| Netfilter | Core framework |
| iptables | Advanced control |
| nftables | Improved version |
| ufw | Beginner-friendly |

---

### Common Commands

Enable firewall:

```bash
sudo ufw enable
````

Check status:

```bash
sudo ufw status
```

Deny SSH:

```bash
sudo ufw deny 22/tcp
```

Allow outgoing:

```bash
sudo ufw default allow outgoing
```

---

### Insight

> ufw = simplified iptables

---

### Common Struggles

* Misconfiguring default policies
* Locking yourself out (SSH rules)

---

# Tools / Technologies Introduced

* Windows Defender Firewall
* Netfilter
* iptables
* nftables
* ufw

---

# Firewall Workflow Cheat Sheet

1. Traffic arrives
2. Firewall checks rules
3. Match found
4. Action applied:

   * Allow
   * Deny
   * Forward

---

# Reflection

This module strengthens your **network-level defensive understanding**.

You now understand:

* How traffic is controlled
* How rules are structured
* How real systems enforce security

---

### From a SOC / DFIR POV

* Firewall logs = network evidence
* Blocked traffic = potential attack
* Allowed traffic = must be monitored
