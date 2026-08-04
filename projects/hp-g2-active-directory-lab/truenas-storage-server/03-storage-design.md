# Storage Design

## Main pool

The main pool uses two 4 TB hard drives in a ZFS mirror.

## Why a mirror was selected

A mirror provides:

- one-drive fault tolerance;
- simple replacement workflow;
- predictable performance;
- straightforward recovery;
- lower complexity than parity layouts for this small system.

## Limitations

A mirror does not protect against:

- accidental deletion;
- ransomware;
- application corruption;
- theft;
- fire;
- multiple drive failures;
- operator error.

Snapshots and separate backups are still required.

## Dataset planning

Datasets have included:

- Documents
- Downloads
- Media
- Backups
- Public
- Home

Each dataset should have a clear purpose, owner and permission model.

## Design principles

- Separate application data from general shares where practical.
- Avoid unnecessary nested datasets.
- Document ACL ownership.
- Test access after permission changes.
- Keep sufficient free space for healthy ZFS operation.
