# TryHackMe Room: Hashing Basics

**Path:** Cyber Security 101  
**Module Type:** Theory + Hands-on  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces hashing functions and their role in cybersecurity, particularly in **password storage and data integrity verification**. It explains how hashing differs from encryption, how collisions occur, and how hashes are used in authentication systems.

The room also covers password cracking techniques, hash identification, and integrity verification using hashing and HMAC.

Understanding hashing is critical for SOC/DFIR roles, especially when working with **logs, password leaks, file verification, and malware analysis**.

---

# Key Concepts Covered

- Hash functions and properties  
- Hash collisions and pigeonhole principle  
- Password hashing and salting  
- Rainbow tables  
- Hash identification (Linux/Windows)  
- Password cracking (Hashcat, John the Ripper)  
- Integrity verification using hashing  
- HMAC (Hash-based Message Authentication Code)  
- Hashing vs Encoding vs Encryption  

---

# Task Breakdown & Notes

---

## Task 1: Introduction

**Objective:**  
Understand what hashing is and why it is used.

A hash function converts input data of any size into a fixed-size output (hash value), which uniquely represents the input.

---

### Question

Let’s begin!

**Answer:**  
No answer needed  

---

## Task 2: Hash Functions

### What is a Hash Function?

- No key involved  
- One-way (cannot reverse)  
- Fixed output size  
- Small input change → huge output change  

---

### Example Insight

Even a **1-bit difference** in input results in a completely different hash (avalanche effect).

---

### Hash Collisions

- Two different inputs → same hash  
- Unavoidable due to finite output space  
- Good algorithms make collisions extremely rare  

---

### Important Note

- MD5 and SHA1 are **insecure (collision attacks exist)**  
- SHA-256 and above are recommended  

---

### Questions

What is the SHA256 hash of the passport.jpg file?

**Answer:**

77148c6f605a8df855f2b764bcc3be749d7db814f5f79134d2aa539a64b61f02

**Explanation:**  
Computed using `sha256sum`, which generates a fixed-length hash of the file.

---

What is the output size in bytes of the MD5 hash function?

**Answer:**

16

**Explanation:**  
MD5 produces a 128-bit hash → 128 ÷ 8 = 16 bytes.

---

If you have an 8-bit hash output, how many possible hash values are there?

**Answer:**

256

**Explanation:**  
Total combinations = 2⁸ = 256 possible hash values.

---

## Task 3: Insecure Password Storage for Authentication

### Common Mistakes

- Storing passwords in plaintext  
- Using deprecated encryption  
- Using weak hashing (e.g., SHA1 without salt)  

---

### Real-World Examples

- RockYou → plaintext leak  
- Adobe → weak encryption + hints  
- LinkedIn → SHA1 without salt  

---

### Question

What is the 20th password in rockyou.txt?

**Answer:**

qwerty

**Explanation:**  
Retrieved using file inspection (e.g., `sed -n '20p' rockyou.txt`).

---

## Task 4: Using Hashing for Secure Password Storage

### Secure Approach

1. Choose strong hashing algorithm (bcrypt, scrypt, Argon2)  
2. Add unique salt  
3. Hash password + salt  
4. Store hash + salt  

---

### Rainbow Tables

- Precomputed hash → password mappings  
- Break unsalted hashes quickly  

---

### Key Defense

- Use **salting** → prevents identical hashes  
- Makes rainbow tables ineffective  

---

### Questions

Manually check the hash “4c5923b6a6fac7b7355f53bfe2b8f8c1”

**Answer:**

inS3CyourP4$$

**Explanation:**  
Matched using rainbow table lookup.

---

Crack the hash “5b31f93c09ad1d065c0491b764d04933”

**Answer:**

tryhackme

**Explanation:**  
Cracked using online hash database / lookup.

---

Should you encrypt passwords in password-verification systems? Yea/Nay

**Answer:**

Nay

**Explanation:**  
Encryption requires storing a key, which creates a single point of failure.

---

## Task 5: Recognising Password Hashes

### Linux Hash Storage

- Stored in `/etc/shadow`  
- Format:

$prefix$options$salt$hash

---

### Common Prefixes

| Prefix | Algorithm |
|--------|----------|
| $y$ | yescrypt |
| $7$ | scrypt |
| $2b$ | bcrypt |
| $6$ | SHA512 |
| $1$ | MD5 |

---

### Windows Hashes

- Stored in SAM  
- Use NTLM (MD4-based)  

---

### Questions

What is the hash size in yescrypt?

**Answer:**

256

**Explanation:**  
Yescrypt produces a 256-bit hash.

---

What’s the Hash-Mode listed for Cisco-ASA MD5?

**Answer:**

2410

**Explanation:**  
Obtained from Hashcat reference table.

---

What hashing algorithm is used in Cisco-IOS if it starts with $9$?

**Answer:**

scrypt

**Explanation:**  
Prefix `$9$` corresponds to scrypt in Cisco systems.

---

## Task 6: Password Cracking

### Key Idea

- Hashes are not decrypted → they are cracked  
- Try inputs until hash matches  

---

### Tools

- Hashcat (GPU-based)  
- John the Ripper (CPU-based)  

---

### Example Syntax

hashcat -m <type> -a 0 hash.txt wordlist.txt

---

### Questions

Crack hash1

**Answer:**

85208520

**Explanation:**  
Cracked using Hashcat with bcrypt mode.

---

Crack SHA256 hash

**Answer:**

halloween

**Explanation:**  
Wordlist attack matched hash value.

---

Crack hash3

**Answer:**

spaceman

**Explanation:**  
SHA512crypt cracked using correct hash mode.

---

Crack hash4

**Answer:**

funforyou

**Explanation:**  
Found via rainbow table / lookup.

---

## Task 7: Hashing for Integrity Checking

### Integrity Verification

- Same input → same hash  
- Any change → different hash  

Used for:
- File verification  
- Malware analysis  
- Detecting tampering  

---

### HMAC

- Combines hash + secret key  
- Provides:
  - Integrity  
  - Authenticity  

---

### Questions

What is SHA256 hash of libgcrypt file?

**Answer:**

09120c9867ce7f2081d6aaa1775386b98c2f2f246135761aae47d81f58685b9c

**Explanation:**  
Generated using `sha256sum` for integrity verification.

---

What’s the hashcat mode number for HMAC-SHA512?

**Answer:**

1750

**Explanation:**  
Retrieved from Hashcat mode reference.

---

## Task 8: Conclusion

### Key Distinction

| Concept | Description |
|--------|------------|
| Hashing | One-way transformation |
| Encoding | Reversible format change |
| Encryption | Reversible with key |

---

### Example

base64 encode → reversible

---

### Question

Decode RU5jb2RlREVjb2RlCg==

**Answer:**

ENcodeDEcode

**Explanation:**  
Base64 decoding returns original string.

---

Ensure you have noted the various concepts and tools explored in this room.

**Answer:**  
No answer needed  

---

# Reflection

Hashing is one of the most practically used concepts in cybersecurity, especially in authentication systems and forensic analysis. This room bridges both defensive and offensive perspectives by covering secure password storage and hash cracking techniques.

These concepts are directly applicable in:

- SOC investigations (log analysis, hash matching)  
- DFIR workflows (file integrity, malware hashing)  
- Password breach analysis  
- Threat intelligence (hash indicators)
