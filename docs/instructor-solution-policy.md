# Instructor Solution & Assessment Protection Policy

> **Standard Identifier**: `SEC-PED-01`  
> **Status**: Mandatory Content Boundary Policy  
> **Applicability**: All Modules, Assessments, Quizzes, CTF Challenges, and Labs

---

## 1. The Fallacy of Client-Side Obfuscation

In open-source and publicly hosted educational materials, authors frequently attempt to hide solutions using insecure techniques:
- ❌ **HTML / Markdown Comments**: `<!-- Instructor Solution: flag{...} -->` (Visible immediately via GitHub raw view or page inspection).
- ❌ **Obscure File Names**: Naming files `._hidden_solution.md` or `.answers.json` (Easily indexed by git and search engines).
- ❌ **Private Directories in Public Repos**: Git does not support directory-level permissions within a single repository; if the repository is public, every file is accessible.
- ❌ **Reversible Encoding**: Base64 or rot13 encoding within Markdown documents.

None of these methods constitute an access control boundary.

---

## 2. Two-Repository Architectural Model

To preserve the academic integrity of quizzes, lab challenges, and certification assessments while keeping the teaching handbook open and public, this curriculum enforces a strict **Two-Repository Architectural Model**:

```text
[ PUBLIC ENVIRONMENT ]
┌────────────────────────────────────────────────────────┐
│ Repository: cybersecurity-teaching-handbook            │
│ Content:                                               │
│ • Full conceptual theory and explanations              │
│ • Step-by-step guided tutorials                        │
│ • Problem statements and challenge descriptions        │
│ • Self-check reflection questions (no answer keys)     │
│ • Rubrics defining grading criteria                    │
└────────────────────────────────────────────────────────┘

                           ║  (Security Boundary)
                           ▼

[ PRIVATE / RESTRICTED ACCESS ENVIRONMENT ]
┌────────────────────────────────────────────────────────┐
│ Repository: cybersecurity-instructor-solutions (Private)│
│ (Or Institutional LMS / Access-Controlled Portal)      │
│ Content:                                               │
│ • Complete step-by-step answer keys                    │
│ • CTF challenge capture flags and payload solutions    │
│ • Automated grading scripts and test vectors           │
│ • Instructor teaching strategies and timing notes      │
└────────────────────────────────────────────────────────┘
```

---

## 3. Student-Facing Content Guidelines (Public Handbook)

All lessons and assessment files created in `cybersecurity-teaching-handbook` must follow these rules:

1. **Self-Check Questions**:
   - Focus on conceptual comprehension, synthesis, and analysis.
   - Example: *"Explain why an attacker might use an IP address rather than a domain name in a phishing URL. What security controls does this attempt to circumvent?"*
2. **Lab Challenges**:
   - Provide clear goals, target criteria, and output format expectations without revealing the exploit string or solution payload.
3. **Grading Rubrics**:
   - Include qualitative rubrics that describe what constitutes an *Unsatisfactory*, *Competent*, or *Exemplary* submission.

---

## 4. Instructor Solution Handling (Private Repository)

Instructor solutions must be authored in an independent, private repository (`cybersecurity-instructor-solutions`) with restricted collaborator access:

1. **Mapping Standard**: Every solution document in the private repository directly mirrors the canonical ID of the public lesson or lab:
   - Public Lesson: `curriculum/modules/module-07-social-engineering-phishing/lessons/08-email-spoofing.md` (`SEC-MOD07-LES08`)
   - Private Solution: `solutions/module-07/SEC-MOD07-LES08-solution.md`
2. **Access Control**: Maintained via GitHub Organization teams, LMS integration, or verified educator access requests.
