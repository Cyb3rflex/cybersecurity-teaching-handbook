# Practical Lab Safety & Network Isolation Framework

> **Standard Identifier**: `SEC-SAFE-01`  
> **Status**: Mandatory Operational Policy  
> **Applicability**: All Practical Laboratories, Toolchains, and Exercises

---

## 1. Safety Principles & Ethical Rules of Engagement

Educational cybersecurity exercises demonstrate offensive methodologies to build robust defensive capabilities. To ensure safe, legal, and non-destructive execution, all practical laboratories developed for this curriculum must adhere to these rules:

1. **Explicit Permission Boundary**: Students and instructors are strictly authorized to scan, probe, or interact ONLY with systems explicitly provisioned by the lab instructions.
2. **Strict Loopback / Virtual Boundary**: No tool, script, or scanner may be configured to target or discover machines on the host computer's local physical network (LAN) or public internet addresses by default.
3. **No Unbounded Exposure**: Intentionally vulnerable servers or services must never be exposed to the public internet or unauthenticated LAN peers.

---

## 2. Lab Isolation Tiers

Labs are categorized into three isolation tiers depending on their network architecture:

```text
+--------------------------------------------------------------------------+
| TIER 1: Localhost / Loopback Applications (Default)                      |
| • Binds strictly to 127.0.0.1 or ::1                                     |
| • No multi-host routing required                                         |
+--------------------------------------------------------------------------+
                                    |
+--------------------------------------------------------------------------+
| TIER 2: Isolated Host-Only Virtual Networks                              |
| • Multi-node scenarios (Attacker, Target, DNS, Gateway)                  |
| • Docker bridge networks with internal: true, or VM Host-Only Switches   |
| • No physical LAN bridging or external NAT routes                         |
+--------------------------------------------------------------------------+
                                    |
+--------------------------------------------------------------------------+
| TIER 3: Sandboxed Execution Environs                                     |
| • Simulated malicious files, scripts, or decoding exercises              |
| • Ephemeral containers, read-only volume mounts, no host access          |
+--------------------------------------------------------------------------+
```

### 2.1 Tier 1: Localhost Application Labs (Default)
- **Scope**: Single-node web applications (e.g., Express servers, Python Flask/FastAPI), command-line static analyzers (e.g., `email-analyzer`), and local cryptography scripts.
- **Network Rule**: The server MUST bind explicitly to `127.0.0.1` (IPv4) or `::1` (IPv6).
  ```javascript
  // Node.js Express example:
  const HOST = '127.0.0.1';
  const PORT = 3000;
  app.listen(PORT, HOST, () => {
    console.log(`Lab server running securely on http://${HOST}:${PORT}`);
  });
  ```
- **Prohibition**: Binding to `0.0.0.0` or empty host strings is prohibited unless running inside an isolated Docker container with port publishing strictly constrained to localhost (`127.0.0.1:3000:3000`).

### 2.2 Tier 2: Isolated Host-Only Multi-Host Networks
- **Scope**: Network security labs requiring multi-host interactions (e.g., packet sniffing, ARP analysis, IDS alerts, client-server web interactions).
- **Network Rule**: Must run inside an isolated virtual network that does not touch physical LAN traffic.
  - **Docker Compose Standard**:
    ```yaml
    version: '3.8'
    services:
      target-app:
        image: lab-target:latest
        networks:
          lab-isolated-net:
            ipv4_address: 10.10.10.5
      
      attacker-node:
        image: lab-attacker:latest
        networks:
          lab-isolated-net:
            ipv4_address: 10.10.10.10

    networks:
      lab-isolated-net:
        driver: bridge
        internal: true  # Blocks external incoming/outgoing traffic
        ipam:
          config:
            - subnet: 10.10.10.0/24
    ```
  - **VirtualBox / VMware Standard**:
    - Use "Host-Only Adapter" (`vboxnet0` / `vmnet1`) or "Internal Network".
    - Never use "Bridged Adapter" connected to physical Wi-Fi or Ethernet interfaces.

### 2.3 Tier 3: Sandboxed Execution
- **Scope**: Analyzing untrusted payloads, obfuscated scripts, or macro files.
- **Rule**: Run in disposable, non-networked containers with read-only root filesystems and automated memory wipes upon exit.

---

## 3. Explicit Prohibitions

1. **Default LAN Scans Forbidden**: No scanner script (such as `net-scanner` or Nmap wrappers) may initiate sweeps of `192.168.0.0/16` or `10.0.0.0/8` by default. Labs must either target explicit loopback ports or hardcoded virtual subnet targets (e.g., `10.10.10.0/24`).
2. **No Third-Party Targets**: Target domain names must resolve to loopback or simulated local DNS servers (e.g., using `example.test` or `lab.local`), never public registered domains.
3. **No Unmonitored Persistence**: Services must not configure system-level startup daemons or systemd auto-start services on the student's host machine.

---

## 4. Teardown and Cleanup Procedures

Every lab specification must define automated and manual teardown steps to guarantee the student's system returns to a clean baseline:

1. **Process Termination**:
   - For Node.js/Python: `npm run stop` or dedicated `cleanup.py` / `kill-port` script.
2. **Container Pruning**:
   - `docker compose down -v --remove-orphans`
3. **Artifact Cleanup**:
   - Removal of temporary log files, generated pcap captures, or test payloads.
