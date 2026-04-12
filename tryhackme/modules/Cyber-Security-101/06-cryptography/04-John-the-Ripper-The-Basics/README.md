# TryHackMe Room: John the Ripper — The Basics

**Path:** Cyber Security 101  
**Module Type:** Practical (Hands-on)  
**Tool Focus:** John the Ripper (Jumbo)  
**Status:** Completed  

---

# Summary

This room focuses on using **John the Ripper**, a powerful password-cracking tool used in both offensive security and forensic workflows.

It covers:
- Hash cracking using wordlists
- Hash identification and formats
- Cracking system password files (/etc/shadow)
- Exploiting weak password patterns
- Cracking protected files (ZIP, RAR, SSH keys)

This room is highly relevant for **SOC/DFIR**, especially in:
- Password breach analysis  
- Hash cracking during investigations  
- Credential recovery scenarios  

---

# Key Concepts Covered

- Dictionary attacks  
- Hash format identification  
- Wordlists (rockyou.txt)  
- NTLM / Linux password hashes  
- Single crack mode (word mangling)  
- Custom rules  
- File hash extraction tools (zip2john, rar2john, ssh2john)  

---

# Tools Used

| Tool | Purpose |
|------|--------|
| John the Ripper | Password cracking |
| hash-identifier | Identify hash types |
| rockyou.txt | Wordlist for attacks |
| zip2john / rar2john / ssh2john | Convert files to crackable hashes |

---

# Task Breakdown & Notes

---

## 🔹 Task 1: Introduction

**Objective:** Understand John the Ripper and its capabilities.

---

Let’s begin!

**Answer:**  
No answer needed  

---

## 🔹 Task 2: Basic Terms

### Key Idea

- Hashing = one-way  
- Cracking = guessing inputs until match  

---

What is the most popular extended version of John the Ripper?

**Answer:**

Jumbo John

**Explanation:**  
Jumbo version includes extended formats and tools like zip2john.

---

## 🔹 Task 3: Setup & Wordlists

### Important

- Wordlist used: **rockyou.txt**
- Location: `/usr/share/wordlists`

---

Which website’s breach created rockyou.txt?

**Answer:**

rockyou.com

---

## 🔹 Task 4: Cracking Basic Hashes

### Key Syntax

john --format=<type> --wordlist=<path> <file>

---

### ⚠️ Common Mistake (Real Experience)

stat: hash2.txt: No such file or directory

**Cause:** Wrong directory  

**Fix:**

cd ~/John-the-Ripper-The-Basics/Task04

---

### Hash Cracking Results

| File | Type | Password |
|------|------|----------|
| hash1.txt | md5 | biscuit |
| hash2.txt | sha1 | kangeroo |
| hash3.txt | sha256 | microphone |
| hash4.txt | whirlpool | colossal |

---

### Example Command

john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt

---

### Terminal Insight

Loaded 1 password hash Cracked 1 password hash (stored in john.pot)

**Explanation:**  
Cracked passwords are stored in `john.pot`.

---

## 🔹 Task 5: Windows Authentication Hashes (NTLM)

### Key Concept

- Windows stores passwords as **NTLM hashes**
- Found in SAM database  

---

### ⚠️ Common Mistake

Error: No format matched requested name 'raw-ntlm'

**Fix:**

john --format=nt --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt

---

### Result

mushroom

---

### Terminal Output

Loaded 1 password hash (NT) mushroom (?) Session completed

---

## 🔹 Task 6: Cracking /etc/shadow Hashes

### Key Concept

- Linux passwords stored in `/etc/shadow`
- Must combine with `/etc/passwd`

---

### Example Data

root:$6$Ha.d5nGupBm29pYr$...

---

### Command Used

john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt etc_hashes.txt

---

### Result

1234

---

### Terminal Output

Loaded 1 password hash (sha512crypt) 1234 (root) Session completed

---

## 🔹 Task 7: Single Crack Mode

### Key Concept

- Uses username to guess passwords  
- Applies **word mangling**

---

### ⚠️ Common Mistake

john --single hash07.txt → no result

**Cause:** Missing username  

---

### Fix

Format file as:

Joker:7bf6d9bb82bed1302f331fc6b816aada

---

### Command

john --single --format=raw-md5 joker_hash.txt

---

### Result

Jok3r

---

## 🔹 Task 8: Custom Rules

### Key Idea

Exploit:
> **Password pattern predictability**

---

### Questions

What do custom rules allow us to exploit?

**Answer:**

Password complexity predictability

---

Rule to append capital letters?

**Answer:**

Az"[A-Z]"

---

Flag to call rule?

**Answer:**

--rule=THMRules

---

## 🔹 Task 9: Cracking ZIP Files

### Step 1: Extract hash

zip2john secure.zip > secure_hash.txt

---

### Step 2: Crack

john --wordlist=/usr/share/wordlists/rockyou.txt secure_hash.txt

---

### Result

pass123

---

### Extract File

unzip secure.zip cat flag.txt

---

### Output

THM{w3ll_d0n3_h4sh_r0y4l}

---

## 🔹 Task 10: Cracking RAR Files

### Commands

rar2john secure.rar > rar_hash.txt john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt

---

### Result

password

---

### Flag

THM{r4r_4rch1ve5_th15_t1m3}

---

## 🔹 Task 11: Cracking SSH Keys

### Command

ssh2john id_rsa > id_rsa_hash.txt john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt

---

### Result

mango

---

## 🔹 Task 12: Conclusion

Time for a new challenge!

**Answer:**  
No answer needed  

---

# Key Takeaways

- Hash cracking = guessing, not decrypting  
- Correct format selection is critical  
- Wordlists are the backbone of attacks  
- Username-based attacks (single mode) are powerful  
- Real-world systems store hashes, not passwords  

---

# Reflection

This room significantly improved practical understanding of password cracking tools and workflows.

Key learnings:
- Debugging command errors (paths, formats)
- Understanding how tools behave internally (john.pot)
- Applying cracking techniques across different formats

These skills directly translate to:
- SOC investigations (credential analysis)
- DFIR workflows (hash matching, password recovery)
- CTF challenges and real-world incident response
