# SOC Investigation Lab

## Project Overview

This project demonstrates a Security Operations Center (SOC) investigation workflow using Kali Linux, Metasploitable 2, Nmap, Wireshark, and VirtualBox.

The objective is to simulate a real-world SOC analyst environment by performing network discovery, traffic analysis, evidence collection, and vulnerability assessment.

---

## Lab Architecture

![SOC Architecture](screenshots/soc_architecture_diagram.png)

---

## Environment Setup

| Component | IP Address | Purpose |
|------------|------------|----------|
| Kali Linux | 192.168.56.104 | Attacker / Analyst Machine |
| Metasploitable 2 | 192.168.56.103 | Vulnerable Target |
| VirtualBox Host-Only Network | 192.168.56.0/24 | Isolated Lab Network |

---

## Tools Used

- Kali Linux
- Metasploitable 2
- Nmap
- Wireshark
- VirtualBox

---

## Phase 1 – Network Discovery

### Connectivity Verification

```bash
ping 192.168.56.103
```

### Service Enumeration

```bash
nmap -sV 192.168.56.103
```

### Findings

| Port | Service |
|--------|---------|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 80 | HTTP |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 5900 | VNC |

---

## Evidence Collection

### Screenshots

Stored in:

screenshots/

### Packet Captures

Stored in:

pcaps/

### Reports

Stored in:

reports/

---

## Repository Structure

```
SOC-Investigation-Lab/
│
├── docs/
├── pcaps/
├── reports/
├── screenshots/
└── README.md
```

---

## Conclusion

The lab successfully demonstrated network discovery and packet analysis within a controlled environment. Multiple exposed services were identified on the target machine, providing a foundation for further vulnerability assessment and SOC investigation activities.

---

## Author

Om Sone

Cybersecurity Enthusiast | CEH-Aligned Projects | Network Security
