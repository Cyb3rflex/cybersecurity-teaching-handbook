# Cybersecurity Curriculum Master Index & Learning Pathways

> **Document Status**: Canonical Curriculum Map  
> **Repository**: `cybersecurity-teaching-handbook`  
> **Format**: Portable Markdown (`.md`)

---

## 1. Curriculum Architecture & Pathways

The curriculum is structured into ten sequential, comprehensive modules designed to take students from baseline technical literacy to advanced defensive and offensive concepts.

### Suggested Learning Tracks:
1. **Foundations Track (Modules 1–3)**: Essential for all learners. Covers fundamentals, command line mastery, and computer networking.
2. **Defensive / SOC Analyst Track (Modules 1, 2, 3, 6, 7, 9, 10)**: Focuses on network defense, phishing triage, malware concepts, incident response, and cloud security.
3. **Offensive / Penetration Testing Track (Modules 1, 2, 3, 4, 5, 8)**: Focuses on web application security, OSINT/reconnaissance, and penetration testing methodologies.

---

## 2. 10-Module Master Outline

### [Module 1: Cybersecurity Foundations](modules/module-01-foundations/overview.md) (`SEC-MOD01`)
- `SEC-MOD01-LES01`: What is Cybersecurity?
- `SEC-MOD01-LES02`: Why Cybersecurity Matters Today
- `SEC-MOD01-LES03`: Cybersecurity vs. InfoSec vs. Ethical Hacking
- `SEC-MOD01-LES04`: The CIA Triad (Confidentiality, Integrity, Availability)
- `SEC-MOD01-LES05`: Threats, Vulnerabilities, Risks and Exploits
- `SEC-MOD01-LES06`: Understanding Attack Surfaces
- `SEC-MOD01-LES07`: Common Cyber Attacks Overview
- `SEC-MOD01-LES08`: Cybersecurity Career Pathways

### [Module 2: Linux & Command Line](modules/module-02-linux-cli/overview.md) (`SEC-MOD02`)
- `SEC-MOD02-LES01`: Introduction to Linux Architecture
- `SEC-MOD02-LES02`: Linux Filesystem Hierarchy
- `SEC-MOD02-LES03`: Users, Groups & Permissions
- `SEC-MOD02-LES04`: Essential Linux Navigation & File Commands
- `SEC-MOD02-LES05`: Process Management & System Services
- `SEC-MOD02-LES06`: Package Management (`apt`, `dpkg`)
- `SEC-MOD02-LES07`: Bash Scripting Essentials
- `SEC-MOD02-LES08`: Introduction to Kali Linux & Security Distributions
- `SEC-MOD02-LES09`: Designing Safe Cybersecurity Practice Environments

### [Module 3: Networking Fundamentals](modules/module-03-networking-fundamentals/overview.md) (`SEC-MOD03`)
- `SEC-MOD03-LES01`: What is a Computer Network?
- `SEC-MOD03-LES02`: IPv4 and IPv6 Addressing
- `SEC-MOD03-LES03`: MAC Addresses & Physical Layer
- `SEC-MOD03-LES04`: TCP/UDP Ports and Core Protocols
- `SEC-MOD03-LES05`: Connection-Oriented (TCP) vs Connectionless (UDP)
- `SEC-MOD03-LES06`: Domain Name System (DNS) Resolution
- `SEC-MOD03-LES07`: Dynamic Host Configuration Protocol (DHCP)
- `SEC-MOD03-LES08`: HTTP and HTTPS Mechanics
- `SEC-MOD03-LES09`: The OSI 7-Layer Reference Model
- `SEC-MOD03-LES10`: The TCP/IP 4-Layer Model
- `SEC-MOD03-LES11`: Network Address Translation (NAT) & Firewalls
- `SEC-MOD03-LES12`: Packet Journey: How Data Travels Across the Internet

### [Module 4: Web & Application Security](modules/module-04-web-application-security/overview.md) (`SEC-MOD04`)
- `SEC-MOD04-LES01`: Web Architecture: Frontend vs. Backend
- `SEC-MOD04-LES02`: Client-Server Communication & HTTP Verbs
- `SEC-MOD04-LES03`: Cookies, Sessions & Web Tokens
- `SEC-MOD04-LES04`: Authentication vs. Authorization
- `SEC-MOD04-LES05`: The OWASP Top 10 Framework
- `SEC-MOD04-LES06`: Injection Vulnerabilities & SQL Injection (SQLi)
- `SEC-MOD04-LES07`: Cross-Site Scripting (XSS) (Reflected, Stored, DOM)
- `SEC-MOD04-LES08`: Broken Object Level & Function Access Control
- `SEC-MOD04-LES09`: Unrestricted File Upload Vulnerabilities
- `SEC-MOD04-LES10`: Security Misconfigurations & Information Disclosure
- `SEC-MOD04-LES11`: Cross-Site Request Forgery (CSRF) & Modern Defenses
- `SEC-MOD04-LES12`: Secure Coding Basics & Input Sanitization

### [Module 5: Reconnaissance & OSINT](modules/module-05-reconnaissance-osint/overview.md) (`SEC-MOD05`)
- `SEC-MOD05-LES01`: Fundamentals of Information Gathering
- `SEC-MOD05-LES02`: Passive vs. Active Reconnaissance
- `SEC-MOD05-LES03`: Open Source Intelligence (OSINT) Methodologies
- `SEC-MOD05-LES04`: DNS Record Enumeration
- `SEC-MOD05-LES05`: WHOIS & Domain Ownership Records
- `SEC-MOD05-LES06`: Subdomain Discovery & Endpoint Enumeration
- `SEC-MOD05-LES07`: Technology Stack Fingerprinting (Headers, Wappalyzer)
- `SEC-MOD05-LES08`: Search Engine Dorking & Public Archives
- `SEC-MOD05-LES09`: Introduction to Network Scanning with Nmap
- `SEC-MOD05-LES10`: Structuring a Safe, Ethical Recon Workflow

### [Module 6: Network Security](modules/module-06-network-security/overview.md) (`SEC-MOD06`)
- `SEC-MOD06-LES01`: Common Network Attack Vectors
- `SEC-MOD06-LES02`: Packet Sniffing & Promiscuous Mode
- `SEC-MOD06-LES03`: Protocol Analysis with Wireshark
- `SEC-MOD06-LES04`: Address Resolution Protocol (ARP) Mechanics
- `SEC-MOD06-LES05`: ARP Cache Poisoning & Man-in-the-Middle (MitM)
- `SEC-MOD06-LES06`: DNS Spoofing & Cache Poisoning
- `SEC-MOD06-LES07`: Denial of Service (DoS) & Distributed DoS (DDoS)
- `SEC-MOD06-LES08`: Network Segmentation & VLANs
- `SEC-MOD06-LES09`: Virtual Private Networks (VPNs) & Tunnels
- `SEC-MOD06-LES10`: Intrusion Detection (IDS) vs Intrusion Prevention (IPS)

### [Module 7: Social Engineering & Phishing](modules/module-07-social-engineering-phishing/overview.md) (`SEC-MOD07`)
- `SEC-MOD07-LES01`: The Human Element in Cybersecurity
- `SEC-MOD07-LES02`: Principles of Influence & Social Engineering Tactics
- `SEC-MOD07-LES03`: Phishing Varieties: Bulk, Spear Phishing, Whaling
- `SEC-MOD07-LES04`: Mobile Deception: Smishing & Vishing
- `SEC-MOD07-LES05`: Credential Harvesting & Lookalike Websites
- `SEC-MOD07-LES06`: Malicious Hyperlinks & URL Shortener Abuse
- `SEC-MOD07-LES07`: Email Protocols & Spoofing (SMTP, SPF, DKIM, DMARC)
- `SEC-MOD07-LES08`: Automated & Manual Email Header Triage
- `SEC-MOD07-LES09`: Developing Phishing Awareness & Training Programs
- `SEC-MOD07-LES10`: Designing a Safe Phishing Analysis Laboratory

### [Module 8: Ethical Hacking & Penetration Testing](modules/module-08-ethical-hacking-pentesting/overview.md) (`SEC-MOD08`)
- `SEC-MOD08-LES01`: Ethical Hacking Defined: Scope & Legality
- `SEC-MOD08-LES02`: Rules of Engagement (RoE) & Legal Contracts
- `SEC-MOD08-LES03`: Standards: PTES, NIST SP 800-115, OSSTMM
- `SEC-MOD08-LES04`: Scoping & Pre-Engagement
- `SEC-MOD08-LES05`: Vulnerability Scanning vs Penetration Testing
- `SEC-MOD08-LES06`: Target Enumeration & Service Probing
- `SEC-MOD08-LES07`: Vulnerability Assessment & CVSS Scoring
- `SEC-MOD08-LES08`: Exploitation Concepts & Proof-of-Concepts (PoC)
- `SEC-MOD08-LES09`: Post-Exploitation Principles & Privilege Escalation
- `SEC-MOD08-LES10`: Lateral Movement & Persistence Concepts
- `SEC-MOD08-LES11`: Technical Penetration Test Reporting
- `SEC-MOD08-LES12`: Remediation Verification & Re-Testing

### [Module 9: Malware & Defensive Security](modules/module-09-malware-defensive-security/overview.md) (`SEC-MOD09`)
- `SEC-MOD09-LES01`: Malware Taxonomy & Anatomy
- `SEC-MOD09-LES02`: Viruses, Worms & Self-Replication
- `SEC-MOD09-LES03`: Trojan Horses & Remote Access Tools (RATs)
- `SEC-MOD09-LES04`: Ransomware Operation & Extortion Models
- `SEC-MOD09-LES05`: Spyware, Adware & Keyloggers
- `SEC-MOD09-LES06`: Rootkits & Kernel-Level Manipulation
- `SEC-MOD09-LES07`: Malware Delivery Vectors & Droppers
- `SEC-MOD09-LES08`: Static vs Dynamic Malware Analysis Fundamentals
- `SEC-MOD09-LES09`: Endpoint Detection & Response (EDR) Architecture
- `SEC-MOD09-LES10`: Security Information & Event Management (SIEM)
- `SEC-MOD09-LES11`: Incident Response Lifecycle (NIST SP 800-61)
- `SEC-MOD09-LES12`: Digital Forensics Baseline Principles

### [Module 10: Modern Cybersecurity](modules/module-10-modern-cybersecurity/overview.md) (`SEC-MOD10`)
- `SEC-MOD10-LES01`: Cloud Security Shared Responsibility Model
- `SEC-MOD10-LES02`: Container Security (Docker, Kubernetes Isolation)
- `SEC-MOD10-LES03`: REST & GraphQL API Security
- `SEC-MOD10-LES04`: Mobile Device Security & MDM
- `SEC-MOD10-LES05`: Internet of Things (IoT) & Operational Tech (OT)
- `SEC-MOD10-LES06`: Artificial Intelligence in Threat Detection
- `SEC-MOD10-LES07`: AI-Powered Attacks: Deepfakes & Synthetic Phishing
- `SEC-MOD10-LES08`: Identity & Access Management (IAM), MFA, SSO
- `SEC-MOD10-LES09`: Zero Trust Architecture (NIST SP 800-207)
- `SEC-MOD10-LES10`: DevSecOps & CI/CD Security Integration
- `SEC-MOD10-LES11`: Software Supply Chain Security & SBOMs
- `SEC-MOD10-LES12`: Cybersecurity Governance, Risk & Compliance (GRC)
