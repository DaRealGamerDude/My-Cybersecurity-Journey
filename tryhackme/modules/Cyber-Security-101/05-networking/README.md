
# TryHackMe Module: Networking

**Path**: Cyber Security 101
**Module Type**: Mixed
**Difficulty**: Beginner
**Status: Completed

---

📘 Module Overview

This module introduces the fundamental principles of computer networking, beginning with theoretical networking models and progressing toward practical protocols and tools used across the Internet.

The module explores how data travels between systems, how devices automatically configure themselves on networks, and how different protocols work together to support services like web browsing, email, and file transfer.

Major areas covered include:
	•	Networking architecture models (OSI and TCP/IP)
	•	IP addressing and subnetting
	•	Transport protocols (TCP and UDP)
	•	Infrastructure protocols like DHCP, ARP, ICMP, and NAT
	•	Core Internet protocols such as DNS, HTTP, FTP, and SMTP
	•	Secure communication using TLS, SSH, and VPN
	•	Network traffic analysis using Wireshark and Tcpdump
	•	Host discovery and enumeration using Nmap

By the end of the module, I developed a foundational understanding of how packets move through networks, how protocols interact across layers, and how analysts can observe and investigate network traffic.

---

🗂️ Rooms in This Module

Order	Room Name	Primary Focus	Status
1	Networking Concepts	OSI model, TCP/IP stack, IP addressing	✔
2	Networking Essentials	DHCP, ARP, ICMP, Routing, NAT	✔
3	Networking Core Protocols	DNS, HTTP, FTP, Email protocols	✔
4	Networking Secure Protocols	TLS, HTTPS, SSH, VPN	✔
5	Wireshark: The Basics	Packet analysis	✔
6	Tcpdump: The Basics	CLI packet capture	✔
7	Nmap: The Basics	Network discovery and scanning	✔


⸻

🧠 Key Concepts Covered (Module-Level)

Network Architecture Models

Understanding the OSI model and TCP/IP model that describe how networking protocols operate across layered architectures.

Network Communication

How devices exchange data through transport protocols such as TCP and UDP.

Network Infrastructure

Protocols that automatically configure and maintain network communication such as DHCP, ARP, ICMP, and NAT.

Internet Application Protocols

Protocols that enable web browsing, file transfer, and email communication.

Network Security

How encryption protocols like TLS and SSH protect network traffic.

Traffic Analysis

Capturing and inspecting packets to investigate network behavior.

⸻

🔍 Room Notes & Task Breakdown

⸻

🔹 Room: Networking Concepts

Room Objective

Introduce the fundamental theoretical models and protocols that form the basis of modern networking.

This room explains how data moves across networks using layered architecture and introduces concepts like IP addressing, TCP/UDP communication, and packet encapsulation.

⸻

Task 1: Introduction

This task introduces the structure of the networking module and explains how networking concepts will be explored across multiple rooms.

Key learning goals include:
	•	Understanding network communication models
	•	Identifying transport protocols
	•	Understanding IP addressing
	•	Learning how packets travel through networks

⸻

Task 2: OSI Model

The OSI (Open Systems Interconnection) model is a conceptual framework developed by ISO to standardize network communication.

It divides communication into seven layers, each responsible for a specific function.

Layer	Name	Function
7	Application	Provides services to applications
6	Presentation	Data encoding, compression, encryption
5	Session	Session establishment and synchronization
4	Transport	End-to-end communication
3	Network	Logical addressing and routing
2	Data Link	Communication within the same network segment
1	Physical	Transmission of electrical or wireless signals

Mnemonic to remember the layers:

Please Do Not Throw Spinach Pizza Away

⸻

Task 3: TCP/IP Model

The TCP/IP model simplifies the OSI model into fewer layers.

TCP/IP Layer	Corresponding OSI Layers
Application	OSI Layers 5–7
Transport	OSI Layer 4
Internet	OSI Layer 3
Link	OSI Layer 2
Physical	OSI Layer 1

This model represents the actual architecture used on the Internet.

---

Task 4: IP Addresses and Subnets

Each device on a network requires a unique identifier called an IP address.

Example IPv4 address:

192.168.1.1

IPv4 characteristics:
	•	32 bits
	•	4 octets
	•	Each octet ranges from 0–255

Example subnet mask:

255.255.255.0

CIDR representation:

/24

Meaning the first 24 bits identify the network.

⸻

Private IP Address Ranges

Defined in RFC 1918

Range	CIDR
10.0.0.0 – 10.255.255.255	/8
172.16.0.0 – 172.31.255.255	/12
192.168.0.0 – 192.168.255.255	/16

Private IPs are used inside local networks and require NAT to communicate with the public Internet.

⸻

Task 5: UDP and TCP

Transport layer protocols allow communication between processes running on networked hosts.

UDP (User Datagram Protocol)

Characteristics:
	•	Connectionless
	•	Fast
	•	No delivery guarantee

Common use cases:
	•	DNS
	•	VoIP
	•	Streaming

⸻

TCP (Transmission Control Protocol)

Characteristics:
	•	Connection-oriented
	•	Reliable
	•	Guarantees packet delivery

TCP establishes connections using the three-way handshake.

SYN → SYN-ACK → ACK

Each packet is assigned a sequence number to detect lost packets.

⸻

Task 6: Encapsulation

Encapsulation describes how each networking layer adds its own header to the data.

Process:
	1.	Application generates data
	2.	Transport layer adds TCP/UDP header
	3.	Network layer adds IP header
	4.	Data link layer adds Ethernet header

Final structure:

Application Data
→ TCP Segment
→ IP Packet
→ Ethernet Frame

The receiving system reverses this process through decapsulation.

⸻

Task 7: Telnet

Telnet is a protocol used for remote terminal connections.

Although historically used for remote administration, it sends data in plaintext, making it insecure.

Example telnet connection:

telnet MACHINE_IP 7

Demonstrated servers included:

Echo Server (Port 7)
Daytime Server (Port 13)
HTTP Server (Port 80)

Example HTTP request sent manually via telnet:

GET / HTTP/1.1
Host: telnet.thm

This exercise demonstrates how HTTP communication works internally.

⸻

🔹 Room: Networking Essentials

Room Objective

Introduce the infrastructure protocols responsible for automatically configuring and maintaining network communication.

These protocols enable devices to discover network settings, resolve hardware addresses, diagnose connectivity issues, and route packets between networks.

⸻

Task 2: DHCP

Dynamic Host Configuration Protocol automatically assigns network settings to devices joining a network.

Required network parameters include:
	•	IP address
	•	Subnet mask
	•	Gateway
	•	DNS server

DHCP operates over UDP ports 67 and 68.

⸻

DHCP Process (DORA)

Step	Description
Discover	Client broadcasts request for DHCP server
Offer	Server offers an available IP address
Request	Client requests offered IP
Acknowledge	Server confirms assignment

This automated configuration prevents IP conflicts.

⸻

Task 3: ARP

Address Resolution Protocol maps IP addresses to MAC addresses within local networks.

Example ARP request:

Who has 192.168.66.1?

Example ARP reply:

192.168.66.1 is-at 44:df:65:d8:fe:6c

ARP packets are not encapsulated inside IP packets and are transmitted directly within Ethernet frames.

⸻

Task 4: ICMP

Internet Control Message Protocol is used for network diagnostics and error reporting.

Two commonly used commands rely on ICMP.

Ping

Tests network connectivity and measures round-trip time.

Example:

ping 192.168.1.1


⸻

Traceroute

Identifies the path packets take to reach a destination.

Example:

traceroute example.com

Traceroute relies on the TTL field in the IP header.

Each router decreases TTL by 1.

When TTL reaches zero, the router sends an ICMP Time Exceeded message.

⸻

Task 5: Routing

Routers forward packets between networks.

Routing protocols determine optimal paths.

Examples:

Protocol	Description
OSPF	Link-state routing protocol
EIGRP	Cisco proprietary routing protocol
BGP	Internet backbone routing protocol
RIP	Distance-vector routing protocol


⸻

Task 6: NAT

Network Address Translation allows multiple private devices to share a single public IP address.

Example translation:

192.168.0.129 → 212.3.4.5

The router maintains a translation table mapping internal connections to external addresses.

This technique significantly reduces public IPv4 address usage.

⸻

If you want, I’ll immediately send Part 2 next, which covers:
	•	Networking Core Protocols
	•	Networking Secure Protocols
	•	Wireshark
	•	Tcpdump
	•	Nmap

and then finish with a large Linux vs Windows command comparison table so the documentation stays consistent with your repo style.
Good. We continue exactly where Part 1 ended, without repeating headers and without breaking your structure. Same template, same depth, no shortcuts.

Below is PART 2 (continuation) covering:
	•	Networking Core Protocols
	•	Networking Secure Protocols

Part 3 will contain Wireshark, Tcpdump, Nmap, tools, and the full command comparison tables.

Everything remains copy-paste GitHub Markdown.

⸻

🔹 Room: Networking Core Protocols

Room Objective

This room introduces the core application-layer protocols that power most Internet services, including web communication, file transfer, and email systems.

Understanding these protocols is critical because they form the majority of observable traffic in network monitoring and incident response investigations.

⸻

Task 1: DNS (Domain Name System)

DNS is responsible for translating human-readable domain names into IP addresses.

Example:

google.com → 142.250.183.142

Without DNS, users would need to memorize IP addresses to access websites.

⸻

DNS Record Types

Record Type	Purpose
A	Maps domain to IPv4 address
AAAA	Maps domain to IPv6 address
CNAME	Alias for another domain
MX	Mail server responsible for email
TXT	Arbitrary text records (often used for verification)


⸻

DNS Query Example

DNS lookup command:

nslookup example.com

Result typically includes:
	•	Resolved IP address
	•	DNS server used
	•	Response status

⸻

Security Relevance

DNS is frequently abused for:
	•	Malware command-and-control
	•	Data exfiltration
	•	Domain generation algorithms (DGAs)
	•	DNS tunneling

SOC analysts frequently monitor suspicious DNS queries during investigations.

⸻

Task 2: WHOIS

WHOIS is a protocol used to retrieve domain registration information.

Example command:

whois example.com

Information returned may include:
	•	Domain registrar
	•	Registration date
	•	Expiration date
	•	Registrant contact details
	•	Name servers

⸻

Security Relevance

WHOIS information helps investigators:
	•	Identify suspicious domains
	•	Investigate phishing infrastructure
	•	Determine domain ownership patterns

Threat intelligence teams frequently correlate WHOIS data with malicious domains.

⸻

Task 3: HTTP (Hypertext Transfer Protocol)

HTTP is the protocol used for communication between web browsers and web servers.

Default port:

80


⸻

HTTP Request Example

GET /index.html HTTP/1.1
Host: example.com

Components:
	•	Method
	•	Resource
	•	HTTP version
	•	Headers

⸻

Common HTTP Methods

Method	Purpose
GET	Retrieve data
POST	Submit data
PUT	Update resource
DELETE	Remove resource


⸻

HTTP Response Example

HTTP/1.1 200 OK
Content-Type: text/html

Status codes indicate result of the request.

⸻

Common HTTP Status Codes

Code	Meaning
200	Success
301	Redirect
403	Forbidden
404	Not Found
500	Server Error


⸻

Security Relevance

HTTP traffic analysis is essential in:
	•	Web exploitation investigations
	•	Malware beaconing detection
	•	Suspicious file downloads
	•	Phishing analysis

⸻

Task 4: HTTPS

HTTPS is simply HTTP over TLS encryption.

Default port:

443

HTTPS provides:
	•	Encryption
	•	Integrity
	•	Authentication

When connecting to HTTPS websites, browsers perform a TLS handshake before transmitting encrypted HTTP data.

⸻

TLS Certificates

Certificates verify the identity of servers.

Certificates are issued by Certificate Authorities (CAs).

Example CAs include:
	•	DigiCert
	•	GlobalSign
	•	Let’s Encrypt

⸻

Security Relevance

TLS encryption protects users from:
	•	Man-in-the-middle attacks
	•	Credential interception
	•	Data tampering

However, attackers can still abuse HTTPS for encrypted malware traffic.

⸻

Task 5: FTP (File Transfer Protocol)

FTP is used to transfer files between systems.

Default port:

21


⸻

FTP Workflow
	1.	Client connects to server
	2.	Authenticates using username/password
	3.	Transfers files

⸻

Common FTP Commands

Command	Function
USER	Specify username
PASS	Provide password
LIST	Display files
RETR	Download file
STOR	Upload file


⸻

Security Issues

FTP transmits credentials in plaintext, making it insecure.

Modern alternatives include:
	•	SFTP
	•	FTPS

⸻

Task 6: Email Protocols

Email systems rely on three major protocols.

⸻

SMTP (Simple Mail Transfer Protocol)

Used to send email.

Default port:

25

Also used with encryption:

587
465


⸻

POP3 (Post Office Protocol)

Used to retrieve email from servers.

Default port:

110

Secure version:

995

POP3 downloads messages locally and may delete them from the server.

⸻

IMAP (Internet Message Access Protocol)

IMAP synchronizes emails between client and server.

Default port:

143

Secure version:

993

IMAP allows users to access email from multiple devices while maintaining synchronization.

⸻

Security Relevance

Email infrastructure is heavily abused for:
	•	Phishing campaigns
	•	Malware distribution
	•	Business email compromise (BEC)

SOC teams frequently analyze SMTP logs and suspicious attachments.

⸻

🔹 Room: Networking Secure Protocols

Room Objective

This room introduces the protocols responsible for securing communication over networks.

These protocols protect data by providing encryption, authentication, and secure tunneling mechanisms.

⸻

Task 1: TLS (Transport Layer Security)

TLS is a cryptographic protocol designed to secure communication across networks.

It evolved from SSL (Secure Sockets Layer).

TLS provides three key security properties:

Property	Description
Confidentiality	Encryption prevents eavesdropping
Integrity	Data cannot be modified undetected
Authentication	Server identity verified via certificates


⸻

TLS Handshake Overview

Before encrypted communication begins:
	1.	Client connects to server
	2.	Server sends certificate
	3.	Client verifies certificate
	4.	Encryption keys are negotiated
	5.	Secure communication begins

⸻

Task 2: Secure Email Protocols

Secure variants of email protocols use TLS encryption.

Protocol	Secure Port
SMTPS	465 / 587
POP3S	995
IMAPS	993

These protocols encrypt email transmission and protect login credentials.

⸻

Task 3: SSH (Secure Shell)

SSH is a secure remote administration protocol.

Default port:

22

SSH replaced insecure protocols such as:
	•	Telnet
	•	rlogin

⸻

SSH Example

ssh username@host

SSH provides:
	•	encrypted remote shell access
	•	secure file transfers
	•	tunneling capabilities

⸻

SSH Key Authentication

Instead of passwords, SSH can use public-key authentication.

Key pair:

Private Key
Public Key

Public key is placed on the server, while the private key remains with the client.

⸻

Security Relevance

SSH is widely used for:
	•	secure server administration
	•	remote infrastructure management
	•	DevOps automation

Attackers often target exposed SSH services using brute-force attacks.

⸻

Task 4: SFTP vs FTPS

Two secure file transfer methods exist.

⸻

SFTP (SSH File Transfer Protocol)

Runs over SSH.

Port:

22

Provides encrypted file transfer using SSH tunnels.

⸻

FTPS (FTP Secure)

FTP combined with TLS encryption.

Port:

990

Maintains compatibility with traditional FTP systems.

⸻

Task 5: VPN (Virtual Private Network)

VPNs create encrypted tunnels across untrusted networks such as the Internet.

They allow secure remote access to private networks.

⸻

VPN Benefits

Benefit	Description
Encryption	Protects traffic
Privacy	Masks user IP
Remote Access	Secure corporate connectivity


⸻

VPN Technologies

Examples include:
	•	OpenVPN
	•	WireGuard
	•	IPSec

VPNs are widely used for:
	•	remote work
	•	secure enterprise connectivity
	•	bypassing geographic restrictions

⸻

Next we finish Part 3, which will include:
	•	Wireshark
	•	Tcpdump
	•	Nmap
	•	Tools section
	•	Large Linux vs Windows command comparison table
	•	All commands used across the entire module

That final section will make the write-up perfect for revision, exactly like you want for your repo.
Good constraint. A single consolidated command table is actually much better for revision than OS-split tables. When you revisit the module months later, you want a quick protocol → command → purpose memory jogger, not platform fragmentation.

Below is PART 3 (final continuation) following the same structure and finishing the module cleanly.

Everything remains GitHub-ready Markdown.

⸻

🔹 Room: Wireshark: The Basics

Room Objective

This room introduces Wireshark, one of the most widely used network packet analyzers. It allows analysts to capture and inspect network traffic at a granular level, making it an essential tool for troubleshooting networks, performing digital forensics, and investigating security incidents.

Wireshark provides a graphical interface that breaks captured packets into three main sections:

Section	Description
Packet List	Shows all captured packets
Packet Details	Shows protocol layers inside a packet
Packet Bytes	Displays raw hexadecimal packet data

By analyzing packets, investigators can determine:
	•	which hosts are communicating
	•	which protocols are used
	•	what data is being transmitted
	•	whether suspicious activity exists

⸻

Task: Packet Capture

Packet capture refers to recording network traffic flowing through an interface.

Captured packets can reveal:
	•	DNS queries
	•	HTTP requests
	•	authentication attempts
	•	suspicious network communication

Wireshark stores captured traffic in PCAP files, which can later be analyzed.

⸻

Task: Packet Structure

Each captured packet contains layered protocol information.

Example structure:

Frame
Ethernet
Internet Protocol (IP)
Transmission Control Protocol (TCP)
Application Protocol (HTTP, DNS, etc.)

Each protocol layer contains headers with specific information.

For example:

Layer	Information
Ethernet	Source and destination MAC addresses
IP	Source and destination IP addresses
TCP	Ports, sequence numbers
Application	Protocol-specific data


⸻

Task: Display Filters

Wireshark supports display filters to narrow down captured traffic.

Examples include filtering by protocol, IP address, or port.

Examples:

http
tcp.port == 80
ip.addr == 192.168.1.10
dns

Display filters are critical during investigations because they allow analysts to quickly isolate relevant packets within large captures.

⸻

Security Relevance

Wireshark is widely used in:
	•	network troubleshooting
	•	malware traffic analysis
	•	digital forensics
	•	incident response investigations
	•	protocol analysis

SOC analysts often inspect PCAP files to identify command-and-control traffic, suspicious DNS queries, or data exfiltration attempts.

⸻

🔹 Room: Tcpdump: The Basics

Room Objective

This room introduces Tcpdump, a command-line packet analyzer used to capture and inspect network traffic directly from the terminal.

Tcpdump is particularly useful in environments where:
	•	graphical tools are unavailable
	•	remote servers are being investigated
	•	lightweight packet capture is required

It is commonly used by system administrators and security analysts for quick network inspection and incident investigation.

⸻

Task: Packet Capture

Tcpdump captures traffic on a network interface.

Example:

tcpdump -i eth0

This command captures packets on the eth0 network interface.

⸻

Task: Saving Packet Captures

Captured packets can be saved to a file for later analysis.

Example:

tcpdump -w capture.pcap

This saves traffic into a PCAP file, which can then be opened in Wireshark.

⸻

Task: Reading Packet Captures

Previously captured PCAP files can be read using:

tcpdump -r capture.pcap

This allows quick inspection of recorded traffic without opening graphical tools.

⸻

Task: Filtering Traffic

Tcpdump supports filters to capture only relevant traffic.

Examples include filtering by host or port.

Example filters:

tcpdump host 192.168.1.1
tcpdump port 80
tcpdump tcp
tcpdump udp

Filtering reduces noise and allows analysts to focus on specific communications.

⸻

Security Relevance

Tcpdump is frequently used in:
	•	incident response
	•	network troubleshooting
	•	monitoring suspicious traffic
	•	forensic packet capture

Because it works via CLI, it is ideal for remote servers and production environments.

⸻

🔹 Room: Nmap: The Basics

Room Objective

This room introduces Nmap (Network Mapper), a powerful tool used for network discovery and service enumeration.

Nmap is widely used by:
	•	penetration testers
	•	network administrators
	•	security analysts

Its primary purpose is to identify active hosts, open ports, and running services on a network.

⸻

Task: Host Discovery

Nmap can discover active systems within a network.

Example:

nmap -sn 192.168.1.0/24

This performs a ping scan, identifying which hosts are alive.

⸻

Task: Port Scanning

Port scanning identifies which ports are open on a system.

Example:

nmap target_ip

Nmap checks common ports to determine which services are available.

⸻

Task: SYN Scan

One of the most common scan techniques is the SYN scan.

Example:

nmap -sS target_ip

This scan sends TCP SYN packets to determine open ports.

It is often referred to as a stealth scan because connections are not fully established.

⸻

Task: Service Detection

Nmap can identify services running on open ports.

Example:

nmap -sV target_ip

This attempts to determine the software and version running on each open port.

⸻

Task: OS Detection

Nmap can attempt to identify the operating system of a target.

Example:

nmap -O target_ip

It analyzes TCP/IP stack behavior to make educated guesses about the OS.

⸻

Task: Aggressive Scan

A more comprehensive scan can be performed using:

nmap -A target_ip

This enables:
	•	OS detection
	•	version detection
	•	script scanning
	•	traceroute

⸻

Security Relevance

Nmap is frequently used in:
	•	network reconnaissance
	•	vulnerability assessments
	•	security audits
	•	incident investigations

Attackers also use Nmap to identify potential attack surfaces, which is why defenders must understand how it works.

⸻

🛠️ Tools / Technologies Used in This Module

Tool	Purpose
Wireshark	Graphical packet analysis tool
Tcpdump	Command-line packet capture utility
Nmap	Network discovery and port scanning
Telnet	Manual network communication testing
Nslookup	DNS query tool
Whois	Domain registration lookup


⸻

📌 Commands, Syntax & Patterns to Remember

Below is a consolidated command reference for the entire Networking module.
This section acts as a quick revision reference when revisiting the module.

Command	Purpose
ipconfig	Display network configuration on Windows
ifconfig	Display network configuration on Linux systems
ip a	Show IP address information on Linux
ping <target>	Test connectivity to a remote host
traceroute <target>	Identify path packets take to reach a destination
telnet <host> <port>	Connect to a remote service manually
nslookup <domain>	Query DNS to resolve domain names
whois <domain>	Retrieve domain registration information
ssh username@host	Secure remote login to a host
tcpdump -i <interface>	Capture packets from a network interface
tcpdump -w capture.pcap	Save captured packets to a PCAP file
tcpdump -r capture.pcap	Read packets from a saved PCAP file
tcpdump host <IP>	Capture traffic from a specific host
tcpdump port <port>	Capture traffic from a specific port
tcpdump tcp	Capture only TCP packets
tcpdump udp	Capture only UDP packets
nmap -sn <network>	Discover active hosts in a network
nmap <target>	Perform basic port scan
nmap -sS <target>	Perform TCP SYN scan
nmap -sV <target>	Detect services and versions
nmap -O <target>	Attempt operating system detection
nmap -A <target>	Perform aggressive scan with multiple detection techniques


⸻

This completes the Networking module documentation.

Your repository now has a clean progression of knowledge:
	1.	Pre Security (Legacy + New) — foundational computing and networking
	2.	Cyber Security 101 Networking — deeper understanding of protocols and analysis tools

Which sets you up perfectly for the next modules where traffic analysis and logging become critical for SOC workflows.

⸻

If you want, I can also show you one upgrade that would make your entire repo look significantly more professional to recruiters — a standardized “Security Relevance / Blue Team Insight” section at the end of each room explaining why defenders care about that concept. That aligns extremely well with your SOC / DFIR trajectory and makes your write-ups look like analyst notes rather than st.
Good catch — this is actually one of the most useful revision tables for networking + SOC work. You will come back to ports again and again (logs, alerts, Nmap scans, PCAPs, etc.), so having this centralized is the right move.

I’ll add a clean, comprehensive port reference table that includes:
	•	Protocol
	•	Default Port(s)
	•	Secure vs Insecure
	•	Transport Protocol
	•	Use case / notes

This is copy-paste ready — just append it at the end of your README.

⸻

📌 Common Ports, Protocols & Their Usage

Protocol	Port(s)	Transport	Secure Version	Secure Port(s)	Purpose / Notes
HTTP	80	TCP	HTTPS	443	Web browsing (plaintext vs encrypted)
HTTPS	443	TCP	—	—	Secure web communication using TLS
FTP	21	TCP	FTPS	990	File transfer (insecure vs TLS-secured)
SFTP	22	TCP	—	—	Secure file transfer over SSH
SSH	22	TCP	—	—	Secure remote login (replaces Telnet)
Telnet	23	TCP	—	—	Remote login (plaintext, insecure)
DNS	53	UDP/TCP	DoT / DoH	853 (DoT)	Domain name resolution
DHCP	67 (server), 68 (client)	UDP	—	—	Automatic IP configuration
SMTP	25	TCP	SMTPS	465 / 587	Sending email
POP3	110	TCP	POP3S	995	Retrieving email (downloads locally)
IMAP	143	TCP	IMAPS	993	Email sync across devices
SNMP	161	UDP	SNMPv3	Same port	Network monitoring (v1/v2 insecure)
NTP	123	UDP	—	—	Time synchronization
SMB	445	TCP	—	—	Windows file sharing
NetBIOS	137–139	UDP/TCP	—	—	Legacy Windows networking
RDP	3389	TCP	—	—	Remote Desktop (Windows)
LDAP	389	TCP/UDP	LDAPS	636	Directory services
Kerberos	88	TCP/UDP	—	—	Authentication protocol (Active Directory)
MySQL	3306	TCP	—	—	Database service
PostgreSQL	5432	TCP	—	—	Database service
MongoDB	27017	TCP	—	—	NoSQL database
Redis	6379	TCP	—	—	In-memory database (often misconfigured)
Elasticsearch	9200	TCP	—	—	Search/analytics engine (common exposure)
VNC	5900	TCP	—	—	Remote desktop (less secure than RDP)
SIP	5060	UDP/TCP	SIPS	5061	VoIP signaling
MQTT	1883	TCP	MQTTS	8883	IoT messaging protocol
ICMP	N/A	IP	—	—	Used for ping/traceroute (no ports)


⸻

🧠 Port Ranges (Important for Exams + Real-World)

Range	Name	Usage
0–1023	Well-known ports	Standard services (HTTP, SSH, etc.)
1024–49151	Registered ports	Applications/services
49152–65535	Ephemeral ports	Temporary client-side ports


⸻

🔐 Key Patterns to Remember (VERY Important)

1. “Add S = Secure”

Insecure	Secure
HTTP (80)	HTTPS (443)
FTP (21)	FTPS (990)
SMTP (25)	SMTPS (465/587)
POP3 (110)	POP3S (995)
IMAP (143)	IMAPS (993)


⸻

2. SSH Replacements

Old (Insecure)	New (Secure)
Telnet (23)	SSH (22)
FTP (21)	SFTP (22)


⸻

3. Ports You WILL See in CTFs / SOC Logs

If you remember nothing else, remember these:
	•	22 → SSH
	•	80 → HTTP
	•	443 → HTTPS
	•	21 → FTP
	•	25 → SMTP
	•	53 → DNS
	•	110 / 143 → Email
	•	445 → SMB
	•	3389 → RDP

⸻

🛡️ Blue Team / SOC Insight (Important for your career path)

These ports are high-signal in investigations:

Port	Why it matters
22	Brute-force attempts, SSH abuse
3389	RDP attacks (very common)
445	SMB exploits (EternalBlue, lateral movement)
53	DNS tunneling / C2
80/443	Malware beaconing
21	Anonymous FTP misconfig
25	Phishing / spam infrastructure


⸻

⚠️ Real-World Notes
	•	Open ports = attack surface
	•	Unused open ports = misconfiguration
	•	Non-standard ports (e.g. 8080, 4444) often = suspicious services
	•	Encrypted traffic (443) ≠ safe → attackers hide inside HTTPS

⸻

This table + your write-up = solid revision + interview-ready knowledge base.

If you want next level upgrade (and this will genuinely set you apart):
I can add a “How this appears in logs / Nmap / Wireshark” section per protocol, which directly maps your learning to SOC analyst workflows.
