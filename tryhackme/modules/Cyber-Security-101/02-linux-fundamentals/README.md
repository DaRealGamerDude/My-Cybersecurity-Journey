# TryHackMe Module: Linux Fundamentals

**Path:** Cyber Security 101  
**Module Type:** Mixed (Theory + Hands-on)  
**Difficulty:** Beginner  
**Status:** Completed  
**Date Completed:** [Add Date]

---

## Summary

This module focuses on learning and practicing **Linux command-line fundamentals**. It introduces the Linux terminal, filesystem navigation, file management, permissions, processes, logging, package management, automation, and remote access.

Although this module was previously completed in earlier learning paths, it was revisited to reinforce **operational understanding and security relevance**, particularly for **SOC and DFIR workflows**.

The module consists of three rooms that progressively build Linux skills:

- Linux Fundamentals Part 1 – Terminal basics and filesystem navigation  
- Linux Fundamentals Part 2 – SSH access, permissions, and system directories  
- Linux Fundamentals Part 3 – Processes, automation, logs, and system management

---

## Rooms in This Module

| Order | Room Name | Primary Focus | Status |
|------|----------|--------------|--------|
| 1 | Linux Fundamentals Part 1 | Terminal basics & filesystem navigation | ✔ |
| 2 | Linux Fundamentals Part 2 | SSH, permissions, directories | ✔ |
| 3 | Linux Fundamentals Part 3 | Processes, automation, logs, utilities | ✔ |

---

## Key Concepts Covered (Module-Level)

- Linux command-line interaction
- Filesystem navigation and manipulation
- Searching for files and content
- Shell operators and command chaining
- File permissions and ownership
- Remote access via SSH
- Process monitoring and management
- Service management using systemctl
- Task automation using cron
- Package management using apt
- Log analysis and monitoring
- File transfer techniques (scp, wget)
- Running temporary web servers

---

## Room Notes & Task Breakdown

---

### 🔹 Room: Linux Fundamentals Part 1

**Room Objective:**  
Introduce the Linux terminal, essential commands, and filesystem interaction.

---

#### Task: Running First Commands

**What the task covers:**

- Introduction to the Linux terminal
- Running basic commands

**Important Commands**

| What it Does | Linux Terminal | Windows CMD | PowerShell |
|--------------|---------------|-------------|-------------|
| Print text | `echo Hello` | `echo Hello` | `Write-Output Hello` |
| Show current user | `whoami` | `whoami` | `whoami` |

---

#### Task: Interacting with the Filesystem

**What the task covers:**

- Navigating directories
- Viewing files
- Understanding file paths

**Commands**

| What it Does | Linux | Windows CMD | PowerShell |
|--------------|-------|-------------|------------|
| List files | `ls` | `dir` | `Get-ChildItem` |
| Change directory | `cd folder` | `cd folder` | `Set-Location folder` |
| Print working directory | `pwd` | `cd` | `Get-Location` |
| View file contents | `cat file.txt` | `type file.txt` | `Get-Content file.txt` |

---

#### Task: Searching for Files

**What the task covers**

- Searching files across directories
- Searching content inside files

**Commands**

| What it Does | Linux | Windows CMD | PowerShell |
|--------------|-------|-------------|------------|
| Find file by name | `find -name file.txt` | `dir /s file.txt` | `Get-ChildItem -Recurse` |
| Search text in file | `grep "text" file` | `findstr "text" file` | `Select-String "text"` |

Example from the lab:

```

grep "81.143.211.90" access.log

```

---

#### Task: Shell Operators

**Concept**

Shell operators allow chaining commands or redirecting output.

| Operator | Purpose |
|--------|--------|
| `&` | Run command in background |
| `&&` | Run next command if previous succeeds |
| `>` | Redirect output (overwrite file) |
| `>>` | Append output to file |

Example:

```

echo password123 > passwords
echo tryhackme >> passwords

```

---

### 🔹 Room: Linux Fundamentals Part 2

**Room Objective:**  
Introduce remote system access, command flags, filesystem management, permissions, and important Linux directories.

---

#### Task: Remote Access via SSH

**Key Learning**

SSH (Secure Shell) allows encrypted remote command execution.

Example:

```

ssh tryhackme@MACHINE_IP

```

Important properties:

- Secure remote login
- Encrypted communication
- Used heavily in server administration and penetration testing

---

#### Task: Command Flags and Manual Pages

Commands can be extended using flags or switches.

Example:

```

ls -a

```

Shows hidden files.

Manual pages can be accessed using:

```

man command

```

Example:

```

man ls

```

---

#### Task: Filesystem Management

**Commands**

| What it Does | Linux Command |
|--------------|--------------|
| Create file | `touch file` |
| Create directory | `mkdir folder` |
| Copy file | `cp file1 file2` |
| Move or rename file | `mv file1 file2` |
| Remove file | `rm file` |
| Remove directory | `rm -R folder` |
| Identify file type | `file filename` |

Example:

```

touch newnote
mv myfile myfolder

```

---

#### Task: Permissions

Linux uses a **read, write, execute** permission model.

Symbolic representation:

```

rwxr-xr-x

```

Numeric representation:

| Permission | Value |
|-----------|------|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

Examples:

| Symbolic | Numeric | Meaning |
|--------|--------|--------|
| rwxr-xr-x | 755 | Owner full access |
| rw-r--r-- | 644 | Owner read/write |
| rwx------ | 700 | Only owner access |

Command example:

```

chmod 750 file.txt

```

---

#### Task: Important Linux Directories

| Directory | Purpose |
|-----------|--------|
| `/etc` | Configuration files |
| `/var/log` | System and service logs |
| `/root` | Root user's home directory |
| `/tmp` | Temporary files |

Security relevance:

- Logs used for forensic investigation
- `/tmp` frequently abused for temporary payloads

---

### 🔹 Room: Linux Fundamentals Part 3

**Room Objective:**  
Introduce system utilities, process management, automation, logging, and package management.

---

#### Task: Text Editors

Two editors introduced:

**Nano**

```

nano filename

```

Used for simple file editing.

**Vim**

More advanced editor with syntax highlighting and custom configurations.

---

#### Task: File Transfer and Web Utilities

Downloading files:

```

wget [http://example.com/file](http://example.com/file)

```

Secure copy via SSH:

```

scp file user@IP:/destination

```

Running a quick web server:

```

python3 -m http.server

```

---

#### Task: Processes

Processes represent programs running on the system.

Commands:

| What it Does | Command |
|--------------|--------|
| List processes | `ps` |
| List all processes | `ps aux` |
| Real-time process monitoring | `top` |
| Kill process | `kill PID` |

Signals:

| Signal | Purpose |
|------|--------|
| SIGTERM | Graceful process termination |
| SIGKILL | Force termination |
| SIGSTOP | Pause process |

Background process example:

```

command &

```

Bring process to foreground:

```

fg

```

---

#### Task: Automation with Cron

Cron schedules automated tasks.

Crontab format:

```

MIN HOUR DOM MON DOW COMMAND

```

Example:

```

0 */12 * * * cp -R /home/user/Documents /var/backups/

```

Command to edit crontab:

```

crontab -e

```

---

#### Task: Package Management

Ubuntu uses **APT** for managing software packages.

Commands:

| Action | Command |
|------|--------|
| Update repository list | `apt update` |
| Install package | `apt install package` |
| Remove package | `apt remove package` |

Repositories are verified using **GPG keys** to ensure software authenticity.

---

#### Task: Logs and Monitoring

Logs are primarily stored in:

```

/var/log/

```

Examples:

| Log Type | Purpose |
|--------|--------|
| Apache access log | Web requests |
| Apache error log | Server errors |
| auth.log | Authentication attempts |
| fail2ban log | Brute-force detection |

Example investigation from the lab:

- IP address observed: `10.9.232.111`
- File accessed: `catsanddogs.jpg`

---

## Tools / Technologies Used in This Module

- Linux Terminal
- SSH
- Nano Text Editor
- Vim Text Editor
- Cron Scheduler
- APT Package Manager
- Python HTTP Server
- SCP File Transfer
- Wget Downloader

---

## 📌 Commands, Syntax & Patterns to Remember

```

# Remote login

ssh user@IP

# Search files

find -name file.txt

# Search text

grep "text" file

# File operations

touch file
mkdir folder
cp file1 file2
mv file1 file2
rm file

# Permissions

chmod 755 file

# Process management

ps aux
top
kill PID

# Cron jobs

crontab -e

# File transfer

scp file user@IP:/path

# Web server

python3 -m http.server

# Download files

wget URL

```

---

## Reflection

Although the Linux Fundamentals module covers beginner material, it establishes the foundation required for many cybersecurity tasks. Understanding the Linux command line is essential for system administration, penetration testing, and defensive security operations.

Revisiting this module reinforced how core Linux concepts such as file permissions, logs, processes, and automation directly relate to **security monitoring, incident response, and system investigation workflows**.
```
