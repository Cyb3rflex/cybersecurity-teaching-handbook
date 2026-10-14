# Module 3: Networking Fundamentals

> **Canonical Module ID**: `SEC-MOD03`  
> **Course Level**: Beginner  
> **Total Estimated Duration**: 10 Hours  
> **Prerequisites**: `SEC-MOD01` & `SEC-MOD02`

---

## 1. Module Overview & Pedagogical Scope
Security is impossible without understanding the protocols that interconnect digital systems. This module breaks down how packets travel from source to destination across local networks and the global internet.

Students examine the OSI 7-Layer model alongside the pragmatic TCP/IP 4-Layer stack. Key topics include IPv4/IPv6 subnetting, MAC addressing, TCP three-way handshakes, UDP characteristics, DNS queries, DHCP lease allocation, and the critical security transition from unencrypted HTTP to TLS-secured HTTPS.

---

## 2. Module Learning Outcomes
Upon completion of this module, students will demonstrate the ability to:
1. Map networking protocols to their corresponding OSI and TCP/IP layers.
2. Differentiate between IP routing, MAC layer switching, and port-based service multiplexing.
3. Trace the end-to-end lifecycle of an HTTP/S request, including DNS lookup, TCP handshake, TLS negotiation, and data transfer.
4. Analyze network socket states on a local host (`LISTENING`, `ESTABLISHED`, `TIME_WAIT`).

---

## 3. Lesson Sequence

| Lesson Number | Canonical ID | Lesson Title | Estimated Time | Hands-on Lab |
| :--- | :--- | :--- | :--- | :--- |
| **Lesson 1** | `SEC-MOD03-LES01` | What is a Computer Network? | 45 mins | None |
| **Lesson 2** | `SEC-MOD03-LES02` | IPv4 and IPv6 Addressing | 60 mins | None |
| **Lesson 3** | `SEC-MOD03-LES03` | MAC Addresses & Ethernet | 45 mins | None |
| **Lesson 4** | `SEC-MOD03-LES04` | Ports, Sockets & Core Protocols | 60 mins | `LAB-NET-01` |
| **Lesson 5** | `SEC-MOD03-LES05` | TCP vs. UDP Mechanics | 45 mins | None |
| **Lesson 6** | `SEC-MOD03-LES06` | DNS Hierarchy & Resolution | 60 mins | None |
| **Lesson 7** | `SEC-MOD03-LES07` | DHCP Allocation Lifecycle | 45 mins | None |
| **Lesson 8** | `SEC-MOD03-LES08` | HTTP and HTTPS Protocol Anatomy | 60 mins | `LAB-NET-02` |
| **Lesson 9** | `SEC-MOD03-LES09` | The OSI 7-Layer Model | 60 mins | None |
| **Lesson 10** | `SEC-MOD03-LES10` | The TCP/IP 4-Layer Architecture | 45 mins | None |
| **Lesson 11** | `SEC-MOD03-LES11` | NAT & Stateful Firewalls | 45 mins | None |
| **Lesson 12** | `SEC-MOD03-LES12` | The Packet Journey Across the Net | 60 mins | None |

---

## 4. Practical Laboratories Overview
- **`LAB-NET-01`**: Local Socket Inspection & Port Discovery (Tier 1 Localhost).
- **`LAB-NET-02`**: Inspecting Plaintext HTTP vs. TLS Encrypted Payloads (Tier 1 Localhost).
