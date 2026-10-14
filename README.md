# Cybersecurity Teaching Handbook

> A comprehensive, structured, and modular cybersecurity curriculum designed for educators, self-directed learners, and training cohorts. Written entirely in portable, standard Markdown.

---

## 📖 About This Handbook

The **Cybersecurity Teaching Handbook** is a documentation-only open educational resource. It covers the entire journey from computing and networking foundations to advanced penetration testing, malware analysis, incident response, and modern cloud/DevSecOps security.

### Core Pedagogical Principles
- **Portable Markdown (`.md`) Only**: No complex web frameworks, static site generators, databases, or client-side JavaScript applications. The handbook is immediately readable on GitHub, inside terminal pagers, in VS Code / Antigravity IDE, or converted to print/PDF.
- **Independent & Decoupled**: Theoretical lessons in this repository link to practical, hands-on lab environments in the companion `cybersecurity-labs` repository via **Canonical Identifiers** and documented workspace conventions.
- **Safety & Isolation by Design**: All associated practical labs default to localhost (`127.0.0.1`) loopback binding or isolated host-only virtual networks, preventing accidental network scanning or external exposure.
- **Academic Integrity**: Student materials are kept free of spoilers, while instructor answer keys and assessment solutions are maintained in an access-controlled, separate private location.

---

## 🗂️ Repository Directory Structure

```text
cybersecurity-teaching-handbook/
├── README.md                                # Master repository overview (this document)
├── CONTRIBUTING.md                          # Contribution guidelines & editorial standards
├── LICENSE                                  # Open documentation license (CC-BY-4.0)
│
├── docs/                                    # Architectural policies & standards
│   ├── STAGE_2_SPECIFICATION.md            # Stage 2 architecture specification & project audit
│   ├── cross-repository-linking.md         # Linking conventions & workspace layout
│   ├── lab-safety-framework.md             # Lab isolation tiers, network rules & cleanup
│   ├── instructor-solution-policy.md       # Student materials vs. private answer key boundary
│   ├── quality-assurance-and-compatibility.md # Empirical QA testing & runtime matrix
│   └── lesson-to-lab-mapping.md            # Lesson-to-lab matrix mapping
│
├── templates/                               # Standardized templates for content creation
│   ├── lesson-template.md                  # Template for student lessons
│   ├── module-overview-template.md         # Template for module overviews
│   ├── lab-specification-template.md       # Template for companion practical lab specs
│   ├── assessment-template.md              # Template for module assessments
│   └── instructor-guide-template.md        # Template for educator teaching notes
│
└── curriculum/                              # Core educational curriculum
    ├── README.md                            # Master Curriculum Index & Tracks
    └── modules/                             # Modules 01 through 10
        ├── module-01-foundations/           # Cybersecurity Foundations
        ├── module-02-linux-cli/             # Linux & Command Line
        ├── module-03-networking-fundamentals/# Networking Fundamentals
        ├── module-04-web-application-security/# Web & Application Security
        ├── module-05-reconnaissance-osint/  # Reconnaissance & OSINT
        ├── module-06-network-security/      # Network Security
        ├── module-07-social-engineering-phishing/# Social Engineering & Phishing
        ├── module-08-ethical-hacking-pentesting/# Ethical Hacking & Penetration Testing
        ├── module-09-malware-defensive-security/# Malware & Defensive Security
        └── module-10-modern-cybersecurity/  # Modern Cybersecurity (Cloud/AI/Zero Trust)
```

---

## 🗺️ Curriculum Module Index

| Module | Canonical ID | Title | Level | Hours |
| :---: | :--- | :--- | :---: | :---: |
| **01** | [`SEC-MOD01`](curriculum/modules/module-01-foundations/overview.md) | Cybersecurity Foundations | Beginner | 6 |
| **02** | [`SEC-MOD02`](curriculum/modules/module-02-linux-cli/overview.md) | Linux & Command Line | Beginner | 8 |
| **03** | [`SEC-MOD03`](curriculum/modules/module-03-networking-fundamentals/overview.md) | Networking Fundamentals | Beginner | 10 |
| **04** | [`SEC-MOD04`](curriculum/modules/module-04-web-application-security/overview.md) | Web & Application Security | Intermediate | 10 |
| **05** | [`SEC-MOD05`](curriculum/modules/module-05-reconnaissance-osint/overview.md) | Reconnaissance & OSINT | Intermediate | 8 |
| **06** | [`SEC-MOD06`](curriculum/modules/module-06-network-security/overview.md) | Network Security | Intermediate | 10 |
| **07** | [`SEC-MOD07`](curriculum/modules/module-07-social-engineering-phishing/overview.md) | Social Engineering & Phishing | Intermediate | 8 |
| **08** | [`SEC-MOD08`](curriculum/modules/module-08-ethical-hacking-pentesting/overview.md) | Ethical Hacking & Penetration Testing | Advanced | 10 |
| **09** | [`SEC-MOD09`](curriculum/modules/module-09-malware-defensive-security/overview.md) | Malware & Defensive Security | Advanced | 10 |
| **10** | [`SEC-MOD10`](curriculum/modules/module-10-modern-cybersecurity/overview.md) | Modern Cybersecurity (Cloud, Containers, Zero Trust) | Advanced | 10 |

---

## 🛠️ Recommended Local Workspace Setup

To work with both the conceptual lessons and the companion executable lab environments, arrange your local folders side-by-side:

```text
workspace-root/
├── cybersecurity-teaching-handbook/   # (This repository) Markdown lessons & guides
└── cybersecurity-labs/                # (Companion repository) Executable labs & code
```

See [docs/cross-repository-linking.md](docs/cross-repository-linking.md) for full linking specifications.

---

## ⚖️ License & Intellectual Property

Educational content and curriculum documentation in this repository are published under the **Creative Commons Attribution 4.0 International (CC-BY-4.0)** license. See [LICENSE](LICENSE) for terms.