# TryHackMe Room: Public Key Cryptography Basics

**Path:** Cyber Security 101  
**Module Type:** Theory + Hands-on  
**Difficulty:** Beginner  
**Status:** Completed  

---

## Summary

This room builds upon basic cryptography concepts and focuses on **asymmetric (public key) cryptography**. It explains how public/private key pairs are used to enable secure communication, authentication, and integrity over insecure networks.

Core topics include RSA, Diffie-Hellman key exchange, SSH authentication, digital signatures, certificates, and PGP/GPG.

These concepts are critical in real-world cybersecurity, especially in **secure communication protocols, authentication systems, and SOC investigations involving encrypted traffic and certificates**.

---

# Key Concepts Covered

- Authentication, Integrity, Confidentiality, Authenticity
- Asymmetric encryption (public/private keys)
- RSA algorithm fundamentals
- Diffie-Hellman key exchange
- SSH key-based authentication
- Digital signatures
- Certificates and trust chains
- PGP / GPG encryption

---

# Task Breakdown & Notes

---

## Task 1: Introduction

**Objective:**  
Understand how cryptography ensures secure communication through authentication, integrity, confidentiality, and authenticity.

---

### Key Security Properties

- **Authentication** → Verifying identity  
- **Authenticity** → Message comes from claimed source  
- **Integrity** → Data not altered  
- **Confidentiality** → Data hidden from unauthorized parties  

---

### Question

Let’s begin!

**Answer:**  
No answer needed  

---

## Task 2: Common Use of Asymmetric Encryption

Asymmetric encryption is primarily used to:
- **Securely exchange symmetric keys**
- Enable **authentication and verification**

---

### Analogy Mapping

| Analogy | Cryptographic Equivalent |
|--------|--------------------------|
| Secret Code | Symmetric key |
| Lock | Public key |
| Lock’s Key | Private key |

---

### Key Insight

- Asymmetric encryption is slow → used for **key exchange**
- Symmetric encryption is fast → used for **actual communication**

---

### Question

In the analogy presented, what real object is analogous to the public key?

**Answer:**

Lock

**Explanation:**  
The lock represents the public key since anyone can use it to encrypt data, but only the private key holder can unlock it.

---

## Task 3: RSA

RSA is a public-key cryptosystem based on the difficulty of factoring large numbers.

---

### Core Idea

- Easy: Multiply large primes  
- Hard: Factor large numbers  

This asymmetry provides security.

---

### RSA Variables (Important for CTFs)

| Variable | Meaning |
|---------|--------|
| p, q | Prime numbers |
| n | p × q |
| e | Public exponent |
| d | Private exponent |
| m | Plaintext |
| c | Ciphertext |

---

### Questions

Knowing that p = 4391 and q = 6659. What is n?

**Answer:**

29239669

**Explanation:**  
n is calculated as p × q.

---

Knowing that p = 4391 and q = 6659. What is ϕ(n)?

**Answer:**

29228620

**Explanation:**  
ϕ(n) = (p − 1)(q − 1), used in RSA key generation.

---

## Task 4: Diffie-Hellman Key Exchange

Used to securely establish a shared secret over an insecure channel.

---

### Key Idea

- No prior shared key needed  
- Both parties compute the **same secret independently**

---

### Process Summary

1. Agree on public values (p, g)  
2. Choose private values (a, b)  
3. Exchange computed public keys  
4. Compute shared secret  

---

### Questions

Consider p = 29, g = 5, a = 12. What is A?

**Answer:**

7

**Explanation:**  
A = g^a mod p.

---

Consider p = 29, g = 5, b = 17. What is B?

**Answer:**

9

**Explanation:**  
B = g^b mod p.

---

Knowing that p = 29, a = 12, and you have B, what is the key calculated by Bob?

**Answer:**

24

**Explanation:**  
Shared key = B^a mod p.

---

Knowing that p = 29, b = 17, and you have A, what is the key calculated by Alice?

**Answer:**

24

**Explanation:**  
Shared key = A^b mod p, both sides derive the same key.

---

## Task 5: SSH

SSH uses asymmetric cryptography for secure remote access.

---

### Key Concepts

- Server authentication via public key fingerprint  
- Client authentication via key pair  
- Private key must remain secret  

---

### Important Commands

ssh-keygen -t ed25519



ssh -i privateKey user@host

---

### Security Insight

- Private keys = equivalent to passwords  
- Permissions must be strict (600)  
- Used heavily in real-world infra + CTFs  

---

### Question

What algorithm does the key use?

**Answer:**

RSA

**Explanation:**  
The key type identifies the algorithm used for encryption/authentication.

---

## Task 6: Digital Signatures and Certificates

---

### Digital Signatures

- Created using **private key**
- Verified using **public key**
- Ensure:
  - Integrity  
  - Authenticity  

---

### Certificates

Used to verify identity (especially in HTTPS).

---

### Chain of Trust

Website → Organization → CA → Trusted by Browser

---

### Question

What does a remote web server use to prove itself to the client?

**Answer:**

Certificate

**Explanation:**  
Certificates verify server identity using trusted Certificate Authorities.

---

## Task 7: PGP and GPG

PGP (Pretty Good Privacy) and GPG are used for:

- Encryption  
- Digital signing  
- Secure email communication  

---

### Example Commands

gpg --full-gen-key



gpg --import backup.key



gpg --decrypt confidential_message.gpg

---

### Key Insight

- Public key → shared  
- Private key → secret  
- Passphrase protects private key  

---

### Question

What secret word does the message hold?

**Answer:**

Pineapple

**Explanation:**  
Message decrypted using the private GPG key.

---

## Task 8: Conclusion

---

### Key Terms

- **Cryptography** → Securing communication  
- **Cryptanalysis** → Breaking cryptographic systems  
- **Brute-force attack** → Trying all possibilities  
- **Dictionary attack** → Using common word lists  

---

### Question

Ensure you have noted the various techniques and tools discussed in this room.

**Answer:**  
No answer needed  

---

# Reflection

This room provides a strong foundation in asymmetric cryptography and its real-world applications. Concepts such as RSA, Diffie-Hellman, SSH authentication, and certificates are essential in modern cybersecurity.

Understanding these mechanisms is critical for:
- Analyzing secure network traffic  
- Investigating authentication mechanisms  
- Understanding TLS/HTTPS workflows  
- Working in SOC and DFIR environments
