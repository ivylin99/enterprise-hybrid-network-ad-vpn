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

### Secure Web Services
![HTTPS Login](screenshots/site7-login.png)
![Public Site](screenshots/site2.png)

### File Sharing & Permissions
![Windows Share](screenshots/windows-share.png)
![Linux Samba](screenshots/linux-samba.png)

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
