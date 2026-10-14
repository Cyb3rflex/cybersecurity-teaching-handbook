# Quality Assurance, Functional Testing & Environment Compatibility

> **Standard Identifier**: `SEC-QA-01`  
> **Status**: Approved Quality Standard  
> **Target Audience**: Quality Engineers, Authors, Lab Developers

---

## 1. Quality Assurance Philosophy: Functional Validation

A passing test suite in this curriculum must validate **actual lab functionality**, not superficial conditions such as file existence or clean linting.

### 1.1 Non-Permitted Testing Shortcuts
- ❌ Testing only that `index.js` or `analyzer.py` exists on disk.
- ❌ Assuming that a script works because it executes `--help` or imports modules without throwing an error.
- ❌ Assuming cross-platform compatibility across Windows, macOS, and Linux without empirical execution.

### 1.2 Mandatory Validation Criteria
For every practical lab or exercise:
1. **Target Startup Test**: The vulnerable target service must initialize on loopback (`127.0.0.1`), listen on the designated port, and respond with expected HTTP status codes or socket handshakes.
2. **Exercise Workflow Test**: The student exercise procedure or script must run against the target and produce the expected security indicator, parsed output, or defensive mitigation.
3. **Clean Teardown Test**: The target service must shut down completely without leaving orphaned processes, locked ports, or residual container networks.

---

## 2. Environment Compatibility & Runtime Matrix

The current local development environment was profiled to establish baseline compatibility.

### 2.1 Host Environment Profile
- **Host Operating System**: Microsoft Windows 11 Pro (Build 26100)
- **Primary Shell**: PowerShell 5.1 / PowerShell 7
- **Node.js**: `v24.15.0`
- **npm**: `10.8.2`
- **Python**: `Python 3.14.4`

### 2.2 Compatibility Observations & Guidance

| Runtime | Local Version | Compatibility Notes & Guidelines |
| :--- | :--- | :--- |
| **Node.js** | `v24.15.0` | **High Compatibility**. Native support for modern ESM modules, Node test runner, and Express 5 (`ddos-defense-lab`). Ensure all server scripts use explicit IPv4 `127.0.0.1` binding. |
| **Python** | `3.14.4` | **Standard Library Verified**. Pure standard library scripts (`email-analyzer`) execute flawlessly with zero dependency overhead. **Caution**: Bleeding-edge Python 3.14 may encounter issues with legacy binary packages (e.g., specific C-extensions or older compiled wheels). Pure Python tools should be prioritized. |
| **Scapy / Raw Sockets** | N/A | **Platform Constraint on Windows**: Raw socket packet crafting (as used in `net-scanner`) requires administrative privileges and Npcap/WinPcap drivers on Windows. When porting or documenting `net-scanner`, specify WSL2 or Linux VM as the recommended execution target. |

---

## 3. Empirical Test Log (Stage 2 Verification)

During Stage 2 verification, existing local assets were executed and verified against real test inputs:

```text
================================================================================
Test Execution: Email Analyzer Tool (email-analyzer)
Runtime: Python 3.14.4 (Windows 11 x64)
Test Target: student_lab_phish.eml (Simulated High-Urgency Phishing Message)
Command: python ..\email-analyzer\analyzer.py ..\email-analyzer\student_lab_phish.eml
================================================================================
Execution Output:
  Triaging: student_lab_phish.eml
  Subject: Urgent: Action Required - Mandatory Employee Account Verification
  From:    Global Payroll & IT Support <helpdesk@corporate-services.example>
  --------------------------------------------------
  DETECTED INDICATORS:
    [-] Mismatched Reply-To address!
    [-] Urgency/Phishing keyword flagged: 'verify your account'
    [-] Urgency/Phishing keyword flagged: 'update password'
    [-] Urgency/Phishing keyword flagged: 'urgent'
    [-] Urgency/Phishing keyword flagged: 'action required'
    [-] Urgency/Phishing keyword flagged: 'suspended'
    [-] Urgency/Phishing keyword flagged: 'login immediately'
    [-] Urgency/Phishing keyword flagged: 'bank transfer'
    [-] Suspicious IP-based URL detected: http://192.168.1.150/portal/auth-verify
  --------------------------------------------------
  FINAL RISK SCORE: 100/100
  VERDICT: CRITICAL / HIGH RISK MALICIOUS
================================================================================
Verification Status: PASSED (Zero warnings, clean exit code 0)
```
