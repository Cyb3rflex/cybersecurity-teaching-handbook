# Module 6: Network Security

> **Canonical Module ID**: `SEC-MOD06`  
> **Course Level**: Intermediate  
> **Total Estimated Duration**: 10 Hours  
> **Prerequisites**: `SEC-MOD03` (Networking Fundamentals)

---

## 1. Module Overview & Pedagogical Scope
Network security bridges the gap between raw transport protocols and real-world defense architectures. Students explore attack vectors operating at Layers 2, 3, and 4—including ARP cache poisoning, DNS hijacking, Man-in-the-Middle (MitM) positioning, and Distributed Denial of Service (DDoS) traffic floods.

On the defensive side, the module teaches network segmentation, VLAN isolation, encrypted VPN tunneling, and the strategic positioning of Intrusion Detection Systems (IDS) versus Intrusion Prevention Systems (IPS).

---

## 2. Module Learning Outcomes
Upon completion of this module, students will demonstrate the ability to:
1. Explain how broadcast protocol vulnerabilities (ARP) enable local Man-in-the-Middle attacks.
2. Capture and filter network packets safely in an isolated virtual environment using Wireshark.
3. Contrast volumetric, protocol, and application-layer Denial of Service attacks.
4. Implement application-layer rate limiting to withstand request floods.
5. Differentiate signature-based vs. anomaly-based detection in IDS/IPS architectures.

---

## 3. Lesson Sequence

| Lesson Number | Canonical ID | Lesson Title | Estimated Time | Hands-on Lab |
| :--- | :--- | :--- | :--- | :--- |
| **Lesson 1** | `SEC-MOD06-LES01` | Network Attack Vectors | 45 mins | `LAB-NET-03` |
| **Lesson 2** | `SEC-MOD06-LES02` | Packet Sniffing & Promiscuous Mode | 45 mins | None |
| **Lesson 3** | `SEC-MOD06-LES03` | Protocol Analysis with Wireshark | 60 mins | `LAB-NET-04` |
| **Lesson 4** | `SEC-MOD06-LES04` | Address Resolution Protocol (ARP) | 45 mins | None |
| **Lesson 5** | `SEC-MOD06-LES05` | ARP Spoofing & MitM | 60 mins | None |
| **Lesson 6** | `SEC-MOD06-LES06` | DNS Attacks & Cache Poisoning | 45 mins | None |
| **Lesson 7** | `SEC-MOD06-LES07` | DoS & DDoS Attack Mechanics | 60 mins | None |
| **Lesson 8** | `SEC-MOD06-LES08` | Network Segmentation & VLANs | 45 mins | None |
| **Lesson 9** | `SEC-MOD06-LES09` | VPNs & Secure Tunneling | 45 mins | None |
| **Lesson 10** | `SEC-MOD06-LES10` | IDS vs. IPS Architecture | 60 mins | None |

---

## 4. Practical Laboratories Overview
- **`LAB-NET-03`**: HTTP Flood Defense & Dynamic Rate Limiting (Tier 1 Localhost `127.0.0.1`). Adapted from `ddos-defense-lab`.
- **`LAB-NET-04`**: Isolated Network Packet Capture & Protocol Decoding (Tier 2 Host-Only Network).
