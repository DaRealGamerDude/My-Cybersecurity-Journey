# TryHackMe Room: Cryptography Basics

**Path:** Cyber Security 101  
**Module Type:** Theory + Hands-on  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces the foundational concepts of cryptography and its role in securing communication across modern systems. It covers key terminology, basic encryption concepts, historical ciphers, and the distinction between symmetric and asymmetric encryption.

The room also introduces mathematical operations such as XOR and modulo, which serve as building blocks for many cryptographic algorithms.

Understanding these concepts is essential for cybersecurity roles, as cryptography underpins secure communication, authentication mechanisms, and data integrity verification in real-world systems.

---

# Key Concepts Covered

- Cryptography fundamentals (confidentiality, integrity, authenticity)
- Plaintext vs Ciphertext
- Encryption and decryption processes
- Caesar Cipher (historical cipher)
- Symmetric encryption (DES, 3DES, AES)
- Asymmetric encryption (RSA, Diffie-Hellman, ECC)
- XOR operation
- Modulo operation

---

# Task Breakdown & Notes

---

## 🔹 Task 1: Introduction

**Objective:**  
Understand the purpose of cryptography and what this room will cover.

Cryptography ensures secure communication by preventing unauthorized access and tampering. It is fundamental to modern systems such as HTTPS, SSH, and secure authentication mechanisms.

---

### Question

I’m ready to start learning about cryptography!

**Answer:**  
No answer needed  

---

## 🔹 Task 2: Importance of Cryptography

Cryptography ensures:

- **Confidentiality** → Data cannot be read by unauthorized parties  
- **Integrity** → Data cannot be altered without detection  
- **Authenticity** → Verifies identity of communicating parties  

Real-world usage includes:
- Login credentials encryption  
- Secure SSH sessions  
- HTTPS certificate verification  
- File integrity using hashing  

---

### Question

What is the standard required for handling credit card information?

**Answer:**

PCI DSS

**Explanation:**  
PCI DSS enforces security standards for storing and transmitting credit card data.

---

## 🔹 Task 3: Plaintext to Ciphertext

Core cryptographic flow:

Plaintext → Encryption + Key → Ciphertext Ciphertext → Decryption + Key → Plaintext

### Key Terms

- **Plaintext** → Original readable data  
- **Ciphertext** → Encrypted unreadable data  
- **Cipher** → Algorithm used for encryption/decryption  
- **Key** → Secret value used in encryption/decryption  
- **Encryption** → Converts plaintext → ciphertext  
- **Decryption** → Converts ciphertext → plaintext  

---

### Questions

What do you call the encrypted plaintext?

**Answer:**

ciphertext

---

What do you call the process that returns the plaintext?

**Answer:**

decryption

---

## 🔹 Task 4: Historical Ciphers

### Caesar Cipher

A substitution cipher where each letter is shifted by a fixed number.

Example:

Plaintext: TRYHACKME Key: 3 Ciphertext: WUBKDFNPH

Decryption reverses the shift.

---

### Security Insight

- Only 25 possible keys → easily brute-forced  
- Considered insecure by modern standards  

---

### Questions

Knowing that XRPCTCRGNEI was encrypted using Caesar Cipher, what is the original plaintext?

**Answer:**

ICANENCRYPT

---

## 🔹 Task 5: Types of Encryption

### Symmetric Encryption

- Same key for encryption and decryption  
- Fast and efficient  
- Key distribution is a challenge  

Examples:

- DES (insecure, 56-bit)
- 3DES (deprecated)
- AES (modern standard, 128/192/256-bit)

---

### Asymmetric Encryption

- Uses **public key + private key pair**  
- Public key → encryption  
- Private key → decryption  

Examples:

- RSA  
- Diffie-Hellman  
- ECC  

---

### Key Insight

- Symmetric → fast, used for bulk data  
- Asymmetric → secure key exchange  

---

### Questions

Should you trust DES? (Yea/Nay)

**Answer:**

Nay

---

When was AES adopted as an encryption standard?

**Answer:**

2001

---

## 🔹 Task 6: Basic Math

### XOR Operation

Truth table:

| A | B | A ⊕ B |
|--|--|--------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

### Key Properties

- A ⊕ A = 0  
- A ⊕ 0 = A  
- Reversible → useful in encryption  

Example:

1010 ⊕ 1100 = 0110

---

### XOR in Cryptography

C = P ⊕ K P = C ⊕ K

Used in simple symmetric encryption models.

---

### Modulo Operation

X % Y = remainder of X ÷ Y

Examples:

25 % 5 = 0 23 % 6 = 5 23 % 7 = 2

---

### Key Insight

- Used heavily in cryptographic algorithms  
- Not reversible → important for security  

---

### Questions

What’s 1001 ⊕ 1010?

**Answer:**

0011

---

What’s 118613842%9091?

**Answer:**

3565

---

What’s 60%12?

**Answer:**

0

---

## 🔹 Task 7: Summary

This room introduced:

- Importance of cryptography  
- Encryption fundamentals  
- Symmetric vs asymmetric encryption  
- Basic mathematical operations (XOR, modulo)  

These concepts form the foundation for more advanced cryptographic systems.

---

### Question

Before proceeding to the next room, make sure you have taken note of all the key terms and concepts introduced in this room.

**Answer:**  
No answer needed  

---

# Reflection

Cryptography is a core component of cybersecurity, enabling secure communication, authentication, and data integrity. Even though users rarely interact with it directly, it is embedded in nearly every secure system—from HTTPS to SSH and secure file verification.

This room establishes the foundational understanding required for analyzing encrypted traffic, understanding authentication mechanisms, and working with security tools in SOC and DFIR environments.
