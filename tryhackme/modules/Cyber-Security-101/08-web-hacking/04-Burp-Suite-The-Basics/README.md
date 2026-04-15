# TryHackMe Room: Burp Suite — The Basics

**Path:** Web Hacking  
**Module Type:** Theory + Hands-on (Web Application Testing)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces **Burp Suite**, the industry-standard tool for web application security testing.

It focuses on:
- Intercepting HTTP/HTTPS traffic  
- Understanding Burp modules  
- Configuring proxy and browser integration  
- Basic web attack workflow (XSS example)  

Burp Suite enables:
> **Full visibility and control over web traffic**

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Overview of Burp Suite | ✔ |
| 2 | What is Burp Suite | Core concept & editions | ✔ |
| 3 | Features | Tools inside Burp | ✔ |
| 4 | Installation | Setup across OS | ✔ |
| 5 | Dashboard | Interface understanding | ✔ |
| 6 | Navigation | Tabs & shortcuts | ✔ |
| 7 | Options | Configuration settings | ✔ |
| 8 | Proxy | Traffic interception | ✔ |
| 9 | FoxyProxy | Browser integration | ✔ |
| 10 | Target Tab | Site mapping | ✔ |
| 11 | Burp Browser | Built-in browser | ✔ |
| 12 | Scoping | Traffic filtering | ✔ |
| 13 | HTTPS Proxying | Certificate handling | ✔ |
| 14 | Example Attack | XSS via Burp | ✔ |
| 15 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered (Module-Level)

- Proxy-based traffic interception  
- HTTP request/response manipulation  
- Web application mapping  
- Scope control  
- Client-side filter bypassing  
- XSS exploitation workflow  
- Browser–proxy integration  

---

# Room Notes & Task Breakdown

---

## Task 2: What is Burp Suite

**Room Objective:**  
Understand Burp Suite and its editions.

---

### Key Learning

- Burp Suite = **web pentesting framework**  
- Intercepts:
  - HTTP  
  - HTTPS traffic  
- Allows:
  - Modify requests before sending  
  - Modify responses before browser receives  

---

### Editions Overview

| Edition | Purpose |
|--------|--------|
| Community | Free, manual testing |
| Professional | Advanced tools + automation |
| Enterprise | Continuous automated scanning |

---

### Q1: Which edition runs on a server?

Burp Suite Enterprise  

**Explanation:**  
Enterprise performs **continuous automated scanning**.

---

### Q2: Burp used for web + ___ apps?

Mobile  

**Explanation:**  
Supports mobile + API testing as well.

---

### Common Struggles

- Thinking Burp = scanner (it’s primarily manual)  
- Confusing Community vs Pro capabilities  

---

## Task 3: Features of Burp Community

**Room Objective:**  
Understand key tools inside Burp.

---

### Key Learning

Core tools:

| Tool | Purpose |
|-----|--------|
| Proxy | Intercept traffic |
| Repeater | Modify & resend requests |
| Intruder | Brute-force / fuzz |
| Decoder | Encode/decode data |
| Comparer | Compare responses |
| Sequencer | Analyze randomness |

---

### Q1: Intercept requests tool?

Proxy  

**Explanation:**  
Core component — everything flows through it.

---

### Q2: Brute-force tool?

Intruder  

**Explanation:**  
Used for fuzzing & credential attacks.

---

### Common Struggles

- Not knowing when to use Repeater vs Intruder  
- Ignoring Proxy logs (huge mistake)  

---

## Task 5: The Dashboard

**Room Objective:**  
Understand Burp interface.

---

### Key Learning

Dashboard sections:

| Section | Purpose |
|--------|--------|
| Tasks | Background processes |
| Event Log | Activity tracking |
| Issue Activity | Vulnerabilities (Pro only) |
| Advisory | Detailed vulnerability info |

---

### Q1: Which menu shows actions/logs?

Event Log  

**Explanation:**  
Tracks proxy start, connections, etc.

---

### Common Struggles

- Ignoring logs (critical for debugging)  
- Overwhelmed by UI initially  

---

## Task 6: Navigation

**Room Objective:**  
Understand movement inside Burp.

---

### Key Learning

- Top bar → modules  
- Second bar → sub-tabs  
- Supports tab detaching  

---

### Shortcuts

| Shortcut | Tab |
|---------|-----|
| Ctrl + Shift + D | Dashboard |
| Ctrl + Shift + P | Proxy |
| Ctrl + Shift + R | Repeater |

---

### Q1: Ctrl + Shift + P?

Proxy tab  

**Explanation:**  
Quick access to interception.

---

### Common Struggles

- Slow navigation without shortcuts  
- Not exploring sub-tabs  

---

## Task 7: Options

**Room Objective:**  
Understand configuration settings.

---

### Key Learning

- Two settings types:
  - User (global)  
  - Project (session-based)  

---

### Q1: Cookie jar location?

Sessions  

**Explanation:**  
Session handling settings.

---

### Q2: Updates setting location?

User settings  

**Explanation:**  
Global configuration.

---

### Q3: Change shortcuts?

Misc  

**Explanation:**  
Keyboard bindings section.

---

### Q4: Override TLS per project?

yea  

**Explanation:**  
Project settings can override.

---

### Common Struggles

- Ignoring settings (limits control)  
- Not using search feature  

---

## Task 8: Burp Proxy

**Room Objective:**  
Understand traffic interception.

---

### Key Learning

- Intercepts requests before server  
- Allows:
  - Forward  
  - Drop  
  - Modify  
- Logs everything  

---

### Features

- HTTP history  
- WebSocket capture  
- Match & Replace (regex)  

---

### Key Takeaway

> Proxy = **full control over web traffic**

---

### Common Struggles

- Forgetting to turn intercept off  
- Not checking HTTP history  

---

## Task 9: FoxyProxy Setup

**Room Objective:**  
Route browser traffic through Burp.

---

### Key Learning

Proxy config:

IP

127.0.0.1  

Port

8080  

---

### Insight

- Browser traffic → Burp → Server  
- If intercept ON → browser hangs  

---

### Common Struggles

- Forgetting proxy is active  
- Browser not loading (intercept issue)  

---

## Task 10: Site Map & Target

**Room Objective:**  
Understand application mapping.

---

### Key Learning

- Site map = auto-generated structure  
- Captures:
  - Pages  
  - Endpoints  
  - APIs  

---

### Q1: Flag from unusual endpoint?

(Found via site exploration)

**Explanation:**  
Enumerated through sitemap.

---

### Common Struggles

- Not exploring all endpoints  
- Ignoring API calls  

---

## Task 11: Burp Browser

**Room Objective:**  
Use built-in browser.

---

### Key Learning

- Pre-configured Chromium  
- No manual proxy setup needed  

---

### Insight

- Faster setup  
- Useful in labs  

---

### Common Struggles

- Sandbox errors (Linux root)  
- Not using built-in browser  

---

## Task 12: Scoping

**Room Objective:**  
Limit traffic to target.

---

### Key Learning

- Define scope → reduce noise  
- Add target → Target tab → Add to scope  

---

### Important Setting

Intercept only in-scope traffic  

---

### Key Takeaway

> Scoping = cleaner + focused analysis

---

### Common Struggles

- Too much noise in proxy  
- Forgetting to set scope  

---

## Task 13: HTTPS Proxying

**Room Objective:**  
Handle TLS interception.

---

### Key Learning

- Need to trust Burp CA certificate  
- Without it → HTTPS errors  

---

### Steps

1. Download cert → http://burp/cert  
2. Import into browser  
3. Trust CA  

---

### Common Struggles

- HTTPS not working  
- Certificate not trusted  

---

## Task 14: Example Attack (XSS)

**Room Objective:**  
Perform basic XSS attack.

---

### Key Learning

- Client-side filters are weak  
- Burp bypasses them easily  

---

### Payload

<script>alert("Succ3ssful XSS")</script>

---

### Workflow

1. Submit normal request  
2. Intercept in Proxy  
3. Replace input with payload  
4. URL encode (Ctrl + U)  
5. Forward  

---

### Result

Alert popup → successful XSS  

---

### Insight

> Burp bypasses frontend validation completely

---

### Common Struggles

- Forgetting to encode payload  
- Testing only in browser (wrong approach)  

---

# Tools / Technologies Used in This Module

- Burp Suite Community Edition  
- HTTP / HTTPS protocols  
- FoxyProxy (Firefox extension)  
- Chromium (Burp browser)  

---

# Commands, Syntax & Patterns to Remember

Proxy

Intercept ON/OFF  
Forward / Drop  

Encoding

Ctrl + U (URL encode)  

Navigation

Ctrl + Shift + P (Proxy)  

Scope

Add to scope → Target tab  

---

# Reflection

This module introduces:

> **how attackers see web applications**

Key takeaways:

- Burp = visibility + control  
- Client-side validation is useless against attackers  
- Traffic manipulation = core web exploitation skill  
- Mapping endpoints = foundation of web attacks  

This directly connects to:

- XSS  
- SQL Injection  
- Authentication bypass  
- API exploitation  
