# HP EliteDesk G2 Active Directory Lab

## Project summary

Build a virtualised Windows Server environment on an HP EliteDesk 800 G2 to practise enterprise systems administration, networking, identity management and security.

## Status

**Current phase:** Hardware inspection and pre-deployment testing

## Objectives

- Validate the HP G2 hardware before deployment
- Install Proxmox VE
- Create an isolated virtual lab network
- Deploy Windows Server
- Configure Active Directory Domain Services
- Configure DNS
- Create users, groups and organisational units
- Join Windows client VMs to the domain
- Deploy Group Policy
- Configure file shares and NTFS permissions
- Automate routine tasks with PowerShell
- Test backup and recovery
- Document troubleshooting and lessons learned

## Planned environment

| System | Role | Suggested resources |
|---|---|---|
| Proxmox host | Virtualisation platform | Physical HP EliteDesk G2 |
| CC-DC01 | Domain controller and DNS | 2 vCPU, 4 GB RAM, 60 GB disk |
| CC-CLIENT01 | Windows client | 2-4 vCPU, 4-6 GB RAM, 64 GB disk |
| CC-CLIENT02 | Second Windows client | 2 vCPU, 4 GB RAM, 64 GB disk |
| CC-FS01 | File server, later phase | 2 vCPU, 4 GB RAM, 80 GB disk |

## Documentation

- [Project plan](01-project-plan.md)
- [Hardware inventory](02-hardware-inventory.md)
- [Pre-deployment testing](03-pre-deployment-testing.md)
- [Proxmox installation](04-proxmox-installation.md)
- [Virtual network design](05-virtual-network-design.md)
- [Windows Server installation](06-windows-server-installation.md)
- [Active Directory deployment](07-active-directory-deployment.md)
- [Group Policy](08-group-policy.md)
- [Backup and recovery](09-backup-and-recovery.md)
- [Testing and validation](10-testing-and-validation.md)
- [Troubleshooting log](troubleshooting-log.md)

## Skills demonstrated

- Hardware validation
- Virtualisation
- Windows Server
- Active Directory
- DNS
- Group Policy
- PowerShell
- Network design
- Security permissions
- Backup and recovery
- Technical documentation


# Windows Server Active Directory Lab

## Project Overview

This project documents the design and implementation of a Windows Server Active Directory lab running on Proxmox.

The objective of this lab is to simulate a small business IT environment while developing practical skills used in IT Help Desk, Systems Administration and Infrastructure Engineering roles.

---

# Objectives

- Deploy a Windows Server 2022 Domain Controller
- Configure Active Directory Domain Services (AD DS)
- Configure integrated DNS
- Build a realistic organisational structure
- Create security groups using best practices
- Create departmental user accounts
- Deploy Windows 11 client computers
- Join clients to the Active Directory domain
- Learn enterprise administration and troubleshooting

---

# Lab Infrastructure

## Physical Host

| Component | Specification |
|-----------|---------------|
| Host | HP EliteDesk G2 |
| Hypervisor | Proxmox VE |
| Backup Storage | TrueNAS NFS |
| Network | Isolated AD Lab Network |

---

## Virtual Machines

| VM | Purpose | IP Address |
|----|----------|------------|
| CC-DC01 | Domain Controller | 10.20.0.10 |
| CC-CLIENT01 | Windows 11 Client | 10.20.0.20 |

---

# Network Design

```
                    Internet
                        │
                  EdgeRouter X
                        │
                 192.168.1.0/24
                        │
                 Proxmox Host
                  vmbr0 (LAN)
                        │
                 NAT (iptables)
                        │
                vmbr1 (10.20.0.1)
                        │
             10.20.0.0/24 AD Lab
                │             │
         CC-DC01        CC-CLIENT01
      10.20.0.10        10.20.0.20
```

---

# Active Directory

## Forest

```
ad.coppercode.test
```

## NetBIOS

```
COPPERCODE
```

---

# DNS Configuration

The Domain Controller hosts the Active Directory DNS zone.

Internal queries:

```
ad.coppercode.test
```

are resolved locally.

External DNS requests are forwarded to:

```
192.168.1.166
```

(AdGuard Home)

---

# Organisational Unit Structure

```
ad.coppercode.test
│
└── Copper Code
    ├── Admin Accounts
    ├── Groups
    ├── Servers
    ├── Service Accounts
    ├── Users
    │   ├── Administration
    │   ├── Help Desk
    │   ├── Management
    │   ├── Repairs
    │   └── Sales
    └── Workstations
```

---

# Security Groups

```
GG-Administration
GG-HelpDesk
GG-Management
GG-Repairs
GG-Sales
GG-IT-Admins
```

Global Security Groups are used to simplify permissions and follow Microsoft Active Directory best practices.

---

# Test Users

| Username | Department |
|----------|------------|
| sandy.admin | Administration |
| alex.repair | Repairs |
| jamie.sales | Sales |

---

# Windows Client

The first Windows 11 client was:

```
CC-CLIENT01
```

Configuration:

- Windows 11 Pro
- VirtIO Drivers
- QEMU Guest Agent
- Joined to Active Directory
- Authenticated using domain credentials

---

# Backup Strategy

Backups are stored on:

- TrueNAS
- NFS Storage
- ZSTD Compression
- Proxmox Snapshot Backups

Baseline backups were created before and after Active Directory deployment.

---

# Skills Demonstrated

## Virtualisation

- Proxmox VE
- Virtual Networking
- VirtIO
- TPM 2.0
- UEFI Virtual Machines

## Windows Server

- Windows Server 2022
- Active Directory Domain Services
- DNS
- Domain Controller Promotion
- Domain Join
- Organizational Units
- Security Groups
- User Administration

## Networking

- Static IP Addressing
- NAT Routing
- DNS Forwarding
- Active Directory DNS
- Internal Name Resolution

## Linux

- systemd Services
- iptables
- NAT (MASQUERADE)
- NFS Storage
- Shell Administration

---

# Lessons Learned

During this project I learned how Active Directory depends heavily on DNS and why clients must use the Domain Controller as their DNS server.

I also learned how to isolate an enterprise lab using Proxmox virtual networking while maintaining internet connectivity through Linux NAT.

Creating Organisational Units and Security Groups before creating users makes future administration significantly easier and follows Microsoft's recommended design practices.

---

# Future Improvements

- Group Policy Objects (GPO)
- Windows Server Update Services (WSUS)
- File Server
- Roaming Profiles
- Folder Redirection
- DFS
- Certificate Services
- Additional Domain Controller
- DHCP Server
- Print Server
- Remote Desktop Services

---

# Status

✅ Operational

Current Version:

```
v1.0
```