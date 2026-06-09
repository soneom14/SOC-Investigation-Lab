# Findings

## Host Information

Victim IP: 192.168.56.103

Analyst System: Kali Linux (192.168.56.104)

## Observations

1. ICMP communication between the analyst workstation and victim host was successfully observed.

2. Service discovery activity identified multiple exposed network services.

3. The following services were detected:

* FTP (21)
* SSH (22)
* Telnet (23)
* SMTP (25)
* HTTP (80)
* NetBIOS (139)
* SMB (445)
* MySQL (3306)
* PostgreSQL (5432)
* VNC (5900)
* IRC (6667)

## Risk Assessment

The victim machine exposes numerous services that increase the attack surface and would require monitoring in a production environment.

## Evidence

* Wireshark ICMP Capture
* Wireshark Nmap Capture
* Nmap Service Discovery Results
