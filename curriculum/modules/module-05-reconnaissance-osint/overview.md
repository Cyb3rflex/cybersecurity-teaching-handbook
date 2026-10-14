# Module 5: Reconnaissance & OSINT

> **Canonical Module ID**: `SEC-MOD05`  
> **Course Level**: Intermediate  
> **Total Estimated Duration**: 8 Hours  
> **Prerequisites**: `SEC-MOD01`, `SEC-MOD02`, `SEC-MOD03`

---

## 1. Module Overview & Pedagogical Scope
Reconnaissance is the initial phase of both security assessments and malicious attacks. This module establishes a rigorous ethical framework for collecting intelligence legally and responsibly.

Students examine passive OSINT methodologies—such as public DNS record harvesting, WHOIS registries, search engine dorking, and passive technology fingerprinting—before progressing to active reconnaissance with port scanning and service enumeration using Nmap. All active exercises are strictly scoped to isolated local targets.

---

## 2. Module Learning Outcomes
Upon completion of this module, students will demonstrate the ability to:
1. Differentiate between passive and active reconnaissance and understand the legal and operational boundaries of each.
2. Query and interpret DNS resource records (`A`, `MX`, `TXT`, `NS`, `CNAME`).
3. Conduct passive OSINT using search operators, certificate transparency logs, and archive databases.
4. Perform localized, authorized port scanning and service fingerprinting using Nmap against simulated localhost services.
5. Synthesize reconnaissance findings into a structured attack surface report.

---

## 3. Lesson Sequence

| Lesson Number | Canonical ID | Lesson Title | Estimated Time | Hands-on Lab |
| :--- | :--- | :--- | :--- | :--- |
| **Lesson 1** | `SEC-MOD05-LES01` | What is Reconnaissance? | 45 mins | None |
| **Lesson 2** | `SEC-MOD05-LES02` | Passive vs Active Recon | 45 mins | None |
| **Lesson 3** | `SEC-MOD05-LES03` | OSINT Fundamentals | 45 mins | None |
| **Lesson 4** | `SEC-MOD05-LES04` | DNS Reconnaissance | 45 mins | None |
| **Lesson 5** | `SEC-MOD05-LES05` | WHOIS & Registrar Records | 45 mins | None |
| **Lesson 6** | `SEC-MOD05-LES06` | Subdomain & Directory Enumeration | 60 mins | `LAB-RECON-01` |
| **Lesson 7** | `SEC-MOD05-LES07` | Technology Fingerprinting | 45 mins | None |
| **Lesson 8** | `SEC-MOD05-LES08` | Search Engine Recon & Dorking | 45 mins | None |
| **Lesson 9** | `SEC-MOD05-LES09` | Introduction to Nmap | 60 mins | `LAB-RECON-02` |
| **Lesson 10** | `SEC-MOD05-LES10` | Building a Recon Workflow | 45 mins | None |

---

## 4. Practical Laboratories Overview
- **`LAB-RECON-01`**: Passive Corporate Recon & Endpoint Discovery (Tier 1 Localhost `127.0.0.1:3000`). Adapted from `codeverse-recon-lab/recon-lab`.
- **`LAB-RECON-02`**: Service Enumeration and Report Generation (Tier 1 Localhost). Adapted from `codeverse-recon-lab/ennumeration-lab`.
