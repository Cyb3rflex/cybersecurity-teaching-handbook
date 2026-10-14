# Lab Specification: [Lab Name]

> **Canonical Lab ID**: `LAB-<DOMAIN>-<NUM>`  
> **Associated Lesson**: `SEC-MOD<MM>-LES<LL>`: [Lesson Title]  
> **Isolation Tier**: Tier 1 (Localhost `127.0.0.1`) / Tier 2 (Host-Only Virtual Network) / Tier 3 (Sandbox)  
> **Target Platform**: Windows 11 / Linux / macOS / WSL2  
> **Estimated Completion Time**: [X] minutes

---

## 1. Lab Objectives & Scenario
### Scenario Context
[Describe the realistic operational scenario—e.g., investigating a phishing email report, auditing a misconfigured web server, or defending against an HTTP flood.]

### Technical Learning Objectives
- [Objective 1: Technical skill demonstrated]
- [Objective 2: Tool utilized]
- [Objective 3: Defensive takeaway]

---

## 2. Environment Architecture & Safety Boundary

### Network Topography
```text
[Student Host]
      │
 (127.0.0.1:<PORT> / Loopback only)
      ▼
[Target Service / Application Container]
```

### Safety Constraints Checklist
- [ ] Service binds exclusively to `127.0.0.1` or isolated internal Docker bridge.
- [ ] No outbound network requests to third-party hosts.
- [ ] No scanning of host LAN subnets.
- [ ] Ephemeral execution; all state destroyed on teardown.

---

## 3. Prerequisites & Dependencies
- **Runtime Required**: [e.g., Python 3.10+ / Node.js 20+]
- **Package Dependencies**: [List packages or standard library only]
- **Estimated Disk / Memory Footprint**: [< 50MB / < 256MB RAM]

---

## 4. Step-by-Step Execution Guide

### Phase 1: Setup & Target Verification
```bash
# Clone or navigate to lab directory
cd labs/<domain>/<lab-directory>/

# Install dependencies (if applicable)
npm install

# Start target service
npm start
```
*Verify that the service is running on `http://127.0.0.1:<PORT>`.*

### Phase 2: Student Investigation / Attack Simulation
```bash
# Run investigation tool
python analyzer.py test_sample.eml
```

### Phase 3: Defensive Remediation / Hardening
[Instructions on configuring rate limits, updating validation rules, or applying input filters.]

---

## 5. Automated Verification & Quality Assurance
To verify your lab execution was successful, run the functional test script:

```bash
# Automated verification test
npm test
# or
python test_lab.py
```

Expected Output:
```text
[PASS] Target initialization on 127.0.0.1:<PORT>
[PASS] Security indicator detection verified
[PASS] Clean teardown completed
```

---

## 6. Teardown & Cleanup
Always clean up lab resources after completion:

```bash
# Stop services and remove temporary files
npm run cleanup
# or
docker compose down -v
```
