# Contributing to the Cybersecurity Teaching Handbook

Thank you for your interest in contributing to the **Cybersecurity Teaching Handbook**! This handbook is an open educational resource built to provide clear, rigorous, and safe instruction in cybersecurity.

---

## 1. Documentation-Only Policy

All contributions to this repository must be written in standard, portable GitHub Flavored Markdown (`.md`).
- **No Web Applications or Frameworks**: Do not submit pull requests adding frontend code, static site generators, databases, dashboards, or web deployment scripts.
- **Portability**: All content should render cleanly on GitHub and in standard markdown viewers.

---

## 2. Using the Standard Templates

Before authoring a new lesson, module, assessment, or instructor guide, you MUST base your work on the canonical templates found in `/templates`:
- New Lesson: [`templates/lesson-template.md`](templates/lesson-template.md)
- Module Overview: [`templates/module-overview-template.md`](templates/module-overview-template.md)
- Lab Specification: [`templates/lab-specification-template.md`](templates/lab-specification-template.md)
- Assessment / Quiz: [`templates/assessment-template.md`](templates/assessment-template.md)
- Instructor Guide: [`templates/instructor-guide-template.md`](templates/instructor-guide-template.md)

---

## 3. Canonical Identifiers & Cross-Repository Linking

Do not use fragile relative paths pointing outside this repository (`../cybersecurity-labs/...`) or premature remote URLs. Reference all lessons and companion labs using their canonical identifiers:
- Lesson ID format: `SEC-MOD<MM>-LES<LL>`
- Lab ID format: `LAB-<DOMAIN>-<NUM>`

Review [`docs/cross-repository-linking.md`](docs/cross-repository-linking.md) for detailed linking specifications.

---

## 4. Lab Safety & Ethical Guidelines

All technical exercises described or referenced must comply with [`docs/lab-safety-framework.md`](docs/lab-safety-framework.md):
- Target services must default to loopback `127.0.0.1`.
- Never suggest scanning or probing physical host LAN subnets, external IP addresses, or third-party web domains.
- Emphasize ethical rules of engagement, authorized boundaries, and defensive remediation in all topics.

---

## 5. Protection of Instructor Solutions

In accordance with [`docs/instructor-solution-policy.md`](docs/instructor-solution-policy.md), student materials and public lessons must NOT include answer keys, CTF solution strings, or exploit payloads. Confidential answer keys are strictly maintained in the private instructor repository.
