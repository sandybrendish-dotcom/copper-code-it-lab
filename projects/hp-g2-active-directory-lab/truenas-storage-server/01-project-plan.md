# Project Plan

## Business scenario

Copper Code and the homelab require central storage for documents, media, backups and self-hosted services.

The server must be:

- reliable;
- simple to operate;
- easy to recover;
- energy-conscious;
- suitable for 24/7 operation;
- expandable without unnecessary complexity.

## Scope

### Included

- TrueNAS SCALE
- ZFS mirrored storage
- SMB shares
- Jellyfin
- Immich
- Tailscale
- Snapshots
- Email alerts
- Backup workflows
- Monitoring and recovery documentation

### Planned

- Home Assistant
- UPS integration
- Improved long-term backup separation
- Additional storage expansion where required

## Success criteria

- Storage pool remains healthy
- SMB access works reliably
- Applications restart after reboot
- Important data is protected by snapshots and external backups
- Restore procedures are tested
- Remote access does not require unsafe public exposure
- Problems and fixes are documented
