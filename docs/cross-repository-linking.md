# Cross-Repository Linking & Workspace Conventions

> **Standard Identifier**: `ARCH-LINK-01`  
> **Status**: Approved Architectural Standard  
> **Target Audience**: Curriculum Authors, Educators, Lab Developers

---

## 1. Context and Problem Statement

The cybersecurity educational system is divided into two distinct repositories:
1. `cybersecurity-teaching-handbook`: The documentation-only, conceptual, pedagogical teaching handbook written in Markdown.
2. `cybersecurity-labs`: The executable, containerized, practical lab environments and scripts.

When learning or teaching locally, relative paths (`../cybersecurity-labs/...`) point to adjacent folders on disk. However, once pushed to remote platforms (such as GitHub), relative links pointing outside the repository tree fail with HTTP 404 errors. Furthermore, inventing hardcoded remote URLs (`https://github.com/Cyb3rflex/...`) before the repositories are created and stabilized creates brittle, broken references.

---

## 2. Recommended Local Directory Arrangement

Both repositories must be cloned side-by-side within a parent workspace folder.

```text
<workspace-root>/
├── cybersecurity-teaching-handbook/   # Documentation, lesson plans, guides
└── cybersecurity-labs/                # Executable code, Docker setups, scripts
```

### Local Setup Instructions for Students and Educators
```bash
# Clone both repositories into the same parent directory
mkdir cybersecurity-workspace && cd cybersecurity-workspace
git clone <handbook-repo-url> cybersecurity-teaching-handbook
git clone <labs-repo-url> cybersecurity-labs
```

---

## 3. Canonical Identifiers (The Stable Linking Contract)

Instead of relying on unstable filesystem paths or premature remote URLs, all lessons and lab exercises share a strict canonical identification schema.

### 3.1 Lesson Identifiers
Format: `SEC-MOD<MM>-LES<LL>`
- `MM`: Two-digit module number (`01` through `10`)
- `LL`: Two-digit lesson number (`01` through `12`)

*Examples:*
- `SEC-MOD01-LES04`: Module 1, Lesson 4 (The CIA Triad)
- `SEC-MOD05-LES06`: Module 5, Lesson 6 (Subdomain Enumeration)
- `SEC-MOD07-LES08`: Module 7, Lesson 8 (Email Spoofing & Phishing Triage)

### 3.2 Practical Lab Identifiers
Format: `LAB-<DOMAIN>-<NUM>`
- `DOMAIN`: Short alphanumeric category code (`FOUND`, `NET`, `WEB`, `RECON`, `SOCENG`, `MALW`, `DEF`)
- `NUM`: Two-digit sequence number

*Examples:*
- `LAB-RECON-01`: Passive Web Reconnaissance Lab
- `LAB-SOCENG-01`: Email Header Analysis & Phishing Triage Lab
- `LAB-NET-01`: Port Scanning & Protocol Analysis Lab
- `LAB-WEB-01`: SQL Injection & Defense Lab

---

## 4. Documentation Standard for Lab References in Lessons

Every lesson Markdown document that links to a practical lab must include the standardized **Practical Lab Callout** in its frontmatter and body.

### Callout Schema:
```markdown
---
### 🛠️ Hands-on Lab Assignment
- **Lab Identifier**: `LAB-SOCENG-01`
- **Lab Title**: Automated Email Header and Indicator Triage
- **Lab Location in `cybersecurity-labs`**: `labs/social-engineering/lab-01-email-analyzer/`
- **Estimated Duration**: 45 minutes
- **Isolation Level**: Tier 1 (Localhost / Python CLI)
- **Local Navigation**:
  If following the standard workspace layout, navigate to:
  `cd ../cybersecurity-labs/labs/social-engineering/lab-01-email-analyzer/`
---
```

This guarantees:
1. The student or educator understands the exact Canonical ID.
2. The relative path inside `cybersecurity-labs` is explicit and unmistakable.
3. If viewed locally in VS Code or Antigravity IDE, the learner can locate the lab immediately.
4. If viewed on GitHub or as a standalone rendered document, no relative external link breaks.
