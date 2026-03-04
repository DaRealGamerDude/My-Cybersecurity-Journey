# TryHackMe Module: Command Line

**Path:** Cyber Security 101  
**Module Type:** Mixed (Theory + Hands-on)  
**Difficulty:** Beginner  
**Status:** Completed  
**Date Completed:** [Add Date]

---

# Summary

This module introduces the fundamentals of interacting with operating systems through **Command Line Interfaces (CLI)**. While graphical interfaces are commonly used by everyday users, command-line tools allow administrators and security professionals to interact with systems more efficiently.

The module explores command-line environments across both **Windows and Linux systems**, covering traditional Windows command prompt utilities, PowerShell automation capabilities, and Linux shell usage.

Understanding CLI environments is critical for cybersecurity professionals because many administrative tasks, automation workflows, and security investigations rely heavily on command-line tools.

---

# Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|------|----------|--------------|--------|
| 1 | Windows Command Line | Basic Windows CLI commands and system interaction | ✔ |
| 2 | Windows PowerShell | Object-based command-line automation | ✔ |
| 3 | Linux Shells | Linux shell usage and scripting | ✔ |

---

# Key Concepts Covered (Module-Level)

- Command Line Interface (CLI)
- Windows Command Prompt (`cmd.exe`)
- PowerShell cmdlets and object-based commands
- System information retrieval via CLI
- Network troubleshooting commands
- File and directory management
- Process and service management
- Linux shell environments
- Bash scripting fundamentals
- Automation using shell scripts

---

# Room Notes & Task Breakdown

---

## 🔹 Room: Windows Command Line

**Room Objective:**  
Introduce the Windows command-line interpreter and teach the essential commands used for system administration, networking, and file management.

---

### Key Learning

- Navigating the Windows filesystem using CLI
- Retrieving system information
- Troubleshooting network connectivity
- Managing files and directories
- Monitoring running processes

---

### Basic System Information

The Windows command prompt interpreter is:

```

cmd.exe

```

Commands for retrieving system details:

```

ver

```

Displays the Windows version.

Example:

```

Microsoft Windows [Version 10.0.20348.2655]

```

---

```

systeminfo

```

Displays detailed system information including:

- Hostname
- OS version
- Hardware details
- Installed memory

Example hostname discovered during the lab:

```

WINSRV2022-CORE

```

---

### Network Troubleshooting Commands

Networking commands help identify connectivity issues and network configuration.

---

**Check IP configuration**

```

ipconfig

```

Displays:

- IPv4 address
- Subnet mask
- Default gateway

---

**Detailed network configuration**

```

ipconfig /all

```

Provides additional details including:

- MAC address
- DHCP status
- DNS servers

---

**Test connectivity**

```

ping example.com

```

Uses ICMP packets to test whether a host is reachable.

---

**Trace network route**

```

tracert example.com

```

Displays the network path packets take to reach a destination.

---

**DNS lookup**

```

nslookup example.com

```

Used to resolve domain names into IP addresses.

---

### Network Connections

```

netstat

```

Displays active network connections.

Advanced usage:

```

netstat -abon

```

Options used:

| Option | Purpose |
|------|--------|
| -a | Show all connections |
| -b | Show executable associated with connection |
| -o | Show process ID |
| -n | Show numerical addresses |

Example services identified during the lab:

```

RpcSs

```

Service listening on port **135**

```

TermService

```

Service listening on port **3389**

---

### File and Disk Management

Common commands used to navigate and manipulate files.

---

**View current directory**

```

cd

```

---

**List directory contents**

```

dir

```

Useful options:

```

dir /a
dir /s

```

---

**Display folder structure**

```

tree

```

---

**Create directory**

```

mkdir backup_files

```

---

**Remove directory**

```

rmdir backup_files

```

---

**Display file contents**

```

type filename.txt

```

---

**Copy files**

```

copy test.txt test2.txt

```

---

**Move files**

```

move test2.txt ..

```

---

**Delete files**

```

erase filename.txt

```

---

### File Challenge

Hidden file located in:

```

C:\Treasure\Hunt

```

Flag discovered:

```

THM{CLI_POWER}

```

---

### Process Management

View running processes:

```

tasklist

```

Filter specific processes:

```

tasklist /FI "imagename eq notepad.exe"

```

Terminate process:

```

taskkill /PID 1516

```

---

### Additional System Commands

```

chkdsk

```

Checks disk integrity.

```

driverquery

```

Lists installed drivers.

```

sfc /scannow

```

Scans and repairs system files.

---

### Shutdown Commands

Restart system:

```

shutdown /r

```

Cancel scheduled shutdown:

```

shutdown /a

```

---

## 🔹 Room: Windows PowerShell

**Room Objective:**  
Introduce PowerShell and demonstrate how its object-oriented architecture allows advanced automation and system management.

---

### Key Learning

- PowerShell cmdlet structure
- Object-based pipeline operations
- System information retrieval
- Managing files and processes
- Basic scripting and remote command execution

---

### What is PowerShell?

PowerShell is an automation framework consisting of:

- A command-line shell
- A scripting language
- A configuration management framework

Unlike the Windows command prompt, PowerShell processes **objects rather than text output**.

PowerShell follows an **object-oriented** design.

---

### PowerShell Cmdlets

Cmdlets follow a **Verb-Noun** structure.

Examples:

```

Get-Content
Set-Location
Get-Process

```

---

### Discovering Commands

List all available commands:

```

Get-Command

```

Filter commands beginning with a specific verb:

```

Get-Command -Name Remove*

```

---

### Help System

View command documentation:

```

Get-Help Get-Date

```

View usage examples:

```

Get-Help New-LocalUser -examples

```

---

### File System Navigation

List directory contents:

```

Get-ChildItem

```

Change directory:

```

Set-Location

```

Create new files or directories:

```

New-Item

```

Delete files or directories:

```

Remove-Item

```

Copy files:

```

Copy-Item

```

Move files:

```

Move-Item

```

View file contents:

```

Get-Content

```

---

### Piping and Filtering Data

PowerShell pipelines pass objects between commands.

Example:

```

Get-ChildItem | Sort-Object Length

```

Filter objects:

```

Get-ChildItem | Where-Object -Property Length -gt 100

```

---

### System and Network Information

Retrieve system configuration:

```

Get-ComputerInfo

```

List local users:

```

Get-LocalUser

```

Hidden user discovered during lab:

```

p1r4t3

```

User description:

```

A merry life and a short one.

```

Hidden treasure flag:

```

THM{p34rlInAsh3ll}

```

---

### Real-Time System Analysis

View running processes:

```

Get-Process

```

View services:

```

Get-Service

```

Monitor network connections:

```

Get-NetTCPConnection

```

Generate file hash:

```

Get-FileHash

```

Hash discovered in the lab:

```

71FC5EC11C2497A32F8F08E61399687D90ABE6E204D2964DF589543A613F3E08

```

Tampered service discovered:

```

p1r4t3-s-compass

```

---

### Remote Command Execution

Execute commands on remote systems:

```

Invoke-Command -ComputerName RoyalFortune -ScriptBlock { Get-Service }

```

---

## 🔹 Room: Linux Shells

**Room Objective:**  
Introduce Linux shell environments, command usage, and shell scripting fundamentals.

---

### Key Learning

- Interacting with Linux shells
- Navigating directories
- Searching file contents
- Understanding shell types
- Writing basic shell scripts

---

### Shell Overview

A **shell** acts as the interface between the user and the operating system.

Example shell command prompt:

```

user@tryhackme:~$

```

---

### Basic Linux Commands

Show current directory:

```

pwd

```

Change directory:

```

cd

```

List directory contents:

```

ls

```

View file contents:

```

cat filename.txt

```

Search for text patterns:

```

grep keyword file

```

---

### Linux Shell Types

Common shells include:

| Shell | Description |
|------|-------------|
| Bash | Default shell in most Linux systems |
| Fish | User-friendly shell with syntax highlighting |
| Zsh | Highly customizable modern shell |

Check current shell:

```

echo $SHELL

```

List available shells:

```

cat /etc/shells

```

---

### Shell Scripting

Shell scripts automate repetitive command sequences.

Every Bash script begins with a **shebang**:

```

#!/bin/bash

```

---

### Making Scripts Executable

```

chmod +x script.sh

```

Execute script:

```

./script.sh

```

---

### Scripting Components

Scripts commonly include:

- Variables
- Loops
- Conditional statements
- Comments

Example loop:

```

for i in {1..10}
do
echo $i
done

```

---

### Locker Script Challenge

Authentication credentials used in the script:

Username:

```

John

```

Company:

```

Tryhackme

```

PIN:

```

7385

```

---

### Log Analysis Script Challenge

Script searched for a keyword inside system logs.

Directory scanned:

```

/var/log

```

Log file containing keyword:

```

authentication.log

```

Hidden message discovered:

```

under the table

```

---

# Tools / Technologies Used in This Module

- Windows Command Prompt
- PowerShell
- Linux Bash Shell
- SSH
- Windows Networking Tools
- File System Utilities
- Shell scripting

---

# 📌 Commands, Syntax & Patterns to Remember

```

# Windows Commands

ipconfig
ipconfig /all
ping
tracert
netstat
tasklist
taskkill
shutdown /r

# PowerShell

Get-Command
Get-Help
Get-ChildItem
Get-Process
Get-Service
Get-NetTCPConnection
Invoke-Command

# Linux Commands

pwd
cd
ls
cat
grep
history

# Bash Script Shebang

#!/bin/bash

# Make script executable

chmod +x script.sh

```

---

# Reflection

Command-line interfaces are fundamental tools for cybersecurity professionals. Many security tasks such as system enumeration, network troubleshooting, log analysis, and automation rely heavily on command-line utilities.

This module provided hands-on experience with three major environments used across enterprise systems: Windows Command Prompt, PowerShell, and Linux shells.

Understanding these environments builds the foundation required for advanced topics such as:

- Linux privilege escalation
- PowerShell-based attacks
- Command-line automation
- Incident response investigations
- System enumeration during penetration testing

If you want, I can also show you **how to make all your module writeups follow the exact same template automatically**, so every repo looks **clean, consistent, and professional**.
