# IP Address Plan – DNS Defense System

## Network Information
Network      : 192.168.70.0/24
Subnet Mask  : 255.255.255.0
Gateway      : 192.168.70.1

## Host List

| Hostname        | Role                | Planned OS              | IP Address |
|-----------------|---------------------|-------------------------|------------|
| R-Gateway       | Network Gateway     | Ubuntu Server           | 192.168.70.1 |
| DNS-SERVER      | Target DNS Server   | Ubuntu Server + Bind9   | 192.168.70.10 |
| SECURITY-ONION  | Monitoring (IDS)    | Security Onion          | 192.168.70.50 |
| ATTACKER-KALI   | Attacker Node       | Kali Linux              | 192.168.70.100 |
