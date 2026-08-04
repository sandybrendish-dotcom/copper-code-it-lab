# TrueNAS Storage Server

## Project summary

Design, deploy and operate a reliable home storage and application server using an HP EliteDesk 800 G1 SFF and TrueNAS SCALE.

The system provides central file storage, media services, photo management, backups and remote access for the Copper Code homelab.

## Status

**Operational and expanding**

## Objectives

- Centralise important files and media
- Provide redundant storage using a mirrored ZFS pool
- Create SMB shares for Windows clients
- Run self-hosted applications
- Provide remote access through Tailscale
- Configure snapshots and backup workflows
- Document failures, fixes and recovery procedures
- Keep the system simple, reliable and easy to recover

## Hardware

| Component | Details |
|---|---|
| Host | HP EliteDesk 800 G1 SFF |
| CPU | Intel Core i5-4690 |
| Memory | 16 GB DDR3 |
| Boot storage | 128 GB SSD |
| Application storage | SanDisk X400 approximately 256 GB |
| Main storage | 2 × 4 TB hard drives |
| Pool layout | Two-disk ZFS mirror |
| Network | Gigabit Ethernet |
| Operating system | TrueNAS SCALE |

## Services

| Service | Purpose | Status |
|---|---|---|
| SMB | Windows file sharing | Operational |
| Jellyfin | Media streaming | Operational |
| Immich | Photo management | Operational |
| Tailscale | Private remote access | Operational |
| Snapshots | Data protection | Configured |
| Email alerts | System notifications | Operational |
| Home Assistant | Smart-home platform | Planned |

## Storage design

The main storage pool uses a two-disk ZFS mirror.

This design was selected because it provides:

- tolerance for one drive failure;
- straightforward recovery;
- simple expansion planning;
- better reliability than a single disk;
- a good balance between capacity and redundancy for the current hardware.

A mirror is not a backup. Important data still requires copies on separate storage.

## Dataset and share structure

The server has used datasets and SMB shares including:

- Documents
- Downloads
- Media
- Backups
- Public
- Home

The exact active structure may change as the server is refined. Public documentation does not expose private paths, usernames or permissions.

## Applications

### Jellyfin

Jellyfin is used for media streaming.

Work completed includes:

- application installation;
- dataset and permission configuration;
- library scanning;
- child dataset ACL fixes;
- hardware transcoding configuration;
- television client connection.

### Immich

Immich is used for photo management.

Work completed includes:

- application installation;
- PostgreSQL permission troubleshooting;
- correction of ownership mismatch;
- creation of an external library;
- monitoring of initial photo indexing load;
- validation of access and photo loading.

### Tailscale

Tailscale provides private remote access without exposing the server directly to the public internet.

## Backup and recovery

The server is part of the broader homelab backup design.

Current and planned controls include:

- ZFS snapshots;
- workstation backup jobs to the NAS;
- restore testing;
- email alerts;
- SMART monitoring;
- configuration documentation;
- UPS integration when the final physical placement is complete.

## Monitoring and maintenance

Routine checks include:

- storage capacity;
- pool health;
- disk health;
- CPU temperature;
- application status;
- backup success;
- snapshot completion;
- email alerts;
- network connectivity.

## Problems solved

This project includes documented troubleshooting for:

- application permissions;
- missing SMB shares;
- Jellyfin library access;
- Immich PostgreSQL ownership mismatch;
- application recovery after power or network changes;
- Windows SMB remapping;
- slow photo indexing under load;
- storage and ACL configuration.

## Skills demonstrated

- TrueNAS SCALE
- ZFS mirrors
- Storage planning
- SMB file sharing
- ACL and permission troubleshooting
- Application deployment
- Docker-style container services
- Media server administration
- Photo management
- Tailscale remote access
- Snapshots and backups
- Monitoring and alerting
- Troubleshooting and recovery
- Technical documentation

## Documentation

- [Project plan](01-project-plan.md)
- [Hardware inventory](02-hardware-inventory.md)
- [Storage design](03-storage-design.md)
- [SMB and permissions](04-smb-and-permissions.md)
- [Applications](05-applications.md)
- [Backup and recovery](06-backup-and-recovery.md)
- [Monitoring and maintenance](07-monitoring-and-maintenance.md)
- [Troubleshooting log](troubleshooting-log.md)
- [Lessons learned](08-lessons-learned.md)
