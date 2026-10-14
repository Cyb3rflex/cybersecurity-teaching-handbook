# Module 2: Linux & Command Line

> **Canonical Module ID**: `SEC-MOD02`  
> **Course Level**: Beginner  
> **Total Estimated Duration**: 8 Hours  
> **Prerequisites**: `SEC-MOD01` (Cybersecurity Foundations)

---

## 1. Module Overview & Pedagogical Scope
Linux is the foundational operating system of the modern security landscape, powering cloud infrastructure, security appliances, containerized platforms, and specialized penetration testing distributions like Kali Linux. This module equips students with practical fluency in the Linux terminal.

Students master filesystem navigation, standard permission models (`chmod`, `chown`, octal notation), process auditing, package management, and basic Bash scripting. Crucially, Lesson 2.9 introduces the architecture of safe, isolated practice laboratories.

---

## 2. Module Learning Outcomes
Upon completion of this module, students will demonstrate the ability to:
1. Navigate the Linux Filesystem Hierarchy Standard (FHS) from the command line.
2. Calculate and configure POSIX user, group, and other file permissions and identify dangerous SUID binaries.
3. Inspect and control active operating system processes, Daemons, and services (`ps`, `top`, `systemctl`).
4. Write structured Bash scripts to automate administrative tasks and log parsing.
5. Provision safe, non-bridged local virtual lab environments.

---

## 3. Lesson Sequence

| Lesson Number | Canonical ID | Lesson Title | Estimated Time | Hands-on Lab |
| :--- | :--- | :--- | :--- | :--- |
| **Lesson 1** | `SEC-MOD02-LES01` | Introduction to Linux Architecture | 45 mins | None |
| **Lesson 2** | `SEC-MOD02-LES02` | Linux Filesystem Hierarchy | 45 mins | None |
| **Lesson 3** | `SEC-MOD02-LES03` | Users, Groups & Permissions | 60 mins | `LAB-LINUX-01` |
| **Lesson 4** | `SEC-MOD02-LES04` | Essential Navigation & File Commands | 60 mins | None |
| **Lesson 5** | `SEC-MOD02-LES05` | Process Management & Services | 60 mins | None |
| **Lesson 6** | `SEC-MOD02-LES06` | Package Management | 45 mins | None |
| **Lesson 7** | `SEC-MOD02-LES07` | Bash Scripting Essentials | 60 mins | None |
| **Lesson 8** | `SEC-MOD02-LES08` | Kali Linux & Security Distros | 45 mins | None |
| **Lesson 9** | `SEC-MOD02-LES09` | Designing Safe Cybersecurity Labs | 60 mins | `LAB-LINUX-02` |

---

## 4. Practical Laboratories Overview
- **`LAB-LINUX-01`**: Linux Permission Auditing & Privilege Separation (Tier 1 Localhost CLI).
- **`LAB-LINUX-02`**: Provisioning an Isolated Multi-Node Virtual Switch/Network (Tier 2 Isolated Network).
