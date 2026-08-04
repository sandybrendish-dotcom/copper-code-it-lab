# Troubleshooting Log

## Immich PostgreSQL ownership mismatch

### Symptoms

Immich failed to start correctly because the PostgreSQL data directory ownership did not match the container requirements.

### Evidence

The base directory used one owner while the PostgreSQL container expected another.

### Resolution

Permissions and ownership were corrected, allowing the application to load.

### Validation

- Immich web interface loaded
- External library was created
- Photos began appearing
- Server load reflected active indexing

## Jellyfin library permissions

### Symptoms

Libraries did not scan correctly or media was not visible.

### Cause

Dataset and child dataset ACLs did not allow the application to access all required paths.

### Resolution

ACLs were corrected for the relevant datasets.

### Validation

- Libraries scanned
- Media appeared
- Playback worked
- Hardware transcoding settings were saved

## Shares and applications missing after power or network changes

### Symptoms

SMB shares became inaccessible and applications appeared missing.

### Resolution

Shares and application access were re-established, and Windows mappings were restored.

### Lesson

Power, network and storage configuration changes must be followed by structured validation of:

1. pool health;
2. datasets;
3. shares;
4. applications;
5. client access.
