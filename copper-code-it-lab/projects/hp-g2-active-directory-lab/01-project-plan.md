# Project Plan

## Business scenario

Create a small virtualised Windows environment for a fictional Copper Code organisation. The lab will model several departments and users while remaining isolated from the normal household network.

## Scope

### Included

- Proxmox host
- One domain controller
- Two Windows client VMs
- Active Directory
- DNS
- Group Policy
- File permissions
- PowerShell
- Backup and restore testing

### Excluded from the first phase

- Production household DNS
- Production DHCP
- Public internet-facing services
- Real customer or employee data
- Connection to business production systems

## Success criteria

- Hardware passes stability testing
- Proxmox installs and remains stable
- Windows clients join the domain
- DNS resolves correctly
- Group Policies apply successfully
- Permissions prevent unauthorised access
- Backups can be restored
- All major decisions and problems are documented
