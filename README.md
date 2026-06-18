# SOC Investigation Lab

## Project Overview

This project demonstrates a Security Operations Center (SOC) investigation workflow using Kali Linux, Metasploitable2, Nmap, Wireshark, and VirtualBox.

The objective was to simulate a real-world SOC analyst environment by performing network verification, service discovery, traffic analysis, evidence collection, and security assessment within a controlled laboratory environment.

---

## Lab Architecture

### Environment Overview

| Component                    | IP Address      | Purpose              |
| ---------------------------- | --------------- | -------------------- |
| Kali Linux                   | 192.168.56.104  | Analyst Machine      |
| Metasploitable2              | 192.168.56.103  | Vulnerable Target    |
| VirtualBox Host-Only Network | 192.168.56.0/24 | Isolated Lab Network |

### Architecture Diagram

![SOC Architecture Diagram](./screenshots/SOC%20architecture%20diagram.jpeg)

---

## Skills Demonstrated

* Network Verification
* Network Reconnaissance
* Nmap Enumeration
* Packet Capture Analysis
* Wireshark Traffic Analysis
* Evidence Collection
* Security Assessment
* Incident Documentation
* Linux Administration
* Vulnerability Identification

---

## Tools Used

* Kali Linux
* VirtualBox
* Metasploitable2
* Nmap
* Wireshark

---

# Investigation Workflow

## Phase 1 – Network Verification

### Objective

Verify connectivity between the analyst machine and the target machine.

### Command

```bash
ping 192.168.56.103
```

### Results

* Successful ICMP communication
* 0% packet loss
* Connectivity confirmed

### Screenshot

![Ping Test](./screenshots/ping_test.jpeg)

---

## Phase 2 – Reconnaissance

### Objective

Identify active services running on the target system.

### Command

```bash
sudo nmap -sV 192.168.56.103
```

### Services Identified

| Port | Service    |
| ---- | ---------- |
| 21   | FTP        |
| 22   | SSH        |
| 23   | Telnet     |
| 25   | SMTP       |
| 53   | DNS        |
| 80   | HTTP       |
| 139  | NetBIOS    |
| 445  | SMB        |
| 3306 | MySQL      |
| 5432 | PostgreSQL |
| 5900 | VNC        |
| 6667 | IRC        |

### Screenshot

![Nmap Scan](./screenshots/nmap_scan.png)

---

## Phase 3 – Traffic Analysis

### Objective

Capture and analyze network traffic generated during reconnaissance activities.

### Tool

Wireshark

### Observed Traffic

* ICMP Echo Requests and Replies
* TCP Connection Attempts
* Service Discovery Traffic
* SMB Communication
* NetBIOS Traffic

### Screenshot

![Wireshark Capture](./screenshots/wireshark_capture.jpeg)

---

## Phase 4 – Evidence Collection

### Objective

Preserve collected evidence for analysis and reporting.

### Evidence Collected

* Packet Capture File
* Nmap Scan Results
* Investigation Screenshots
* Findings Report

### Packet Capture

```text
pcaps/network_capture.pcapng
```

---

# Investigation Findings

## Summary

The investigation successfully demonstrated a complete SOC workflow including:

* Network Verification
* Service Enumeration
* Traffic Capture
* Evidence Collection
* Security Assessment
* Incident Documentation

### Key Security Findings

* Multiple services exposed on the target machine.
* SMB and NetBIOS services increase attack surface.
* Telnet service transmits data without encryption.
* Successful traffic capture validated network activity.
* Evidence preserved through screenshots and packet captures.

---

## Documentation

| Document                       | Description                         |
| ------------------------------ | ----------------------------------- |
| Findings.md                    | Investigation findings and analysis |
| Phase1-Network-Verification.md | Connectivity testing                |
| Phase2-Reconnaissance.md       | Nmap service discovery              |
| Phase3-Traffic-Analysis.md     | Wireshark analysis                  |
| Phase4-Evidence-Collection.md  | Evidence preservation               |

---

## Repository Structure

```text
SOC-Investigation-Lab/
│
├── docs/
│   ├── Findings.md
│   ├── Phase1-Network-Verification.md
│   ├── Phase2-Reconnaissance.md
│   ├── Phase3-Traffic-Analysis.md
│   └── Phase4-Evidence-Collection.md
│
├── pcaps/
│   └── network_capture.pcapng
│
├── reports/
│   └── final_findings.md
│
├── screenshots/
│   ├── SOC architecture diagram.jpeg
│   ├── ping_test.jpeg
│   ├── nmap_scan.png
│   └── wireshark_capture.jpeg
│
└── README.md
```

---

## Future Improvements

* Nessus Vulnerability Scanning
* OpenVAS Integration
* Snort IDS Monitoring
* Suricata Alert Analysis
* SIEM Integration
* Incident Response Playbooks

---

## Author

**Om Sone**

Computer Science Engineering Student | Cybersecurity Enthusiast | SOC Analyst Aspirant | Network Security Researcher

---

## Disclaimer

This project was conducted in an isolated laboratory environment using intentionally vulnerable systems for educational and research purposes only.
