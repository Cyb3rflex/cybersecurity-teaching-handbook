# Curriculum Lesson-to-Lab Mapping Matrix

> **Standard Identifier**: `CURR-MAP-01`  
> **Status**: Approved Curriculum Mapping  
> **Repository Relationship**: Maps `cybersecurity-teaching-handbook` lessons to `cybersecurity-labs` environments

---

## 1. Mapping Overview & Principles

Every module in the teaching handbook pairs conceptual theoretical lessons with practical, reproducible laboratory exercises. This mapping matrix defines the formal connection between canonical lesson IDs and practical lab identifiers.

---

## 2. Master Mapping Matrix

| Module & Title | Lesson ID | Lesson Title | Lab ID | Lab Title & Focus | Isolation Tier | Existing Local Asset |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Mod 1: Foundations** | `SEC-MOD01-LES04` | The CIA Triad in Practice | `LAB-FOUND-01` | Data Integrity Verification with Hashes | Tier 1 (CLI) | New Python/Bash lab |
| **Mod 2: Linux & CLI** | `SEC-MOD02-LES03` | Users & Permissions | `LAB-LINUX-01` | Linux File Permission Auditing & SUID | Tier 1 (CLI) | Linux CLI exercises |
| **Mod 2: Linux & CLI** | `SEC-MOD02-LES09` | Safe Cybersecurity Labs | `LAB-LINUX-02` | Setting up Isolated Lab Networks | Tier 2 (Docker) | `CyberRange` network arch |
| **Mod 3: Networking** | `SEC-MOD03-LES04` | Ports, Sockets & Protocols | `LAB-NET-01` | Socket Inspection & Service Discovery | Tier 1 (Loopback) | Adapted from `net-scanner` |
| **Mod 3: Networking** | `SEC-MOD03-LES08` | HTTP vs. HTTPS Traffic | `LAB-NET-02` | Inspecting Plaintext vs TLS Traffic | Tier 1 (Loopback) | Local TLS inspection |
| **Mod 4: Web Security** | `SEC-MOD04-LES07` | SQL Injection Fundamentals | `LAB-WEB-01` | Vulnerable Login Bypass & Parameterized Queries | Tier 1 (127.0.0.1) | `CyberRange/labs/web-001` |
| **Mod 4: Web Security** | `SEC-MOD04-LES08` | Cross-Site Scripting (XSS) | `LAB-WEB-02` | Reflected & Stored XSS Mitigation | Tier 1 (127.0.0.1) | Express XSS sandbox |
| **Mod 5: Recon & OSINT**| `SEC-MOD05-LES06` | Subdomain & Path Enumeration | `LAB-RECON-01` | Passive Corporate Recon & Endpoint Discovery | Tier 1 (127.0.0.1) | `codeverse-recon-lab/recon-lab` |
| **Mod 5: Recon & OSINT**| `SEC-MOD05-LES09` | Introduction to Nmap | `LAB-RECON-02` | Local Service Fingerprinting | Tier 1 (127.0.0.1) | `codeverse-recon-lab/ennumeration-lab` |
| **Mod 6: Network Security**|`SEC-MOD06-LES01` | Network Attacks & Flooding | `LAB-NET-03` | HTTP Rate Limiting & DoS Mitigation | Tier 1 (127.0.0.1) | `ddos-defense-lab` |
| **Mod 6: Network Security**|`SEC-MOD06-LES03` | Packet Sniffing with Wireshark|`LAB-NET-04` | Packet Capture in Host-Only Networks | Tier 2 (Host-Only) | Docker bridge capture |
| **Mod 7: Social Engineering**|`SEC-MOD07-LES08`| Email Spoofing & Phishing | `LAB-SOCENG-01`| Automated Email Header & Indicator Triage | Tier 1 (CLI) | `email-analyzer` |
| **Mod 8: Pentesting** | `SEC-MOD08-LES04` | Methodology & Scoping | `LAB-PENT-01` | Writing Rules of Engagement & Scopes | Tier 1 (Doc/CLI) | Pentest methodology |
| **Mod 9: Malware Defense**|`SEC-MOD09-LES10`| Basic Malware Analysis Concepts|`LAB-MALW-01`| Static Analysis of Obfuscated Scripts | Tier 3 (Sandbox) | Isolated script analyzer |
| **Mod 10: Modern Security**|`SEC-MOD10-LES02`| Container Security Basics | `LAB-MOD-01` | Auditing Dockerfile Misconfigurations | Tier 1 (CLI) | Docker bench auditing |

---

## 3. Adaptation Standards for Reusable Assets

When adapting existing local assets into `cybersecurity-labs`:
1. **Source Preservation**: The original projects (`email-analyzer`, `ddos-defense-lab`, `codeverse-recon-lab`, `CyberRange`) remain pristine and unaltered.
2. **Network Sanitization**: Any adapted web server or API must be configured with `127.0.0.1` binding and non-privileged ports.
3. **Automated Verification**: Each adapted lab must include a standardized verification script (`test.js` or `test_lab.py`).
