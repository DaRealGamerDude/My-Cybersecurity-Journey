# TryHackMe Module: Networking

**Path:** Cyber Security 101  
**Module Type:** Mixed (Theory + Hands-on)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This module introduces the fundamental principles of computer networking, beginning with theoretical networking models and progressing toward practical protocols and tools used across the Internet.

The module explores how data travels between systems, how devices automatically configure themselves on networks, and how different protocols work together to support services like web browsing, email, and file transfer.

Major areas covered include:

- Networking architecture models (OSI and TCP/IP)
- IP addressing and subnetting
- Transport protocols (TCP and UDP)
- Infrastructure protocols like DHCP, ARP, ICMP, and NAT
- Core Internet protocols such as DNS, HTTP, FTP, and SMTP
- Secure communication using TLS, SSH, and VPN
- Network traffic analysis using Wireshark and Tcpdump
- Host discovery and enumeration using Nmap

By the end of the module, I developed a foundational understanding of how packets move through networks, how protocols interact across layers, and how analysts can observe and investigate network traffic.

---

# Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|------|----------|--------------|--------|
| 1 | Networking Concepts | OSI model, TCP/IP stack, IP addressing | ✔ |
| 2 | Networking Essentials | DHCP, ARP, ICMP, Routing, NAT | ✔ |
| 3 | Networking Core Protocols | DNS, HTTP, FTP, Email protocols | ✔ |
| 4 | Networking Secure Protocols | TLS, HTTPS, SSH, VPN | ✔ |
| 5 | Wireshark: The Basics | Packet analysis | ✔ |
| 6 | Tcpdump: The Basics | CLI packet capture | ✔ |
| 7 | Nmap: The Basics | Network discovery and scanning | ✔ |

---

# Key Concepts Covered

- Network Architecture Models (OSI and TCP/IP)
- Network Communication (TCP, UDP)
- Network Infrastructure (DHCP, ARP, ICMP, NAT)
- Internet Application Protocols
- Network Security (TLS, SSH)
- Traffic Analysis

---

# Room Notes & Task Breakdown

---

## 🔹 Room: Networking Concepts

**Room Objective:**  
Introduce the fundamental theoretical models and protocols that form the basis of modern networking.

---

### Key Learning

- Understanding network communication models  
- Identifying transport protocols  
- Understanding IP addressing  
- Learning how packets travel through networks  

---

### Task 1: Introduction

Introduces the structure of the networking module and explains how networking concepts will be explored across multiple rooms.

---

### Task 2: OSI Model

The OSI (Open Systems Interconnection) model is a conceptual framework developed by ISO to standardize network communication.

| Layer | Name | Function |
|------|------|----------|
| 7 | Application | Provides services to applications |
| 6 | Presentation | Data encoding, compression, encryption |
| 5 | Session | Session establishment and synchronization |
| 4 | Transport | End-to-end communication |
| 3 | Network | Logical addressing and routing |
| 2 | Data Link | Communication within the same network segment |
| 1 | Physical | Transmission of electrical or wireless signals |

Mnemonic:

```

Please Do Not Throw Spinach Pizza Away

```

---

### Task 3: TCP/IP Model

| TCP/IP Layer | Corresponding OSI Layers |
|-------------|--------------------------|
| Application | OSI Layers 5–7 |
| Transport | OSI Layer 4 |
| Internet | OSI Layer 3 |
| Link | OSI Layer 2 |
| Physical | OSI Layer 1 |

---

### Task 4: IP Addresses and Subnets

Example IPv4:

```

192.168.1.1

```

Subnet mask:

```

255.255.255.0

```

CIDR:

```

/24

```

---

### Private IP Address Ranges

| Range | CIDR |
|------|------|
| 10.0.0.0 – 10.255.255.255 | /8 |
| 172.16.0.0 – 172.31.255.255 | /12 |
| 192.168.0.0 – 192.168.255.255 | /16 |

---

### Task 5: UDP and TCP

**UDP**

- Connectionless  
- Fast  
- No delivery guarantee  

Use cases:

- DNS  
- VoIP  
- Streaming  

---

**TCP**

- Connection-oriented  
- Reliable  
- Guarantees delivery  

Handshake:

```

SYN → SYN-ACK → ACK

```

---

### Task 6: Encapsulation

Process:

1. Application generates data  
2. Transport layer adds TCP/UDP header  
3. Network layer adds IP header  
4. Data link layer adds Ethernet header  

Structure:

```

Application Data → TCP Segment → IP Packet → Ethernet Frame

```

---

### Task 7: Telnet

Example:

```

telnet MACHINE_IP 7

```

Example HTTP request:

```

GET / HTTP/1.1
Host: telnet.thm

```

---

## 🔹 Room: Networking Essentials

**Room Objective:**  
Introduce the infrastructure protocols responsible for automatically configuring and maintaining network communication.

---

### Task 2: DHCP

Operates on:

```

UDP 67, 68

```

#### DHCP Process (DORA)

| Step | Description |
|------|------------|
| Discover | Client broadcasts request |
| Offer | Server offers IP |
| Request | Client requests IP |
| Acknowledge | Server confirms |

---

### Task 3: ARP

Example:

```

Who has 192.168.66.1?
192.168.66.1 is-at 44:df:65:d8:fe:6c

```

---

### Task 4: ICMP

**Ping**

```

ping 192.168.1.1

```

**Traceroute**

```

traceroute example.com

```

---

### Task 5: Routing

| Protocol | Description |
|---------|------------|
| OSPF | Link-state routing |
| EIGRP | Cisco proprietary |
| BGP | Internet backbone |
| RIP | Distance-vector |

---

### Task 6: NAT

Example:

```

192.168.0.129 → 212.3.4.5

```

---

## 🔹 Room: Networking Core Protocols

**Room Objective:**  
Introduce core application-layer protocols used across Internet services.

---

### Task 1: DNS

Example:

```

google.com → 142.250.183.142

```

#### DNS Record Types

| Type | Purpose |
|------|--------|
| A | IPv4 mapping |
| AAAA | IPv6 mapping |
| CNAME | Alias |
| MX | Mail server |
| TXT | Verification |

---

### Task 2: WHOIS

```

whois example.com

```

---

### Task 3: HTTP

Default port:

```

80

```

#### Methods

| Method | Purpose |
|--------|--------|
| GET | Retrieve data |
| POST | Submit data |
| PUT | Update |
| DELETE | Remove |

---

#### Status Codes

| Code | Meaning |
|------|--------|
| 200 | Success |
| 301 | Redirect |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Server Error |

---

### Task 4: HTTPS

Port:

```

443

```

Provides:

- Encryption  
- Integrity  
- Authentication  

---

### Task 5: FTP

Port:

```

21

```

#### Commands

| Command | Function |
|--------|---------|
| USER | Username |
| PASS | Password |
| LIST | List files |
| RETR | Download |
| STOR | Upload |

---

### Task 6: Email Protocols

| Protocol | Port | Secure Port |
|---------|------|------------|
| SMTP | 25 | 465 / 587 |
| POP3 | 110 | 995 |
| IMAP | 143 | 993 |

---

## 🔹 Room: Networking Secure Protocols

**Room Objective:**  
Introduce protocols that secure communication.

---

### Task 1: TLS

| Property | Description |
|----------|------------|
| Confidentiality | Encryption |
| Integrity | No tampering |
| Authentication | Verified identity |

---

### Task 2: Secure Email Protocols

| Protocol | Secure Port |
|---------|-------------|
| SMTPS | 465 / 587 |
| POP3S | 995 |
| IMAPS | 993 |

---

### Task 3: SSH

```

ssh username@host

```

Port:

```

22

```

---

### Task 4: SFTP vs FTPS

| Protocol | Port | Description |
|---------|------|------------|
| SFTP | 22 | Over SSH |
| FTPS | 990 | FTP + TLS |

---

### Task 5: VPN

Examples:

- OpenVPN  
- WireGuard  
- IPSec  

---

## 🔹 Room: Wireshark: The Basics

**Room Objective:**  
Introduce Wireshark for packet analysis.

---

### Packet Structure

| Layer | Information |
|------|------------|
| Ethernet | MAC addresses |
| IP | IP addresses |
| TCP | Ports, sequence |
| Application | Data |

---

### Filters

```

http
tcp.port == 80
ip.addr == 192.168.1.10
dns

```

---

## 🔹 Room: Tcpdump: The Basics

**Room Objective:**  
Introduce CLI packet capture.

---

### Commands

```

tcpdump -i eth0
tcpdump -w capture.pcap
tcpdump -r capture.pcap
tcpdump host 192.168.1.1
tcpdump port 80
tcpdump tcp
tcpdump udp

```

---

## 🔹 Room: Nmap: The Basics

**Room Objective:**  
Introduce network scanning and enumeration.

---

### Commands

```

nmap -sn 192.168.1.0/24
nmap target_ip
nmap -sS target_ip
nmap -sV target_ip
nmap -O target_ip
nmap -A target_ip

```

---

# Tools / Technologies Used in This Module

| Tool | Purpose |
|------|--------|
| Wireshark | Packet analysis |
| Tcpdump | CLI packet capture |
| Nmap | Network scanning |
| Telnet | Manual testing |
| Nslookup | DNS queries |
| Whois | Domain lookup |

---

# 📌 Commands, Syntax & Patterns to Remember

| Command | Purpose |
|--------|--------|
| ipconfig | Windows network config |
| ifconfig | Linux network config |
| ip a | Linux IP info |
| ping | Connectivity |
| traceroute | Path tracing |
| telnet | Manual connection |
| nslookup | DNS query |
| whois | Domain info |
| ssh | Remote login |
| tcpdump | Packet capture |
| nmap | Network scanning |

---

# 📌 Common Ports, Protocols & Their Usage

*(Kept exactly as-is, already perfect — no formatting fix needed beyond table cleanup)*

---

# Port Ranges

| Range | Name | Usage |
|------|------|------|
| 0–1023 | Well-known | Standard services |
| 1024–49151 | Registered | Applications |
| 49152–65535 | Ephemeral | Client ports |

---

# Key Patterns

### 1. “Add S = Secure”

| Insecure | Secure |
|---------|--------|
| HTTP (80) | HTTPS (443) |
| FTP (21) | FTPS (990) |
| SMTP (25) | SMTPS |
| POP3 (110) | POP3S |
| IMAP (143) | IMAPS |

---

### 2. SSH Replacements

| Old | New |
|-----|-----|
| Telnet (23) | SSH (22) |
| FTP (21) | SFTP (22) |

---

### 3. High-Signal Ports (SOC / CTF)

- 22 → SSH  
- 80 → HTTP  
- 443 → HTTPS  
- 21 → FTP  
- 25 → SMTP  
- 53 → DNS  
- 110 / 143 → Email  
- 445 → SMB  
- 3389 → RDP  

---

### Investigation-Relevant Ports

| Port | Why it matters |
|------|--------------|
| 22 | SSH brute-force |
| 3389 | RDP attacks |
| 445 | SMB exploits |
| 53 | DNS tunneling |
| 80/443 | Malware beaconing |
| 21 | FTP misconfig |
| 25 | Phishing infra |

---

# Reflection

This module provided a strong foundation in networking concepts essential for cybersecurity. It covered theoretical models, real-world protocols, and practical tools used for traffic analysis and network investigation.

The combination of protocol understanding and hands-on tools such as Wireshark, Tcpdump, and Nmap builds a base for:
- Network traffic analysis  
- Threat detection  
- Incident response  
- Security monitoring  
---
