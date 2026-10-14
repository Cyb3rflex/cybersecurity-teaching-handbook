# Module 7: Social Engineering & Phishing

> **Canonical Module ID**: `SEC-MOD07`  
> **Course Level**: Intermediate  
> **Total Estimated Duration**: 8 Hours  
> **Prerequisites**: `SEC-MOD01`, `SEC-MOD03`

---

## 1. Module Overview & Pedagogical Scope
Human psychology remains the most frequently targeted vulnerability in corporate security incidents. This module dissects the psychological principles exploited by social engineers—urgency, authority, scarcity, social proof, and fear.

Students analyze the technical infrastructure behind phishing: email protocols (SMTP), sender spoofing, SPF, DKIM, and DMARC authentication records, lookalike domains (typosquatting), and malicious link shorteners. In the lab component, students utilize static code analysis to triage raw `.eml` files and calculate risk scores based on header anomalies and indicator extraction.

---

## 2. Module Learning Outcomes
Upon completion of this module, students will demonstrate the ability to:
1. Identify psychological manipulation techniques utilized in social engineering campaigns.
2. Differentiate between mass phishing, targeted spear phishing, whaling, smishing, and vishing.
3. Parse raw email headers to verify delivery pathways, sender hops, and `From` vs. `Reply-To` mismatches.
4. Explain how SPF, DKIM, and DMARC records establish sender authenticity.
5. Safely extract threat indicators (URLs, bare IP links, attachments) from suspicious communications.

---

## 3. Lesson Sequence

| Lesson Number | Canonical ID | Lesson Title | Estimated Time | Hands-on Lab |
| :--- | :--- | :--- | :--- | :--- |
| **Lesson 1** | `SEC-MOD07-LES01` | What is Social Engineering? | 45 mins | None |
| **Lesson 2** | `SEC-MOD07-LES02` | Psychological Principles of Deception | 45 mins | None |
| **Lesson 3** | `SEC-MOD07-LES03` | Phishing, Spear Phishing & Whaling | 45 mins | None |
| **Lesson 4** | `SEC-MOD07-LES04` | Mobile Vectors: Smishing & Vishing | 45 mins | None |
| **Lesson 5** | `SEC-MOD07-LES05` | Lookalike Websites & Typosquatting | 45 mins | None |
| **Lesson 6** | `SEC-MOD07-LES06` | Malicious Links & Redirects | 45 mins | None |
| **Lesson 7** | `SEC-MOD07-LES07` | Email Spoofing & Header Architecture | 60 mins | None |
| **Lesson 8** | `SEC-MOD07-LES08` | SPF, DKIM, DMARC & Sender Verification | 60 mins | None |
| **Lesson 9** | `SEC-MOD07-LES09` | Identifying Phishing & Static Triage | 60 mins | `LAB-SOCENG-01` |
| **Lesson 10** | `SEC-MOD07-LES10` | Building a Safe Phishing Awareness Program | 45 mins | None |

---

## 4. Practical Laboratories Overview
- **`LAB-SOCENG-01`**: Automated Email Header & Indicator Triage (Tier 1 Localhost CLI). Adapted from `email-analyzer`. Students execute Python-based static analysis against sample `.eml` files, decoding multipart bodies, identifying spoofed Reply-To addresses, and calculating risk scores.
