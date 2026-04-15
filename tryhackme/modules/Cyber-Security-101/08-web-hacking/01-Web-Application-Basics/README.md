# TryHackMe Room: Web Application Basics

**Path:** Web Hacking  
**Module Type:** Theory + Practical (Fundamentals)  
**Difficulty:** Beginner  
**Status:** Completed  

---

# Summary

This room introduces the **fundamentals of how web applications work**, focusing on:

- Client ↔ Server interaction  
- URL structure and components  
- HTTP request and response lifecycle  
- Request methods, headers, and bodies  
- Response codes and headers  
- Security headers and their role in defense  

It forms the **base layer for web security**, required before learning:
- Burp Suite  
- Web exploitation (XSS, SQLi, etc.)  

---

# Rooms in This Module

| Order | Section | Primary Focus | Status |
|------|--------|--------------|--------|
| 1 | Introduction | Overview of web apps | ✔ |
| 2 | Web Application Overview | Frontend vs Backend | ✔ |
| 3 | URL | Structure & components | ✔ |
| 4 | HTTP Messages | Request/Response basics | ✔ |
| 5 | Request Line & Methods | HTTP methods & usage | ✔ |
| 6 | Request Headers & Body | Data transmission | ✔ |
| 7 | Response Codes | Status handling | ✔ |
| 8 | Response Headers | Server responses | ✔ |
| 9 | Security Headers | Defensive controls | ✔ |
| 10 | Practical | HTTP interaction | ✔ |
| 11 | Conclusion | Wrap-up | ✔ |

---

# Key Concepts Covered (Module-Level)

- Web application architecture (Frontend / Backend)
- HTTP protocol fundamentals
- URL anatomy & attack surface
- HTTP methods (GET, POST, etc.)
- Request & response structure
- Headers as control mechanisms
- Status codes interpretation
- Security headers (CSP, HSTS, etc.)

---

# Room Notes & Task Breakdown

---

## Task 2: Web Application Overview

**Room Objective:**  
Understand how web applications are structured.

---

### Key Learning

- Frontend:
  - HTML → structure  
  - CSS → styling  
  - JavaScript → logic  

- Backend:
  - Web Server → handles requests  
  - Database → stores data  
  - Infrastructure → supports operations  
  - WAF → filters malicious traffic  

---

### Q1: Which component hosts web applications?

web server

**Explanation:**  
The web server processes incoming HTTP requests and serves content.

---

### Q2: Tool used to access web apps?

web browser

**Explanation:**  
Acts as the client that sends requests and renders responses.

---

### Q3: Security filtering layer?

web application firewall

**Explanation:**  
WAF blocks malicious traffic like SQLi/XSS before reaching server.

---

### Common Struggles

- Mixing frontend vs backend roles  
- Ignoring backend attack surface  
- Not understanding WAF importance  

---

## Task 3: Uniform Resource Locator (URL)

**Room Objective:**  
Understand structure and components of a URL.

---

### Key Learning

URL Components:
- Scheme (HTTP/HTTPS)
- Host (domain)
- Port
- Path
- Query String
- Fragment

---

### Q1: Secure protocol?

HTTPS

**Explanation:**  
Encrypts communication using TLS → prevents interception.

---

### Q2: Fake domain attack?

Typosquatting

**Explanation:**  
Attackers exploit similar-looking domains for phishing.

---

### Q3: Input data part of URL?

Query String

**Explanation:**  
User-controlled input → major injection point.

---

### Common Struggles

- Ignoring URL as attack surface  
- Not recognizing query manipulation risks  
- Missing phishing indicators  

---

## Task 4: HTTP Messages

**Room Objective:**  
Understand structure of HTTP communication.

---

### Key Learning

HTTP Message Structure:
- Start Line  
- Headers  
- Empty Line  
- Body  

Types:
- Request (client → server)  
- Response (server → client)  

---

### Q1: Server returns?

HTTP response

**Explanation:**  
Response contains requested data or error status.

---

### Q2: What separates headers and body?

Empty Line

**Explanation:**  
Critical delimiter in HTTP parsing.

---

### Common Struggles

- Confusing request vs response  
- Ignoring structure importance  
- Not visualizing packet flow  

---

## Task 5: HTTP Request Line & Methods

**Room Objective:**  
Understand request structure and methods.

---

### Key Learning

Request Line:

METHOD /path HTTP/version

---

### Common Methods

| Method | Purpose | Risk |
|-------|--------|------|
| GET | Fetch data | Info leakage |
| POST | Send data | Injection |
| PUT | Update data | Unauthorized modification |
| DELETE | Remove data | Data loss |

---

### Q1: Most used HTTP version?

HTTP/1.1

**Explanation:**  
Introduced persistent connections → widely adopted.

---

### Q2: Method to check allowed operations?

OPTIONS

**Explanation:**  
Used for enumeration of allowed methods.

---

### Q3: Resource identifier?

URL Path

**Explanation:**  
Specifies exact endpoint on server.

---

### Common Struggles

- Treating methods as harmless  
- Ignoring method-based vulnerabilities  
- Not understanding enumeration via OPTIONS  

---

## Task 6: HTTP Request Headers & Body

**Room Objective:**  
Understand metadata and data transmission.

---

### Key Learning

Important Headers:
- Host  
- User-Agent  
- Cookie  
- Content-Type  

Body Formats:
- URL Encoded  
- JSON  
- XML  
- Form Data  

---

### Q1: Domain header?

Host

**Explanation:**  
Defines target server for request.

---

### Q2: Default form encoding?

application/x-www-form-urlencoded

**Explanation:**  
Encodes data as key=value pairs.

---

### Q3: Where metadata exists?

Request Headers

**Explanation:**  
Headers guide how request is processed.

---

### Common Struggles

- Ignoring headers during analysis  
- Not understanding encoding formats  
- Missing cookie importance  

---

## Task 7: HTTP Response Codes

**Room Objective:**  
Understand server response behavior.

---

### Key Learning

Status Code Categories:

| Range | Meaning |
|------|--------|
| 1xx | Informational |
| 2xx | Success |
| 3xx | Redirection |
| 4xx | Client Error |
| 5xx | Server Error |

---

### Q1: Contains version + code?

Status Line

**Explanation:**  
First line defines outcome of request.

---

### Q2: Server failure category?

Server Error Responses

**Explanation:**  
5xx → server-side issues.

---

### Q3: Not found code?

404

**Explanation:**  
Resource does not exist.

---

### Common Struggles

- Memorizing without understanding  
- Ignoring status codes in debugging  
- Not linking codes to attack detection  

---

## Task 8: HTTP Response Headers

**Room Objective:**  
Understand server-side metadata.

---

### Key Learning

Important Headers:
- Content-Type  
- Server  
- Set-Cookie  
- Cache-Control  

---

### Q1: Header leaking server info?

Server

**Explanation:**  
Reveals backend tech → useful for attackers.

---

### Q2: HTTPS-only cookie flag?

Secure

**Explanation:**  
Prevents transmission over HTTP.

---

### Q3: JS-restricted cookie flag?

HttpOnly

**Explanation:**  
Prevents access via JavaScript → XSS mitigation.

---

### Common Struggles

- Ignoring response headers  
- Not recognizing info leakage  
- Missing cookie security flags  

---

## Task 9: Security Headers

**Room Objective:**  
Understand defensive mechanisms.

---

### Key Learning

Important Headers:
- CSP → controls resource loading  
- HSTS → forces HTTPS  
- X-Content-Type-Options → prevents MIME sniffing  
- Referrer-Policy → controls referrer data  

---

### Q1: CSP directive for scripts?

script-src

**Explanation:**  
Defines allowed script sources.

---

### Q2: HSTS directive for subdomains?

includeSubDomains

**Explanation:**  
Applies HTTPS enforcement across subdomains.

---

### Q3: Prevent MIME sniffing?

nosniff

**Explanation:**  
Forces browser to respect declared content type.

---

### Common Struggles

- Not understanding header impact  
- Ignoring misconfigurations  
- Treating headers as optional  

---

## Task 10: Practical HTTP Requests

**Room Objective:**  
Apply HTTP methods in practice.

---

### Q1: GET /api/users

THM{YOU_HAVE_JUST_FOUND_THE_USER_LIST}

**Explanation:**  
GET request retrieves data from server.

---

### Q2: POST update user

THM{YOU_HAVE_MODIFIED_THE_USER_DATA}

**Explanation:**  
POST modifies server-side data.

---

### Q3: DELETE user

THM{YOU_HAVE_JUST_DELETED_A_USER}

**Explanation:**  
DELETE removes resource.

---

### Common Struggles

- Not mapping methods to actions  
- Confusion between POST vs PUT  
- Not understanding API interaction  

---

# Tools / Technologies Used in This Module

- Web Browser  
- HTTP Protocol  
- Basic API interaction  

---

# Commands, Syntax & Patterns to Remember

HTTP Request Format

METHOD /path HTTP/version

Headers

Host: example.com  
User-Agent: Mozilla/5.0  

Common Methods

GET  
POST  
PUT  
DELETE  
OPTIONS  

---

# Reflection

This module builds the **foundation of web security**.

Key takeaways:

- Every web interaction = HTTP request  
- Every input = potential attack vector  
- Headers = control layer (and attack surface)  
- Security headers = first line of defense  

This is directly relevant for:

- SOC (log analysis of HTTP traffic)  
- DFIR (understanding attacker requests)  
- Web pentesting (Burp Suite, injections)
