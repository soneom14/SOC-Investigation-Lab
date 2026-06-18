# SOC Investigation Lab

## Project Overview

This project demonstrates an end-to-end Security Operations Center (SOC) investigation workflow using Kali Linux, Metasploitable2, Nmap, Wireshark, and VirtualBox.

The objective was to simulate a real-world SOC analyst environment by performing network verification, service discovery, traffic analysis, evidence collection, and security assessment within a controlled laboratory environment.

---

## Documentation

- [Phase 1 - Network Verification](docs/Phase1-Network-Verification.md)
- [Phase 2 - Reconnaissance](docs/Phase2-Reconnaissance.md)
- [Phase 3 - Traffic Analysis](docs/Phase3-Traffic-Analysis.md)
- [Phase 4 - Evidence Collection](docs/Phase4-Evidence-Collection.md)
- [Findings Report](docs/Findings.md)
- [Final Investigation Report](reports/final_findings.md)

---

## Project Outcome

Successfully completed an end-to-end SOC investigation workflow including:

- Network Verification
- Service Enumeration
- Traffic Analysis
- Evidence Collection
- Security Assessment
- Incident Documentation

This project demonstrates practical SOC analyst skills using industry-standard cybersecurity tools and methodologies.

---

## Lab Architecture

### Environment Overview

| Component | IP Address | Purpose |
|------------|------------|----------|
| Kali Linux | 192.168.56.104 | Analyst Machine |
| Metasploitable2 | 192.168.56.103 | Vulnerable Target |
| VirtualBox Host-Only Network | 192.168.56.0/24 | Isolated Lab Network |

### Architecture Diagram

![SOC Architecture Diagram](screenshots/SOC%20architecture%20diagram.jpeg)

---

## Skills Demonstrated

- Network Verification
- Network Reconnaissance
- Nmap Enumeration
- Service Discovery
- Wireshark Traffic Analysis
- Packet Capture Analysis
- Evidence Collection
- Security Assessment
- Incident Documentation
- Vulnerability Identification
- Linux Administration
- Cybersecurity Reporting

---

## Tools Used

- Kali Linux
- VirtualBox
- Metasploitable2
- Nmap
- Wireshark

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

- Successful ICMP communication
- 0% packet loss
- Connectivity confirmed

### Screenshot

![Ping Test](screenshots/ping_test.jpeg)

---

## Phase 2 – Reconnaissance

### Objective

Identify active services running on the target system.

### Command

```bash
sudo nmap -sV 192.168.56.103
```

### Services Identified

| Port | Service |
|--------|----------|
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
| 6667 | IRC |

### Screenshot

![Nmap Scan](screenshots/nmap_scan.png)

---

## Phase 3 – Traffic Analysis

### Objective

Capture and analyze network traffic generated during reconnaissance activities.

### Tool

Wireshark

### Observed Traffic

- ICMP Echo Requests and Replies
- TCP Connection Attempts
- SMB Communication
- NetBIOS Traffic
- Service Discovery Traffic

### Screenshot

![Wireshark Capture](screenshots/wireshark_capture.jpeg)

---

## Phase 4 – Evidence Collection

### Objective

Preserve collected evidence for analysis and reporting.

### Evidence Collected

- Packet Capture File
- Nmap Scan Results
- Investigation Screenshots
- Findings Report

### Packet Capture

```text
pcaps/network_capture.pcapng
```

---

# Investigation Findings

## Host Information

| System | IP Address |
|----------|------------|
| Analyst Machine | 192.168.56.104 |
| Target Machine | 192.168.56.103 |

---

## Security Observations

### Network Connectivity

- Successful communication established between analyst and target systems.
- ICMP traffic observed and validated.
- No packet loss detected.

### Service Discovery

Multiple services were exposed on the target system.

### Identified Services

| Service | Risk Level |
|----------|------------|
| FTP | Medium |
| SSH | Low |
| Telnet | High |
| SMTP | Medium |
| DNS | Low |
| HTTP | Medium |
| NetBIOS | High |
| SMB | High |
| MySQL | Medium |
| PostgreSQL | Medium |
| VNC | Medium |
| IRC | Medium |

---

## Risk Assessment

The target system exposes multiple services that increase the attack surface and could be exploited by attackers.

### Key Risks

- Unencrypted Telnet communication
- SMB exposure
- NetBIOS information disclosure
- Multiple publicly accessible services

### Potential Impact

- Unauthorized access
- Credential compromise
- Information disclosure
- Lateral movement opportunities

---

## Recommendations

1. Disable unnecessary services.
2. Replace Telnet with SSH.
3. Restrict SMB access.
4. Implement firewall controls.
5. Continuously monitor network traffic.
6. Conduct regular vulnerability assessments.

---

## Key Achievements

- Verified connectivity between analyst and target systems.
- Identified multiple exposed network services.
- Captured and analyzed live network traffic.
- Preserved evidence through screenshots and packet captures.
- Conducted security assessment of discovered services.
- Produced professional investigation documentation and reporting.

---

## Repository Structure

```text
SOC-Investigation-Lab/
│
├── docs/
│   ├── Phase1-Network-Verification.md
│   ├── Phase2-Reconnaissance.md
│   ├── Phase3-Traffic-Analysis.md
│   ├── Phase4-Evidence-Collection.md
│   └── Findings.md
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

- Nessus Vulnerability Scanning
- OpenVAS Integration
- Snort IDS Monitoring
- Suricata Alert Analysis
- SIEM Integration
- Incident Response Playbooks

---

## Author

**Om Sone**

Cybersecurity Student | SOC Analyst Enthusiast | Network Security Learner

---

## Disclaimer

This project was conducted in an isolated laboratory environment using intentionally vulnerable systems for educational and research purposes only.
