# Investigation Findings

## Executive Summary

This investigation was conducted in a controlled laboratory environment using Kali Linux as the analyst workstation and Metasploitable2 as the target system. The objective was to validate network connectivity, identify exposed services, analyze network traffic, collect evidence, and assess potential security risks. Multiple services were discovered on the target machine, and network traffic was successfully captured and analyzed using Wireshark.

---

## Host Information

| System                           | IP Address     |
| -------------------------------- | -------------- |
| Kali Linux (Analyst Machine)     | 192.168.56.104 |
| Metasploitable2 (Target Machine) | 192.168.56.103 |

---

## Key Findings

### Network Verification

* Successful ICMP communication was established between the analyst and target systems.
* No packet loss was observed during connectivity testing.
* The target machine was reachable and responsive.

### Service Discovery

The Nmap scan identified multiple active services on the target machine:

| Port | Service    | Risk Level |
| ---- | ---------- | ---------- |
| 21   | FTP        | Medium     |
| 22   | SSH        | Low        |
| 23   | Telnet     | High       |
| 25   | SMTP       | Medium     |
| 53   | DNS        | Low        |
| 80   | HTTP       | Medium     |
| 139  | NetBIOS    | High       |
| 445  | SMB        | High       |
| 3306 | MySQL      | Medium     |
| 5432 | PostgreSQL | Medium     |
| 5900 | VNC        | Medium     |
| 6667 | IRC        | Medium     |

### Traffic Analysis

Wireshark analysis confirmed the following network activity:

* ICMP Echo Requests and Echo Replies
* TCP connection attempts to exposed services
* SMB communication traffic
* NetBIOS service broadcasts
* Network reconnaissance activity generated during Nmap scanning

---

## Evidence Collected

The following evidence was collected during the investigation:

* Ping connectivity screenshots
* Nmap service discovery results
* Wireshark packet captures
* Packet Capture (PCAP) file
* Final investigation report

### Evidence Locations

```text
screenshots/ping_test.jpeg
screenshots/nmap_scan.png
screenshots/wireshark_capture.jpeg
pcaps/network_capture.pcapng
reports/final_findings.md
```

---

## Risk Assessment

The target system exposes numerous services that significantly increase the attack surface.

### High Risk Services

* Telnet (Port 23)
* SMB (Port 445)
* NetBIOS (Port 139)

### Security Concerns

* Telnet transmits credentials in plaintext.
* SMB exposure may allow unauthorized access and lateral movement.
* NetBIOS can reveal system and network information.
* Multiple active services increase the likelihood of exploitation.

### Potential Impact

* Unauthorized access
* Credential theft
* Information disclosure
* Service exploitation
* Lateral movement within a network

---

## Recommendations

1. Disable unnecessary services.
2. Replace Telnet with SSH for secure remote access.
3. Restrict SMB and NetBIOS access using firewall rules.
4. Apply security updates and patches regularly.
5. Implement network monitoring and logging.
6. Conduct routine vulnerability assessments.
7. Follow the principle of least privilege.

---

## Conclusion

The SOC investigation successfully demonstrated the complete workflow of network verification, reconnaissance, traffic analysis, evidence collection, and security assessment. The target system was found to expose multiple services, including several high-risk services that would require remediation in a production environment. The collected evidence and findings provide a clear understanding of the system's security posture and highlight areas for improvement.
