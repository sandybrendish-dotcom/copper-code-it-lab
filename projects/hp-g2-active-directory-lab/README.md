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
