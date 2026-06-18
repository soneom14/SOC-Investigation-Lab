# SOC Investigation Lab

## Project Overview

This project demonstrates a Security Operations Center (SOC) investigation workflow using Kali Linux, Metasploitable 2, Nmap, Wireshark, and VirtualBox.

The objective is to simulate a real-world SOC analyst environment by performing network discovery, traffic analysis, evidence collection, and vulnerability assessment.

---

## Lab Architecture

![SOC Architecture](screenshots/SOC%20architecture%20diagram.jpeg)

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

## Phase 1 – Network Discovery and Traffic Analysis

### Connectivity Verification

```bash
ping 192.168.56.103
```

### Service Enumeration

```bash
nmap -sV 192.168.56.103
```

### Open Services Identified

| Port | Service |
|------|---------|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 5900 | VNC |
| 8180 | Apache Tomcat |

---

## Evidence Collection

### Screenshots

Stored in:

```text
screenshots/
```

### Packet Captures

Stored in:

```text
pcaps/
```

### Reports

Stored in:

```text
reports/
```

---

## Repository Structure

```text
SOC-Investigation-Lab/
│
├── docs/
├── pcaps/
├── reports/
├── screenshots/
│   └── SOC architecture diagram.jpeg
└── README.md
```

---

## Key Findings

- Successful communication established between Kali Linux and Metasploitable 2.
- ICMP traffic captured and analyzed using Wireshark.
- Multiple services detected using Nmap version detection.
- Vulnerable services identified for future assessment.
- Evidence collected and stored for SOC investigation reporting.

---

## Conclusion

The lab successfully demonstrated network discovery, service enumeration, and packet capture within a controlled VirtualBox environment. The collected evidence forms the foundation for future vulnerability assessment and SOC analysis activities.

---

## Author

**Om Sone**

Cybersecurity Enthusiast | CEH-Aligned Projects | Network Security | Vulnerability Assessment
