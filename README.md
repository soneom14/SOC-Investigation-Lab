# SOC Investigation Lab

## Project Overview

This project demonstrates a Security Operations Center (SOC) investigation workflow using Kali Linux, Metasploitable2, Nmap, Wireshark, and VirtualBox.

The objective is to simulate a real-world SOC analyst environment by performing network discovery, traffic analysis, evidence collection, and vulnerability assessment in a controlled lab environment.

---

## Lab Architecture

### Environment Overview

| Component | IP Address | Purpose |
|------------|------------|------------|
| Kali Linux | 192.168.56.104 | Analyst Machine |
| Metasploitable2 | 192.168.56.103 | Vulnerable Target |
| VirtualBox Host-Only Network | 192.168.56.0/24 | Isolated Lab Network |

### Architecture Diagram

![SOC Architecture Diagram](screenshots/SOC%20architecture%20diagram.jpeg)

---

## Tools Used

- Kali Linux
- VirtualBox
- Metasploitable2
- Nmap
- Wireshark

---

## Network Verification

The first phase of the investigation was to verify connectivity between the analyst machine and the target system.

### Ping Test

Command:

```bash
ping 192.168.56.103
```

Result:

- Successful ICMP communication
- 0% packet loss
- Connectivity confirmed

Screenshot:

![Ping Test](screenshots/ping_test.jpeg)

---

## Reconnaissance

Service discovery was performed using Nmap.

### Nmap Scan

Command:

```bash
nmap -sV 192.168.56.103
```

Key Services Identified:

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

Screenshot:

![Nmap Scan](screenshots/nmap_scan.png)

---

## Traffic Analysis

Network traffic was captured using Wireshark during reconnaissance and connectivity testing.

Observed Traffic:

- ICMP Echo Requests and Replies
- TCP Connection Attempts
- SMB Broadcast Traffic
- NetBIOS Name Service Traffic

Screenshot:

![Wireshark Capture](screenshots/wireshark_capture.jpeg)

---

## Evidence Collection

Packet captures were collected and preserved for analysis.

Location:

```text
pcaps/network_capture.pcapng
```

---

## Findings

- Network connectivity successfully established.
- Multiple services exposed by the target system.
- Clear-text protocols such as Telnet detected.
- SMB and NetBIOS services accessible.
- Several outdated services identified.
- Network traffic successfully captured and preserved.

---

## Risk Assessment

The target environment contains intentionally vulnerable services designed for security testing.

Potential Risks:

- Unauthorized access through exposed services.
- Information disclosure.
- Weak authentication mechanisms.
- Exploitable legacy software.

---

## Conclusion

This investigation successfully demonstrated the SOC workflow of:

- Network Verification
- Service Enumeration
- Traffic Capture
- Evidence Collection
- Documentation and Reporting

The project provides hands-on experience with common SOC analyst activities using open-source cybersecurity tools.

---

## Repository Structure

```text
SOC-Investigation-Lab/
│
├── docs/
│   └── Phase1-Network-Verification.md
│
├── pcaps/
│   └── network_capture.pcapng
│
├── reports/
│   └── final_findings.md
│
├── screenshots/
│   ├── SOC architecture diagram.jpeg
│   ├── nmap_scan.png
│   ├── ping_test.jpeg
│   └── wireshark_capture.jpeg
│
└── README.md
```

---

## Author

**Om Sone**

SOC Investigation Lab Project using Kali Linux, Nmap, Wireshark, and Metasploitable2.
