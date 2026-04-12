# TryHackMe Room: Public Key Cryptography Basics

**Path:** Cyber Security 101  
**Module Type:** Theory + Hands-on  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces public key (asymmetric) cryptography and its role in securing modern digital communication. It explains how asymmetric systems solve key distribution problems, and how they enable authentication, integrity, and confidentiality.

Core concepts include RSA, Diffie-Hellman key exchange, SSH key authentication, digital signatures, certificates, and PGP/GPG encryption.

These concepts are critical in real-world cybersecurity, especially in areas such as secure communications, authentication systems, and network security protocols.

---

# Key Concepts Covered

- Authentication, Integrity, Confidentiality, Authenticity
- Asymmetric encryption (public/private key model)
- RSA algorithm
- Diffie-Hellman key exchange
- SSH key-based authentication
- Digital signatures
- Certificates and Certificate Authorities (CAs)
- PGP / GPG encryption
- Cryptanalysis, brute-force, dictionary attacks

---

# Room Notes & Task Breakdown

---

## Task 1: Introduction

**Objective:**  
Understand how cryptography ensures secure communication in real-world scenarios.

Core security properties:

- **Authentication** → Verifying identity  
- **Authenticity** → Message comes from claimed sender  
- **Integrity** → Data is not altered  
- **Confidentiality** → Data is not exposed  

---

### Question

Let’s begin!

**Answer:**  
No answer needed  

---

## Task 2: Common Use of Asymmetric Encryption

Asymmetric encryption is primarily used to **securely exchange symmetric keys**, since symmetric encryption is faster for actual communication.

---

### Analogy Mapping

| Analogy | Cryptographic Meaning |
|--------|----------------------|
| Secret Code | Symmetric key + cipher |
| Lock | Public key |
| Key | Private key |

---

### Key Insight

- Public key → shared openly  
- Private key → kept secret  
- Used once → then switch to symmetric encryption  

---

### Question

In the analogy presented, what real object is analogous to the public key?

**Answer:**

Lock

---

## Task 3: RSA

RSA is a public-key encryption algorithm based on the difficulty of factoring large numbers.

---

### Why RSA Works

- Easy → multiply primes  
- Hard → factor large numbers  

This one-way difficulty provides security.

---

### Key Variables (Important for CTFs)

| Variable | Meaning |
|---------|--------|
| p, q | Prime numbers |
| n | p × q |
| e | Public exponent |
| d | Private exponent |
| m | Plaintext |
| c | Ciphertext |

---

### Encryption & Decryption

c = m^e mod n m = c^d mod n

---

### Questions

Knowing that p = 4391 and q = 6659. What is n?

**Answer:**

29239669

---

Knowing that p = 4391 and q = 6659. What is ϕ(n)?

**Answer:**

29228620

---

## Task 4: Diffie-Hellman Key Exchange

Used to establish a shared secret over an insecure channel.

---

### Key Idea

Two parties generate a **shared key without ever transmitting it directly**.

---

### Process Summary

1. Public values: p, g  
2. Private keys: a, b  
3. Public keys:  
   - A = g^a mod p  
   - B = g^b mod p  
4. Shared secret:  
   - A^b mod p = B^a mod p  

---

### Security Insight

- Prevents key exposure during transmission  
- Commonly used in TLS handshakes  

---

### Questions

Consider p = 29, g = 5, a = 12. What is A?

**Answer:**

7

---

Consider p = 29, g = 5, b = 17. What is B?

**Answer:**

9

---

Knowing that p = 29, a = 12, and you have B from the second question, what is the key calculated by Bob?

**Answer:**

24

---

Knowing that p = 29, b = 17, and you have A from the first question, what is the key calculated by Alice?

**Answer:**

24

---

## Task 5: SSH

SSH uses asymmetric cryptography for secure remote access.

---

### Server Authentication

- Server presents public key  
- Client verifies fingerprint  
- Prevents MITM attacks  

---

### Client Authentication

Two methods:

- Password-based (less secure)  
- Key-based (preferred)  

---

### Key Generation

ssh-keygen -t ed25519

---

### Key Files

- Private key → must remain secret  
- Public key → shared with server  

---

### Security Notes

- Private key ≈ password → never share  
- Permissions must be restricted (`600`)  
- Can be used for persistence/backdoors in CTFs  

---

### Question

Check the SSH Private Key in ~/Public-Crypto-Basics/Task-5. What algorithm does the key use?

**Answer:**

RSA

---

## Task 6: Digital Signatures and Certificates

### Digital Signatures

- Created using private key  
- Verified using public key  

---

### Key Idea

- Ensures **authenticity + integrity**  
- Often signs a **hash**, not raw data  

---

### Certificates

Used to verify identity of servers (e.g., HTTPS).

---

### Chain of Trust

Server → Organization → Certificate Authority → Trusted Root CA

---

### Real-World Use

- HTTPS websites  
- TLS encryption  
- Browser trust model  

---

### Question

What does a remote web server use to prove itself to the client?

**Answer:**

Certificate

---

## Task 7: PGP and GPG

PGP (Pretty Good Privacy) and GPG are used for:

- File encryption  
- Email security  
- Digital signatures  

---

### Key Generation

gpg --full-gen-key

---

### Usage

gpg --import backup.key gpg --decrypt confidential_message.gpg

---

### Key Insight

- Public key → encrypt  
- Private key → decrypt  
- Private keys can be passphrase-protected  

---

### Question

Use GPG to decrypt the message in ~/Public-Crypto-Basics/Task-7. What secret word does the message hold?

**Answer:**

Pineapple

---

## 🔹 Task 8: Conclusion

### Key Terms

- **Cryptography** → Securing communication  
- **Cryptanalysis** → Breaking cryptographic systems  
- **Brute-force attack** → Try all possibilities  
- **Dictionary attack** → Try likely passwords  

---

### Question

Ensure you have noted the various techniques and tools discussed in this room.

**Answer:**  
No answer needed  

---

# Reflection

This room builds directly on basic cryptography and introduces real-world implementations of asymmetric encryption. Concepts like RSA, Diffie-Hellman, SSH authentication, and certificates are foundational to modern security protocols such as TLS and secure remote access.

Understanding these mechanisms is essential for SOC analysts and DFIR workflows, where identifying encrypted traffic, verifying certificates, and analysing authentication mechanisms are common tasks.
