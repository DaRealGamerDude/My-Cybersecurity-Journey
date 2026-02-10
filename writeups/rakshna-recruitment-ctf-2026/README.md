# [Rakshna Recruitment CTF 2026](https://www.rakshnamait.com/events)

**Date Completed:** February 10, 2026  
**Difficulty:** Beginner–Intermediate  
**Format:** Multi-domain CTF (Forensics, Crypto, OSINT, Web)  
**Context:** Society recruitment challenge  
**Status:** Completed (All tasks solved)

---

## Executive Summary

This write-up documents my second-ever Capture The Flag (CTF) experience, completed as part of the Rakshna recruitment process.

Unlike my first CTF (a SOC-focused, investigation-heavy challenge on TryHackMe), this CTF was broad and puzzle-driven, covering **forensics, cryptography, OSINT, and web security**. The shift in style forced me to move away from structured SOC workflows and instead rely on experimentation, pattern recognition, and tool exploration. Like my first CTF, I did rely on ChatGPT for some tasks but that was more to guide me in a particular direction than to just CTRL + C and V the answers and thus lose a crucial learning opportunity from this CTF.

Each task tested a different way of thinking:
- **Forensics** rewarded attention to file structure and headers
- **Cryptography** exposed my weakest area and forced trial-and-error learning
- **OSINT** punished overthinking and rewarded basic investigative instincts
- **Web** strongly favored source-code awareness and prior development experience

Overall, this CTF highlighted both my strengths (forensics intuition, web fundamentals) and my weakest area (cryptography), while introducing new tools and workflows that I had not previously used.

---

## Challenge Breakdown

The CTF consisted of four independent tasks:

| Task | Category | Focus |
|-----|--------|------|
| Task 1 | Forensics | File headers & hex analysis |
| Task 2 | Cryptography | Encoding layers & classical ciphers |
| Task 3 | OSINT | Social media footprint analysis |
| Task 4 | Web | Client-side source code inspection |

<img width="1600" height="999" alt="image" src="https://github.com/user-attachments/assets/b6b92a22-f48b-4927-934f-9677ef41c998" />

---

## Task 1 — The Ghost in the Header (Forensics)

### Problem Statement
A supposedly “sanitized” image file was intercepted. The file no longer opened in any image viewer, but we were told it *was* originally an image.

**Goal:** Recover the hidden message from the corrupted data.

---

### Approach & Analysis

The provided file appeared as a meaningless blob of data at first glance. The key realization was that **files don’t stop being files just because extensions are removed**.

Steps taken:
1. Inspected the raw data using a hex viewer
<img width="1600" height="1002" alt="image" src="https://github.com/user-attachments/assets/3d24a17b-a069-4f52-8fc4-6f432e0fb02a" />
2. Looked for known **magic bytes / file signatures**
3. Identified a valid PNG header (`89 50 4E 47`)
4. Reconstructed the file by restoring its proper header and structure
<img width="1600" height="1000" alt="image" src="https://github.com/user-attachments/assets/fb45f087-dbd0-4e68-85cd-35495d7b3b66" />
5. Opened the recovered image normally

Once opened, the image contained a plaintext message revealing the flag.
`will add image once the ctf is over`
---

### Result
**Flag:**  
`RAKSHNA{I'll-reveal-the-flag-after-the-ctf-ends}`

---

### Reflection

This was my favorite task.

It aligned closely with my interest in **DFIR and forensics**, and reinforced an important lesson:  
> Most “corrupted” files aren’t broken — they’re misunderstood.

Understanding file formats at the byte level is far more powerful than relying on tools alone.

---

## Task 2 — 3-STEP VERIFICATION (Cryptography)

### Problem Statement
An intercepted message was protected by multiple layers of encoding. The final layer was hinted to be a **Vigenère cipher**, using the society’s name as the key.


---

### Approach & Analysis

This task was the hardest for me due to minimal prior experience with cryptography and thus I used ChatGPT to help me with this one but instead of blindly copy pasting I instead asked it to provide me witht a step by step guide on how to deal with Cryptography problems, the things to check for, tools to use, etc.. and I think it ended up teaching me a lot more than if I just left it blank or blidnly copy pasted the answer from somewhere.

What I identified early:
- The string was clearly **Base64**
- The problem description hinted that **Base64 was not the final step**

The challenge came after decoding:
- The output did not resemble readable plaintext
- Multiple transformations were attempted: UTF-8, XOR, hex conversions but to no avail as shown below
<img width="1080" height="1080" alt="Untitled design" src="https://github.com/user-attachments/assets/c80f6369-7ef2-4284-87e7-738420bc7c10" />

Eventually, through experimentation (image below):
1. Base64 decoding revealed structured binary data
2. Applying **Vigenère decoding** using the key `RAKSHNA`
3. Further transformations unexpectedly revealed a readable string
4. The final output resolved into the flag
<img width="1080" height="1080" alt="Untitled design" src="https://github.com/user-attachments/assets/cc060133-8376-4077-a2e5-1bf633c69fa1" />

This solution path was not linear and involved significant trial-and-error, but it reinforced how layered encodings often hide simple results beneath complexity.

---

### Result
**Flag:**  
`RAKSHNA{I'll-reveal-the-flag-after-the-ctf-ends}`

---

### Reflection

This task exposed a clear weakness in my skill set.

Cryptography requires:
- Familiarity with classical ciphers
- Comfort with layered transformations
- Confidence in experimenting without immediately “understanding” the output

While frustrating, it was also the most educational task because it forced me to explore tools and techniques I would normally avoid.

---

## Task 3 — The Trail of Breadcrumbs (OSINT)

### Problem Statement
A hint suggested that the society’s social media presence might contain clues.

**Goal:** Track down the hidden flag using open-source intelligence.

---

### Approach & Analysis

My initial mistake was overcomplicating the problem.

Steps taken:
1. Reviewed official social media posts for hidden hints
2. Found nothing immediately obvious
3. Shifted focus to **followers and associated accounts**
4. Identified an unusual account created in August 2025
5. Checked the bio of that account
6. Discovered a **Pastebin link**
7. Retrieved the flag from the paste content

<img width="1080" height="1080" alt="Untitled design (1)" src="https://github.com/user-attachments/assets/a9f83c2e-ff4f-4585-ba08-5dd0fe58ef21" />

---

### Result
**Flag:**  
`RAKSHNA{I'll-reveal-the-flag-after-the-ctf-ends}`

---

### Reflection

In hindsight, this task was simple.

The biggest lesson here was:
> OSINT is often about **where to look**, not how deep to go.

I made the task harder by assuming complexity where none was required. Sometimes, the answer really *is* in plain sight.

---

## Task 4 — The Administrator’s Oversight (Web)

### Problem Statement
A prototype login portal was provided. The challenge hinted that developers had left critical information exposed client-side.

**Goal:** Reconstruct the flag from:
- Styles
- Elements
- Script

---

### Approach & Analysis

This task was solved quickly due to prior web development experience.

Steps taken:
1. Opened browser developer tools
2. Viewed page source
3. Inspected:
   - CSS comments (Styles)
   - Hidden HTML attributes (Elements)
   - JavaScript functions (Script)
4. Identified all three flag fragments directly in the client-side code
5. Reassembled them into a single flag

<img width="830" height="1268" alt="image" src="https://github.com/user-attachments/assets/61ca8742-d6e6-455e-8cb5-2f12a3c2e3f1" />

No authentication bypass or brute forcing was required — everything was already exposed.

---

### Result
**Flag:**  
`RAKSHNA{I'll-reveal-the-flag-after-the-ctf-ends}`

---

## Overall Takeaways

- File format knowledge is essential for forensic analysis
- Cryptography is a clear gap I need to strengthen
- OSINT rewards restraint more than creativity
- Web vulnerabilities often come from developer assumptions
- Tool exploration is part of learning — not a shortcut

---

## Tools & Platforms Used

- Hex editors / CyberChef
- Browser Developer Tools
- Base64 & classical cipher decoding
- Social media platforms
- Pastebin
- ChatGPT, specifically for assistance with the Cryptography task because I have no prior experience in it.

---

## 📌 What I’ll Improve Before the Next CTF

- Build foundational cryptography intuition
- Practice identifying encoding layers faster
- Reduce overanalysis during OSINT challenges
- Continue strengthening DFIR fundamentals

---

## Closing Note

This CTF was very different from my first SOC-focused challenge, but equally valuable.  
It confirmed my interest in defensive security while showing me where my fundamentals still need work.

Write-ups like this are part of how I track that progress.
