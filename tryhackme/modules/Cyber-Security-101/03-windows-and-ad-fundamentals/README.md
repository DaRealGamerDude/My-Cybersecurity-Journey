# TryHackMe Module: Windows and AD Fundamentals

**Path:** Cyber Security 101  
**Module Type:** Mixed (Theory + Hands-on)  
**Difficulty:** Beginner  
**Status:** Completed  
**Date Completed:** [Add Date]

---

## Summary

This module focuses on learning the fundamentals of **Microsoft Windows environments and Active Directory (AD)**. Since a majority of corporate networks rely heavily on Windows-based infrastructure, understanding how Windows and Active Directory function is essential for both offensive and defensive cybersecurity roles.

The Windows Fundamentals rooms introduce the Windows operating system, its security mechanisms, system configuration tools, and built-in defensive technologies.

The final room, **Active Directory Basics**, explores the architecture and management of Windows domains, including domain controllers, organizational units, group policies, authentication mechanisms, and domain trust relationships.

Since Windows Fundamentals 1–3 were previously completed, they are briefly summarized, while the **Active Directory Basics** room is explored in more detail.

---

## Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|------|----------|--------------|--------|
| 1 | Windows Fundamentals 1 | Windows OS basics & desktop environment | ✔ |
| 2 | Windows Fundamentals 2 | System configuration, registry & monitoring | ✔ |
| 3 | Windows Fundamentals 3 | Windows security features | ✔ |
| 4 | Active Directory Basics | Domain architecture & identity management | ✔ |

---

## Key Concepts Covered (Module-Level)

- Windows operating system architecture
- NTFS filesystem permissions
- Windows security mechanisms (UAC, BitLocker, Defender)
- System configuration and monitoring tools
- Windows Registry
- Windows Domain architecture
- Active Directory objects and structure
- Organizational Units (OUs)
- Security Groups
- Group Policy Objects (GPOs)
- Kerberos authentication
- NetNTLM authentication
- Domain trees, forests, and trust relationships

---

## Room Notes & Task Breakdown

---

### 🔹 Room: Windows Fundamentals 1

**Room Objective:**  
Introduce the Windows operating system, desktop interface, filesystem structure, and security controls.

---

#### Key Learning

- Understanding the **Windows desktop environment**
- Introduction to the **NTFS filesystem**
- Understanding **User Account Control (UAC)**
- Using the **Control Panel** and system management tools

---

#### Important Concepts

**NTFS File System**

NTFS is the primary filesystem used by modern Windows operating systems. It provides:

- File permissions
- Encryption support
- Compression
- Access control lists (ACLs)

These features allow administrators to control how users interact with files and system resources.

---

#### Security Relevance

- NTFS permissions enforce access control
- UAC prevents unauthorized privilege escalation
- File permissions help restrict sensitive data access

---

### 🔹 Room: Windows Fundamentals 2

**Room Objective:**  
Explore Windows system configuration tools and deeper operating system components.

---

#### Key Learning

- System Configuration (`msconfig`)
- Windows Registry
- Resource monitoring
- Task Manager and performance monitoring

---

#### Windows Registry

The **Windows Registry** is a hierarchical database used to store configuration settings for:

- Operating system components
- Applications
- Hardware settings
- User preferences

Registry structure example:

```

HKEY_LOCAL_MACHINE
HKEY_CURRENT_USER
HKEY_CLASSES_ROOT

```

---

#### Security Relevance

Registry modifications are frequently used by malware to:

- Achieve persistence
- Modify startup behavior
- Disable security tools

Monitoring registry changes is an important defensive practice.

---

### 🔹 Room: Windows Fundamentals 3

**Room Objective:**  
Introduce built-in Windows security tools and update mechanisms.

---

#### Key Learning

- Windows Update
- Windows Defender
- BitLocker encryption
- Security monitoring tools

---

#### Windows Security Tools

| Tool | Purpose |
|-----|--------|
| Windows Defender | Built-in antivirus |
| Windows Firewall | Network protection |
| BitLocker | Full disk encryption |
| Windows Update | Patch management |

---

#### Security Relevance

These tools help protect endpoints from:

- Malware infections
- Unauthorized access
- Vulnerabilities due to outdated software

Patch management is critical in enterprise environments.

---

### 🔹 Room: Active Directory Basics

**Room Objective:**  
Introduce the structure and functionality of Active Directory and Windows domains.

---

#### Task: Windows Domains

A **Windows Domain** centralizes the management of users and computers within an organization.

Key component:

**Active Directory**

Active Directory acts as the central repository storing:

- User accounts
- Computers
- Groups
- Network resources

The server responsible for running Active Directory is called a:

```

Domain Controller (DC)

```

---

#### Task: Active Directory Objects

Active Directory stores information as **objects**.

Common objects include:

| Object Type | Description |
|-------------|-------------|
| Users | Accounts representing individuals or services |
| Machines | Computer accounts joined to the domain |
| Groups | Collections of users or machines |
| Printers | Network printing resources |
| Shares | Shared folders |

Users and machines are both considered **security principals**, meaning they can be authenticated and assigned permissions.

---

#### Machine Accounts

When a computer joins a domain, a **machine account** is automatically created.

Naming format:

```

COMPUTERNAME$

```

Example:

```

TOM-PC$

```

Machine passwords are automatically rotated and often consist of long random values.

---

#### Security Groups

Security groups allow administrators to manage permissions efficiently.

Example default groups:

| Group | Description |
|------|-------------|
| Domain Admins | Full administrative privileges |
| Server Operators | Manage domain servers |
| Backup Operators | Access files for backup purposes |
| Account Operators | Manage user accounts |
| Domain Users | All users in the domain |

---

#### Organizational Units (OUs)

OUs organize objects inside Active Directory.

Example OU structure:

```

THM
├── IT
├── Marketing
├── Sales
├── Management
└── R&D

```

OUs are primarily used to:

- Organize users
- Apply group policies
- Mirror organizational structure

Important distinction:

| Feature | Purpose |
|-------|---------|
| Organizational Units | Policy management |
| Security Groups | Permission management |

---

#### Task: Managing Users in Active Directory

Administrative tasks include:

- Creating users
- Deleting users
- Resetting passwords
- Delegating permissions

Example PowerShell command used during the lab:

```

Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString)

```

Force password change at next login:

```

Set-ADUser -ChangePasswordAtLogon $true -Identity sophie

```

---

#### Delegation

Delegation allows administrators to grant limited privileges without giving full administrative access.

Example use case:

- Allow helpdesk staff to reset passwords for specific departments.

Delegation improves security by following the **principle of least privilege**.

---

#### Task: Managing Computers

Computers are typically separated into different Organizational Units.

Example structure:

```

thm.local
├── Servers
├── Workstations
└── Domain Controllers

```

Benefits of separating systems:

- Different security policies
- Different update policies
- Improved administrative control

---

#### Task: Group Policy Objects (GPO)

Group Policy Objects allow administrators to enforce configurations across users and computers.

Examples of policies:

- Password policies
- Account lockout rules
- Screen lock policies
- Control panel restrictions

Example command to update policies:

```

gpupdate /force

```

Group policies are distributed via the network share:

```

SYSVOL

```

---

#### Task: Authentication Methods

Windows domains use two authentication protocols.

---

**Kerberos (Default)**

Kerberos uses ticket-based authentication.

Process overview:

1. User authenticates with Domain Controller
2. Receives a **Ticket Granting Ticket (TGT)**
3. Uses TGT to request service tickets
4. Accesses resources using service tickets

Key component:

```

Key Distribution Center (KDC)

```

---

**NetNTLM**

Legacy authentication protocol using a challenge-response mechanism.

Process overview:

1. Server sends challenge
2. Client encrypts challenge using password hash
3. Domain controller verifies response

Important note:

Passwords are **never transmitted directly over the network**.

---

#### Task: Trees, Forests and Trusts

As organizations grow, multiple domains may exist.

---

**Tree**

A group of domains sharing the same namespace.

Example:

```

thm.local
├── uk.thm.local
└── us.thm.local

```

---

**Forest**

A collection of multiple domain trees with different namespaces.

Example:

```

thm.local
mht.local

```

---

**Trust Relationships**

Trust relationships allow users from one domain to access resources in another.

Types:

| Trust Type | Description |
|------------|-------------|
| One-way trust | Domain A trusts Domain B |
| Two-way trust | Both domains trust each other |

Trusts enable cross-domain resource access.

---

## Tools / Technologies Used in This Module

- Windows OS
- Active Directory Domain Services (AD DS)
- Group Policy Management Console
- Active Directory Users and Computers
- Windows Registry
- PowerShell
- Remote Desktop Protocol (RDP)

---

## 📌 Commands, Syntax & Patterns to Remember

```

# Reset AD user password

Set-ADAccountPassword username -Reset

# Force password change at login

Set-ADUser -ChangePasswordAtLogon $true

# Force group policy update

gpupdate /force

# Login to domain machine

THM\username

# Identify machine account

COMPUTERNAME$

```

---

## Reflection

Windows and Active Directory are central components of enterprise infrastructure. Most corporate environments rely on Active Directory to manage identity, authentication, and access control across thousands of systems.

Understanding Active Directory is critical for cybersecurity because many attacks specifically target misconfigurations within domain environments.

This module introduced the core concepts of Windows domain architecture and Active Directory management, providing the foundation needed to explore topics such as:

- Active Directory exploitation
- Domain privilege escalation
- Kerberos attacks
- AD security monitoring
- Enterprise incident response
