# Backup and Recovery

## Current controls

- ZFS snapshots
- Workstation backup jobs to the NAS
- Restore testing
- Email alerts
- Tailscale for remote administration
- Configuration notes

## Important principle

The NAS is a storage system, not the only copy of important data.

## Recovery tests

| Test | Status | Notes |
|---|---|---|
| Restore workstation backup | Completed | Restore test successful |
| Recover SMB mapping | Completed | Reconnected after network changes |
| Recover applications after interruption | Completed | Applications restored after troubleshooting |
| Restore deleted file from snapshot | To document | Future validation |
| Full configuration recovery | Planned | Requires tested procedure |

## Future improvements

- UPS shutdown integration
- Separate off-device backup
- Periodic restore tests
- Exported configuration stored securely
- Documented replacement-drive procedure
