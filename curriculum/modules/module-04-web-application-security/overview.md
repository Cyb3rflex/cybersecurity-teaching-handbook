# Module 4: Web & Application Security

> **Canonical Module ID**: `SEC-MOD04`  
> **Course Level**: Intermediate  
> **Total Estimated Duration**: 10 Hours  
> **Prerequisites**: `SEC-MOD01`, `SEC-MOD02`, `SEC-MOD03`

---

## 1. Module Overview & Pedagogical Scope
Web applications represent the primary external attack surface for most modern organizations. This module covers the architecture of web applications (frontends, backends, databases, APIs) and the principal vulnerabilities cataloged in the OWASP Top 10.

Students study the mechanics of SQL Injection (SQLi), Cross-Site Scripting (XSS), broken access controls, dangerous file uploads, and session flaws, followed by secure coding principles (parameterization, context-aware output encoding, least privilege).

---

## 2. Module Learning Outcomes
Upon completion of this module, students will demonstrate the ability to:
1. Explain the client-server interaction model, HTTP headers, cookies, and session management.
2. Identify and safely demonstrate SQL Injection and articulate the mechanism of parameterized queries.
3. Differentiate between Reflected, Stored, and DOM-based Cross-Site Scripting (XSS).
4. Evaluate web access control models and identify Direct Object Reference (IDOR) vulnerabilities.
5. Apply secure coding guidelines to prevent injection and authentication bypasses.

---

## 3. Lesson Sequence

| Lesson Number | Canonical ID | Lesson Title | Estimated Time | Hands-on Lab |
| :--- | :--- | :--- | :--- | :--- |
| **Lesson 1** | `SEC-MOD04-LES01` | How Websites Work | 45 mins | None |
| **Lesson 2** | `SEC-MOD04-LES02` | Frontend vs Backend Architecture | 45 mins | None |
| **Lesson 3** | `SEC-MOD04-LES03` | HTTP Requests, Responses & Headers | 45 mins | None |
| **Lesson 4** | `SEC-MOD04-LES04` | Cookies, Sessions & State | 45 mins | None |
| **Lesson 5** | `SEC-MOD04-LES05` | Authentication vs. Authorization | 45 mins | None |
| **Lesson 6** | `SEC-MOD04-LES06` | The OWASP Top 10 Framework | 60 mins | None |
| **Lesson 7** | `SEC-MOD04-LES07` | SQL Injection Fundamentals | 60 mins | `LAB-WEB-01` |
| **Lesson 8** | `SEC-MOD04-LES08` | Cross-Site Scripting (XSS) | 60 mins | `LAB-WEB-02` |
| **Lesson 9** | `SEC-MOD04-LES09` | Broken Access Control & IDOR | 45 mins | None |
| **Lesson 10** | `SEC-MOD04-LES10` | File Upload Vulnerabilities | 45 mins | None |
| **Lesson 11** | `SEC-MOD04-LES11` | Security Misconfigurations | 45 mins | None |
| **Lesson 12** | `SEC-MOD04-LES12` | Secure Coding Basics | 60 mins | None |

---

## 4. Practical Laboratories Overview
- **`LAB-WEB-01`**: SQL Injection Authentication Bypass & Remediation (Tier 1 Localhost `127.0.0.1`). Adapted from `CyberRange/labs/web-001`.
- **`LAB-WEB-02`**: XSS Payload Execution & Output Encoding Defenses (Tier 1 Localhost `127.0.0.1`).
