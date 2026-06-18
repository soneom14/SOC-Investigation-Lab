# Final SOC Investigation Findings

## Analyst System

* Operating System: Kali Linux
* IP Address: 192.168.56.104

## Target System

* Operating System: Metasploitable2
* IP Address: 192.168.56.103

## Investigation Objective

Perform an end-to-end SOC investigation by identifying active services, capturing network traffic, and documenting security observations within a controlled laboratory environment.

## Reconnaissance Results

Service discovery identified multiple exposed services:

| Port | Service    | Version          |
| ---- | ---------- | ---------------- |
| 21   | FTP        | vsftpd 2.3.4     |
| 22   | SSH        | OpenSSH 4.7p1    |
| 23   | Telnet     | Linux telnetd    |
| 25   | SMTP       | Postfix smtpd    |
| 53   | DNS        | ISC BIND 9.4.2   |
| 80   | HTTP       | Apache 2.2.8     |
| 139  | NetBIOS    | Samba 3.x        |
| 445  | SMB        | Samba 3.x        |
| 3306 | MySQL      | MySQL 5.0.51a    |
| 5432 | PostgreSQL | PostgreSQL 8.3   |
| 5900 | VNC        | VNC Protocol 3.3 |
| 6667 | IRC        | UnrealIRCd       |
| 8180 | HTTP       | Apache Tomcat    |

## Traffic Analysis

Network communication was captured using Wireshark during reconnaissance activities.

Observed traffic included:

* ICMP Echo Requests and Replies
* TCP Connection Attempts
* TCP Reset Responses
* Service Discovery Traffic
* SMB/NetBIOS Announcements

## Risk Assessment

The target system exposes numerous network services which significantly increase the attack surface. Legacy software versions and multiple publicly exposed services represent potential security risks that would require monitoring and hardening in a production environment.

## Conclusion

The investigation successfully demonstrated the SOC workflow of reconnaissance, evidence collection, packet analysis, and incident documentation using open-source cybersecurity tools.
