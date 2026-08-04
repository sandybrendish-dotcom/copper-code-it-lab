# Applications

## Jellyfin

### Purpose

Provide local media streaming to computers and televisions.

### Work completed

- Installed Jellyfin
- Configured storage access
- Corrected ACL issues
- Fixed library scanning
- Configured hardware transcoding
- Connected television client

### Validation

- Libraries visible
- Media playback works
- Hardware transcoding enabled
- Service survives reboot

## Immich

### Purpose

Provide private photo management and browsing.

### Work completed

- Installed Immich
- Troubleshot PostgreSQL ownership mismatch
- Corrected dataset permissions
- Created an external library
- Confirmed photos indexed progressively
- Monitored server load during ingestion

### Validation

- Web interface loads
- Photos appear
- External library scans
- Database remains healthy
- Application survives restart

## Tailscale

### Purpose

Provide private remote access to the server.

### Validation

- Server joins tailnet
- Remote connection succeeds
- No direct public port exposure required
