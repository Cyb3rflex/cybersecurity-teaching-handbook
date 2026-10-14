# Cybersecurity Teaching Handbook: Stage 2 Architecture & Implementation Specification

> **Document Status**: Stage 2 Implementation Note  
> **Repository**: `cybersecurity-teaching-handbook`  
> **Classification**: Educational Architecture & Policy Specification (Documentation-Only)  
> **Format**: Portable Markdown (`.md`)

---

## 1. Executive Summary & Core Directives

This specification incorporates all approved architectural principles and strict operational constraints for the **Cybersecurity Teaching Handbook** and its companion practical laboratory ecosystem.

### Core Directives Summary
1. **Preserve and Verify Existing Projects**: No destructive operations, blind copying, unauthorized modifications, or renaming of existing sibling projects (`cybersecurity-curriculum`, `email-analyzer`, `ddos-defense-lab`, `codeverse-recon-lab`, `net-scanner`, `CyberRange`, `ThreatIQ`). Reusable assets are audited for structure, dependencies, license, and functionality before planned adaptation.
2. **Handbook is Strictly Documentation-Only**: The `cybersecurity-teaching-handbook` repository consists solely of portable, structured Markdown (`.md`) files. No static site generators (Docusaurus, VitePress, Hugo), frontend frameworks (React, Vite), databases, dashboards, APIs, or web deployment pipelines are permitted within this repository.
3. **Correct Cross-Repository Linking**: Repositories remain decoupled and independent. Cross-repository references rely on **canonical IDs** and documented side-by-side local directory conventions rather than broken relative paths (`../`) on remote git hosts. No premature GitHub URLs are assumed.
4. **Practical Lab Safety & Network Isolation**: Localhost (`127.0.0.1`) binding is the mandatory default for all web application targets. For multi-host network exercises, labs must utilize isolated host-only virtual networks (Docker bridge or hypervisor host-only switch) with explicit scope definitions and automated teardown. Default scanning of host LANs, public IPs, or third-party networks is strictly prohibited.
5. **Separation of Student Materials & Instructor Answer Keys**: Public educational materials must never store confidential answer keys or walk-through solutions. Solution keys must reside in a separate private repository or access-controlled boundary—not hidden in Markdown comments, obfuscated file names, or subdirectories in a public repository.
6. **Empirical Quality Assurance & Environment Compatibility**: Lab verification requires execution of actual functional tests on real target systems. Environment dependencies (Node.js runtime, Python versions) and platform constraints (Windows native vs. WSL2 vs. Linux) are verified and documented.
7. **Strict Scope Control**: Execution is bounded strictly to **Stage 2** (directory structure, Markdown templates, lab specification standard, repository guide, curriculum index, and mapping conventions). Complete lesson text generation and git commit/push actions are deferred until Stage 2 review.

---

## 2. Audit of Existing Cybersecurity Projects

Before proposing reuse or lab adaptation, the existing projects located in the local development environment were inspected:

| Project Name | Primary Stack | Dependencies & Runtimes | License Status | Current Functionality & Reusability Assessment |
| :--- | :--- | :--- | :--- | :--- |
| **`cybersecurity-curriculum`** | Markdown, HTML/CSS/JS | Standalone web viewer (`index.html`, `script.js`, `styles.css`) + 71 KB master curriculum (`cybersecurity-curriculum.md`) | None found | **High Reuse**: Contains complete 10-module curriculum structure covering Foundations, Linux/CLI, Networking, Web Security, Recon/OSINT, Network Attacks, Social Engineering, Pentesting, Malware Defense, and Modern Security. Outlines serve as the canonical baseline. Project files remain untouched. |
| **`email-analyzer`** | Python 3 | Pure Python standard library (`email`, `re`, `urllib.parse`, `sys`). Zero external dependencies. | None found | **Verified Reusable Asset**: CLI triage tool parses `.eml` headers, identifies `From`/`Reply-To` mismatches, scores phishing keywords, extracts IP/domain URLs. Executed and verified functional under Python 3.14.4 on Windows. Maps to Module 7 (Social Engineering & Phishing). |
| **`ddos-defense-lab`** | Node.js / Express | Express `^5.2.1`, Node.js v24.x | ISC (`package.json`) | **Reusable Asset**: Demonstrates HTTP request flooding and rate limiting. Must be audited to ensure bindings are constrained to `127.0.0.1` before deployment in the labs repository. |
| **`codeverse-recon-lab`** | Node.js / Express | Express web servers (`recon-lab` on port 3000, `ennumeration-lab`) | None found | **Reusable Asset**: Simulates corporate web endpoints, `robots.txt`, backup directories, and enumeration targets. Suitable for passive/active recon labs (Module 5). |
| **`net-scanner`** | Python | `scapy`, Python venv | None found | **Conditional Asset**: Scans local network using ARP packets. Platform limitations: requires packet capture driver (Npcap on Windows) and admin privileges. Must be adapted so it never scans the user's host LAN by default; must bind only to isolated virtual networks. |
| **`CyberRange`** | Multi-container Docker | Node.js/Express, React/Vite, Postgres, Redis, Docker Compose | None found | **Reference Architecture**: Orchestrated containerized environment with dedicated attacker and target subnets. Serves as a reference design for Tier 2/3 multi-host network labs. |
| **`ThreatIQ`** | React 18, Node.js | React/Vite, Tailwind CSS, Express | None found | **Separate Application**: Gamified awareness platform. Not a standalone lab exercise; remains preserved without modification. |

---

## 3. Handbook Repository Architecture (Documentation-Only)

The repository layout for `cybersecurity-teaching-handbook` adheres strictly to standard Markdown files organized hierarchically:

```text
cybersecurity-teaching-handbook/
├── README.md                                # Master repository documentation & navigation
├── CONTRIBUTING.md                          # Contribution standards & template rules
├── LICENSE                                  # Open documentation license (CC-BY-4.0)
├── docs/                                    # Architectural specifications and policies
│   ├── STAGE_2_SPECIFICATION.md            # Comprehensive architecture & implementation note (this document)
│   ├── cross-repository-linking.md         # Linking strategy & local workspace conventions
│   ├── lab-safety-framework.md             # Lab isolation tiers, networking rules & cleanup
│   ├── instructor-solution-policy.md       # Public handbook vs. private instructor solution boundaries
│   ├── quality-assurance-and-compatibility.md # Testing protocols, runtime matrices & platform notes
│   └── lesson-to-lab-mapping.md            # Canonical matrix mapping lessons to practical exercises
├── templates/                               # Standardized schemas for content creation
│   ├── lesson-template.md                  # Standard template for student lessons
│   ├── module-overview-template.md         # Standard template for module overviews
│   ├── lab-specification-template.md       # Standard template for companion practical labs
│   ├── assessment-template.md              # Standard template for module quizzes and tests
│   └── instructor-guide-template.md        # Standard template for educator delivery notes
└── curriculum/                              # Core educational curriculum
    ├── README.md                            # Curriculum Index & Module Roadmap
    └── modules/                             # Module directories (Modules 01 - 10)
        ├── module-01-foundations/
        │   └── overview.md
        ├── module-02-linux-cli/
        │   └── overview.md
        ├── module-03-networking-fundamentals/
        │   └── overview.md
        ├── module-04-web-application-security/
        │   └── overview.md
        ├── module-05-reconnaissance-osint/
        │   └── overview.md
        ├── module-06-network-security/
        │   └── overview.md
        ├── module-07-social-engineering-phishing/
        │   └── overview.md
        ├── module-08-ethical-hacking-pentesting/
        │   └── overview.md
        ├── module-09-malware-defensive-security/
        │   └── overview.md
        └── module-10-modern-cybersecurity/
            └── overview.md
```

---

## 4. Cross-Repository Linking Strategy

To maintain complete decoupling between the documentation handbook and the companion practical labs repository, the following linking model is enforced:

### 4.1 Recommended Local Workspace Arrangement
Learners and educators clone both repositories as siblings within a unified workspace directory:

```text
workspace-root/
├── cybersecurity-teaching-handbook/  # (This repo) Documentation, guides, curriculum
└── cybersecurity-labs/               # (Companion repo) Code, environments, Dockerfiles, scripts
```

### 4.2 Canonical Reference Identifiers
All educational units and practical exercises are referenced using deterministic canonical identifiers:
- **Lesson IDs**: `SEC-MOD<module_num>-LES<lesson_num>` (e.g., `SEC-MOD07-LES08` for Module 7, Lesson 8: Email Spoofing).
- **Lab Specification IDs**: `LAB-<domain>-<lab_num>` (e.g., `LAB-SOCENG-01` for Email Header Analysis).
- **Assessment IDs**: `ASSESS-MOD<module_num>` (e.g., `ASSESS-MOD07`).

### 4.3 GitHub and Local Link Resolution
- Direct relative file paths across repositories (`../cybersecurity-labs/labs/...`) break when viewed on GitHub.
- Handbook documents must state the companion **Lab ID** and relative path within the companion repository:
  > **Associated Lab**: `LAB-SOCENG-01`  
  > **Lab Directory in `cybersecurity-labs`**: `labs/social-engineering/lab-01-email-analyzer/`
- No hardcoded public remote URLs (`https://github.com/user/...`) are published until repositories are officially created and verified.

---

## 5. Practical Lab Safety and Network Isolation Framework

Practical cybersecurity labs carry operational risks if misconfigured. The safety framework enforces three isolation tiers:

### 5.1 Tier 1: Localhost Application Labs (Default)
- **Scope**: Single-process web applications, scripts, static analyzers, and code analysis exercises.
- **Rule**: All sockets and services MUST bind strictly to `127.0.0.1` (IPv4 loopback) or `::1` (IPv6 loopback).
- **Prohibition**: Binding to `0.0.0.0` or exposing ports on external network interfaces is strictly forbidden.

### 5.2 Tier 2: Host-Only Multi-Node Network Labs
- **Scope**: Exercises requiring multiple simulated machines (e.g., simulated client, DNS server, vulnerable web target).
- **Rule**: Must use an isolated, non-routed virtual network:
  - In Docker Compose: Internal custom bridge networks with external routing disabled (`internal: true`).
  - In Virtual Machines: "Host-Only" or "Internal Network" virtual adapters.
- **Prohibition**: No bridged networking to the host computer's physical LAN interface.

### 5.3 Tier 3: Sandboxed Execution
- **Scope**: Static analysis of untrusted files, simulated payloads, or script decoders.
- **Rule**: Executed in ephemeral containers or virtual machines with no persistent volume mounts to sensitive host directories.

### 5.4 Operational Rules of Engagement
- **No LAN Scanning**: Scanning or interacting with the host's actual local subnet (e.g., home or office router) is prohibited.
- **No External Targeting**: Directing scanning tools (`nmap`, `scapy`, `curl`) against third-party public IPs or domains is explicitly forbidden.
- **Automated Cleanup**: Every lab specification must include a clean teardown procedure (`npm run stop`, `docker compose down -v`, or cleanup scripts).

---

## 6. Protection of Instructor Solutions

A critical flaw in educational materials is storing answer keys in public locations disguised by obscure filenames or hidden sections.

### 6.1 Security Boundary Policy
- **No Client-Side Secrecy**: Storing solutions in hidden Markdown comments (`<!-- solution -->`), separate folders in a public repository (`/solutions/`), or encrypted files with shared passwords does **not** constitute an access control boundary.
- **Two-Repository Architectural Model**:
  1. **Public Repository (`cybersecurity-teaching-handbook`)**: Contains student lesson content, guided exercises, open-ended discussion questions, lab setup instructions, and problem statements without answer keys.
  2. **Private / Restricted Location (`cybersecurity-instructor-keys`)**: A separate access-controlled repository or institutional LMS containing full solution walkthroughs, CTF flags, sample grading rubrics, and detection signatures.

---

## 7. Quality Assurance and Compatibility Validation

### 7.1 Real Functional Testing Protocol
Tests must validate actual tool execution, input processing, and output correctness—not mere file presence.

### 7.2 Local Runtime Verification Results (Windows 11 Local Environment)
- **Node.js**: `v24.15.0` (Active LTS line verified).
- **Python**: `Python 3.14.4` (Bleeding-edge build verified).
- **PowerShell Execution Policy**: Standard unrestricted/remote-signed policy requires explicit `-ExecutionPolicy Bypass` for script execution.

### 7.3 Specific Asset Functional Verification
- **`email-analyzer` (`analyzer.py`)**:
  - Tested with `student_lab_phish.eml` and `test_phish.eml`.
  - **Result**: PASSED. Successfully parsed MIME parts, identified mismatched `From`/`Reply-To` headers, extracted URL `http://192.168.1.150/portal/auth-verify`, calculated 100/100 risk score, and returned `CRITICAL / HIGH RISK MALICIOUS` verdict without third-party library requirements.
- **`net-scanner` (`scanner.py`)**:
  - Requires `scapy` and Npcap/WinPcap kernel driver on Windows. Standard Python socket permissions cannot craft raw ARP packets on Windows without administrative elevation or driver support.
  - **Documentation Requirement**: Must be marked with a platform constraint note recommending Linux/WSL2 execution or containerized execution.

---

## 8. Stage 2 Deliverables and Next Steps

The following Stage 2 files have been designed and implemented in the repository:
1. `docs/STAGE_2_SPECIFICATION.md` — Master specification and audit note.
2. `docs/cross-repository-linking.md` — Linking standard and local workspace structure.
3. `docs/lab-safety-framework.md` — Lab isolation tiers and network rules.
4. `docs/instructor-solution-policy.md` — Separation of student material and answer keys.
5. `docs/quality-assurance-and-compatibility.md` — Testing requirements and platform notes.
6. `docs/lesson-to-lab-mapping.md` — Matrix mapping lessons to lab specifications.
7. `templates/lesson-template.md` — Standardized lesson template.
8. `templates/module-overview-template.md` — Standardized module overview template.
9. `templates/lab-specification-template.md` — Standardized lab specification template.
10. `templates/assessment-template.md` — Assessment and quiz template.
11. `templates/instructor-guide-template.md` — Pedagogical and delivery notes template.
12. `curriculum/README.md` — Curriculum index for Modules 1 through 10.
13. `README.md` & `CONTRIBUTING.md` — Repository documentation and contribution guide.

> **Review Hold**: In accordance with Directive 7, execution halts at Stage 2 completion. Full lesson content generation and git commits will await user review.
