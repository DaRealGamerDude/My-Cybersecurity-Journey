# TryHackMe Room: JavaScript Essentials

**Path:** Web Hacking  
**Module Type:** Theory + Practical (Client-Side Fundamentals)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **JavaScript (JS)** from a cybersecurity perspective, focusing on:

- Core programming concepts (variables, functions, loops)  
- Integration of JS within HTML  
- Client-side execution and browser interaction  
- Abuse of JS features (dialogue functions, control flow)  
- Understanding minified and obfuscated code  

It emphasizes how **legitimate JS functionality can be abused by attackers**, forming a critical base for understanding:
- XSS (Cross-Site Scripting)  
- Client-side bypasses  
- Malicious script behavior  

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | JS fundamentals overview | ✔ |
| 2 | Essential Concepts | Variables, loops, functions | ✔ |
| 3 | JavaScript Overview | Execution & console usage | ✔ |
| 4 | Integrating JS | Internal vs external JS | ✔ |
| 5 | Dialogue Functions | alert, prompt, confirm abuse | ✔ |
| 6 | Control Flow | Logic & bypassing checks | ✔ |
| 7 | Minified Files | Obfuscation & deobfuscation | ✔ |
| 8 | Best Practices | Secure coding principles | ✔ |
| 9 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered (Module-Level)

- Client-side execution of JavaScript  
- Variables, data types, functions, loops  
- DOM interaction (`document.getElementById`)  
- Internal vs external script loading  
- User interaction functions (alert, prompt, confirm)  
- Control flow logic and bypassing mechanisms  
- Code obfuscation & reverse engineering  
- Secure JS development practices  

---

# Room Notes & Task Breakdown

---

## Task 2: Essential Concepts

**Room Objective:**  
Understand core JavaScript building blocks.

---

### Key Learning

- Variables:
  - `var`, `let`, `const`
- Data Types:
  - string, number, boolean, object  
- Functions:
  - Reusable blocks of logic  
- Loops:
  - Execute code repeatedly  

---

### Q1: What allows repeated execution of code?

loop

**Explanation:**  
Loops (for, while) execute code blocks multiple times based on conditions.

---

### Common Struggles

- Confusing variable scopes (`var` vs `let`)  
- Not understanding loop boundaries  
- Treating functions as optional instead of reusable logic  

---

## Task 3: JavaScript Overview

**Room Objective:**  
Understand how JS executes in the browser.

---

### Key Learning

- JavaScript is **interpreted (not compiled)**  
- Runs directly in browser console  
- Uses `console.log()` for output  
- Executes client-side → visible to users  

---

### Q1: Output when x = 10?

The result is: 20

**Explanation:**  
Expression `x + y` evaluates to 20 → printed using `console.log`.

---

### Q2: JS type?

Interpreted

**Explanation:**  
Executed directly by browser engine (no compilation step).

---

### Common Struggles

- Thinking JS is secure (it’s not — fully visible)  
- Not using browser dev tools  
- Ignoring client-side exposure  

---

## Task 4: Integrating JavaScript in HTML

**Room Objective:**  
Understand how JS is embedded in web pages.

---

### Key Learning

Two integration methods:

| Type | Description |
|------|------------|
| Internal | JS inside `<script>` tag |
| External | JS in `.js` file |

---

### Q1: JS inside HTML?

Internal

**Explanation:**  
Code written directly within HTML file.

---

### Q2: Reusable method?

External

**Explanation:**  
External JS allows reuse across multiple pages.

---

### Q3: External file name?

thm_external.js

**Explanation:**  
Referenced via `<script src="...">`.

---

### Q4: Linking attribute?

src

**Explanation:**  
`src` specifies external JS file location.

---

### Common Struggles

- Not checking source code during testing  
- Ignoring external JS files (huge mistake in pentesting)  
- Missing hidden logic in separate files  

---

## Task 5: Abusing Dialogue Functions

**Room Objective:**  
Understand how JS interaction functions can be abused.

---

### Key Learning

Core functions:
- `alert()` → message  
- `prompt()` → user input  
- `confirm()` → boolean decision  

---

### Q1: Alert count in invoice.html?

5

**Explanation:**  
Loop executes alert multiple times → controlled via iteration.

---

### Q2: Input dialogue function?

prompt

**Explanation:**  
Used to capture user input dynamically.

---

### Q3: Stored value if input = Tesla?

Tesla

**Explanation:**  
Prompt returns user input → stored in variable.

---

### Insight

- These functions are **commonly abused in XSS attacks**  
- Can disrupt UX or inject malicious scripts  

---

### Common Struggles

- Underestimating alert/prompt abuse  
- Not linking to XSS concepts  
- Ignoring user input risks  

---

## Task 6: Bypassing Control Flow

**Room Objective:**  
Understand logic manipulation in JS.

---

### Key Learning

- Conditional statements:
  - `if-else`
- Control execution flow  
- Used in authentication logic  

---

### Q1: Output if age < 18?

You are a minor.

**Explanation:**  
Condition fails → else block executes.

---

### Q2: Admin password?

ComplexPassword

**Explanation:**  
Credentials exposed in client-side JS → easily bypassable.

---

### Insight

- Client-side validation is **NOT secure**  
- Attackers can:
  - Modify JS  
  - Bypass conditions  

---

### Common Struggles

- Trusting frontend validation  
- Not inspecting JS source  
- Missing hardcoded credentials  

---

## Task 7: Exploring Minified Files

**Room Objective:**  
Understand obfuscation and reverse engineering.

---

### Key Learning

- Minification:
  - Removes spaces, reduces size  
- Obfuscation:
  - Makes code unreadable  

---

### Q1: Alert message?

Welcome to THM

**Explanation:**  
Original logic preserved despite obfuscation.

---

### Q2: Value of obfuscated age?

21

**Explanation:**  
Hex math resolves to decimal value.

---

### Insight

- Obfuscation ≠ security  
- Code can always be reversed  

---

### Common Struggles

- Getting intimidated by obfuscated code  
- Not using deobfuscation tools  
- Assuming obfuscation = protection  

---

## Task 8: Best Practices

**Room Objective:**  
Understand secure JS development.

---

### Key Learning

- Never trust client-side validation  
- Avoid untrusted JS libraries  
- Do not hardcode secrets  
- Use obfuscation in production  

---

### Q1: Blindly include JS?

nay

**Explanation:**  
Untrusted scripts = supply chain attack risk.

---

### Common Struggles

- Including random CDN scripts  
- Hardcoding API keys  
- Ignoring supply chain risks  

---

# Tools / Technologies Used in This Module

- Google Chrome DevTools (Console)  
- JavaScript (Client-side)  
- HTML DOM interaction  
- Online obfuscation/deobfuscation tools  

---

# Commands, Syntax & Patterns to Remember

Variables

let x = 5;

Output

console.log("text");

Functions

function greet(name) { }

Loops

for (let i = 0; i < 10; i++)

DOM Manipulation

document.getElementById("id").innerHTML

User Input

prompt()  
alert()  
confirm()  

---

# Reflection

This module highlights a critical reality:

> **Client-side code is never secure**

Key takeaways:

- JS is fully visible → attackers can inspect everything  
- Authentication logic in JS = broken by design  
- Obfuscation slows attackers but doesn’t stop them  
- Input handling = major attack vector (XSS)  

This directly connects to:

- Web exploitation (XSS, DOM-based attacks)  
- SOC detection (malicious script behavior)  
- DFIR (analyzing injected scripts)
