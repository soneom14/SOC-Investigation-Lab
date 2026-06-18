# Findings

## Host Information

| System | IP Address |
|----------|------------|
| Analyst Machine (Kali Linux) | 192.168.56.104 |
| Target Machine (Metasploitable2) | 192.168.56.103 |

---

## Investigation Summary

A Security Operations Center (SOC) investigation was conducted in a controlled laboratory environment to verify connectivity, identify active services, capture network traffic, and document security observations on the target system.

---

## Observations

### Network Connectivity

- Successful ICMP communication observed between analyst and target systems.
- No packet loss detected during connectivity testing.
- Target host responded consistently to ping requests.

### Service Discovery Results

The Nmap scan identified multiple active services running on the target machine.

| Port | Service | Risk Level |
|--------|----------|------------|
| 21 | FTP | Medium |
| 22 | SSH | Low |
| 23 | Telnet | High |
| 25 | SMTP | Medium |
| 53 | DNS | Low |
| 80 | HTTP | Medium |
| 139 | NetBIOS | High |
| 445 | SMB | High |
| 3306 | MySQL | Medium |
| 5432 | PostgreSQL | Medium |
| 5900 | VNC | Medium |
| 6667 | IRC | Medium |

---

## Traffic Analysis

Network traffic captured in Wireshark revealed:

- ICMP Echo Requests and Replies
- TCP Handshake Attempts
- Service Discovery Activity
- SMB and NetBIOS Communications
- Network Broadcast Traffic

Traffic patterns matched expected reconnaissance behavior performed during the investigation.

---

## Security Assessment

### Identified Risks

- Telnet service transmits data in clear text.
- SMB and NetBIOS services increase attack surface.
- Multiple exposed services provide additional entry points for attackers.
- Legacy services present potential security weaknesses.

### Potential Impact

If deployed in a production environment, these exposed services could lead to:

- Unauthorized Access
- Credential Theft
- Information Disclosure
- Lateral Movement Opportunities

---

## Evidence Collected

### Packet Capture

Location:

```text
pcaps/network_capture.pcapng
```

### Screenshots

- Ping Verification
- Nmap Service Discovery
- Wireshark Traffic Analysis
- Network Architecture Diagram

---

## Recommendations

1. Disable unused services.
2. Replace Telnet with SSH.
3. Restrict SMB access where unnecessary.
4. Implement firewall rules to limit exposure.
5. Continuously monitor network traffic.
6. Conduct regular vulnerability assessments.

---

## Conclusion

The SOC investigation successfully demonstrated the complete workflow of:

- Network Verification
- Service Enumeration
- Traffic Analysis
- Evidence Collection
- Security Documentation

The target machine exposed multiple services that would require monitoring and hardening in a real-world environment. Evidence was successfully captured, analyzed, and documented using Kali Linux, Nmap, and Wireshark.
