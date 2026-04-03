# Enterprise Hybrid Network PoC

Built a hybrid Windows and Linux network proof of concept with Active Directory, VPN using RADIUS authentication, secure web hosting, and cross-platform file sharing.

## Overview
This repository documents a hands-on Windows and Linux network lab designed to demonstrate system administration, networking, and access control skills.

The project simulates a small business environment with Active Directory, secure remote access, Windows and Linux server integration, web hosting, and group-based permissions for internal and external clients.

This work was completed independently as part of a server administration assignment and is presented here as a portfolio project.

## Network Topology
<img width="1473" height="841" alt="1" src="https://github.com/user-attachments/assets/c0a59bbb-167b-4d5b-bcdc-8aed3938f7cb" />

## Architecture & Key Components

### Active Directory Domain
- Custom domain (`firstname.com`)
- User and group creation using PowerShell
- Organizational Units and security groups
- Centralized authentication and authorization

### Windows Server Infrastructure
- **Domain Controller**
  - Active Directory, DNS, DHCP
  - IIS hosting multiple HTTP/HTTPS websites
- **VPN / RRAS Server**
  - Dual NIC configuration (internal LAN + NAT)
  - Remote access using RADIUS through NPS
  - DHCP failover configured with a 60/40 split

### Linux Server
- Joined to Active Directory using `net ads`
- Samba file sharing for domain users
- Apache web server hosting:
  - CGI guestbook application
  - Restricted website with authentication
- SSH access limited to one privileged local user
- `sudo` configured for controlled administration

## Security & Access Control
- Group-based access control using Active Directory security groups
- VPN access limited to authorized users
- Windows Authentication and HTTPS for secure web access
- File share permissions configured using AGLP principles
- Least-privilege access applied across systems

## Client Validation & Testing

### Internal Client
- Domain-joined Windows workstation
- Verified:
  - website access and authentication
  - SMB and Samba permissions
  - DNS name resolution and service access

### External Client
- Tested VPN connectivity
- Verified access to:
  - internal web services
  - file shares
  - Linux management through SSH
- Used RSAT tools for remote Windows administration

## Technologies Used
- Windows Server (AD DS, DNS, DHCP, IIS, NPS, RRAS)
- Active Directory
- PowerShell
- Linux
- Samba, Apache, SSH
- VPN and RADIUS authentication
- TCP/IP, NAT, DHCP failover

## Validation Screenshots

### Active Directory Automation
<img width="1428" height="904" alt="image" src="https://github.com/user-attachments/assets/645e9cd3-ae0a-47cc-8786-e65a769e22e1" />
<img width="1593" height="1323" alt="image" src="https://github.com/user-attachments/assets/8d295df7-76eb-4292-8853-a86ae6a46644" />

### Secure Web Services
<img width="1698" height="765" alt="2" src="https://github.com/user-attachments/assets/4e93f0d9-e585-4a36-abcb-61c1a48cd5cf" />
<img width="1647" height="1080" alt="3" src="https://github.com/user-attachments/assets/3b09993c-979f-4777-9d95-0deacb7163d7" />
<img width="1174" height="1262" alt="4" src="https://github.com/user-attachments/assets/e1e39ea0-4488-4afe-9800-019827c07b94" />

### File Sharing & Permissions
<img width="913" height="535" alt="image" src="https://github.com/user-attachments/assets/6970a0bb-12a9-47b6-b84b-63fd6f17117c" />


### Secure Remote Access (VPN)
![VPN Connected](screenshots/vpn-connected.png)
![Internal Access via VPN](screenshots/vpn-internal-access.png)


## Platform Reflection
- Windows: centralized management (Active Directory, Group Policy)
- Linux: flexible configuration and lightweight services
- Hybrid setup: combines centralized authentication with open-source services

## Purpose
This project is included in my portfolio to show:
- hands-on network and server administration
- Windows and Linux integration
- secure configuration and access control
