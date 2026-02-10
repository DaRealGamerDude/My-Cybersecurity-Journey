# Rakshna Recruitment CTF 2026

**Date Completed:** February 10–11, 2026  
**Difficulty:** Beginner–Intermediate  
**Format:** Multi-domain CTF (Forensics, Crypto, OSINT, Web)  
**Context:** Society recruitment challenge  
**Status:** Completed (All tasks solved)

---

## 🧠 Executive Summary

This write-up documents my second-ever Capture The Flag (CTF) experience, completed as part of the Rakshna recruitment process.

Unlike my first CTF (a SOC-focused, investigation-heavy challenge on TryHackMe), this CTF was broad and puzzle-driven, covering **forensics, cryptography, OSINT, and web security**. The shift in style forced me to move away from structured SOC workflows and instead rely on experimentation, pattern recognition, and tool exploration.

Each task tested a different way of thinking:
- **Forensics** rewarded attention to file structure and headers
- **Cryptography** exposed my weakest area and forced trial-and-error learning
- **OSINT** punished overthinking and rewarded basic investigative instincts
- **Web** strongly favored source-code awareness and prior development experience

Overall, this CTF highlighted both my strengths (forensics intuition, web fundamentals) and my weakest area (cryptography), while introducing new tools and workflows that I had not previously used.

---

## 🗂️ Challenge Breakdown

The CTF consisted of four independent tasks:

| Task | Category | Focus |
|-----|--------|------|
| Task 1 | Forensics | File headers & hex analysis |
| Task 2 | Cryptography | Encoding layers & classical ciphers |
| Task 3 | OSINT | Social media footprint analysis |
| Task 4 | Web | Client-side source code inspection |

---

## 🔍 Task 1 — The Ghost in the Header (Forensics)

### Problem Statement
A supposedly “sanitized” image file was intercepted. The file no longer opened in any image viewer, but we were told it *was* originally an image.

**Goal:** Recover the hidden message from the corrupted data.

---

### Approach & Analysis

The provided file appeared as a meaningless blob of data at first glance. The key realization was that **files don’t stop being files just because extensions are removed**.

Steps taken:
1. Inspected the raw data using a hex viewer
2. Looked for known **magic bytes / file signatures**
3. Identified a valid PNG header (`89 50 4E 47`)
4. Reconstructed the file by restoring its proper header and structure
5. Opened the recovered image normally

Once opened, the image contained a plaintext message revealing the flag.

---

### Result
**Flag:**  
`RAKSHNA{h3xdump_h3r0_2026}`

---

### Reflection

This was my favorite task.

It aligned closely with my interest in **DFIR and forensics**, and reinforced an important lesson:  
> Most “corrupted” files aren’t broken — they’re misunderstood.

Understanding file formats at the byte level is far more powerful than relying on tools alone.

---

## 🔐 Task 2 — 3-STEP VERIFICATION (Cryptography)

### Problem Statement
An intercepted message was protected by multiple layers of encoding. The final layer was hinted to be a **Vigenère cipher**, using the society’s name as the key.


