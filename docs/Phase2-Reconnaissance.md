# Phase 2 - Reconnaissance

## Objective

Identify active services running on the target machine.

## Command

```bash
sudo nmap -sV 192.168.56.103
```

## Results

The following services were identified:

| Port | Service |
|--------|---------|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 80 | HTTP |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 5900 | VNC |
| 6667 | IRC |

## Screenshot

Insert Nmap screenshot here.
