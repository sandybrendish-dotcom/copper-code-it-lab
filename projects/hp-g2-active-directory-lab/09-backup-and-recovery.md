# Backup and Recovery

## Objectives

- Back up Proxmox VM configuration and disks
- Protect documentation and scripts
- Test restoration rather than assuming backups work

## Planned tests

- [X] Create Proxmox VM backup
- [ ] Restore a Windows client VM
- [ ] Restore a file from backup
- [ ] Record recovery time
- [ ] Document domain-controller recovery considerations
- [ ] Store sensitive recovery details privately

## Recovery record

| Test | Date | Result | Recovery time | Notes |
|---|---|---|---:|---|
| Client VM restore | TBD | Pending | TBD | |
| File restore | TBD | Pending | TBD | |


## Proxmox backup target

A dedicated NFS dataset was created on the TrueNAS server for Proxmox VM backups.

### Configuration

- Backup platform: TrueNAS SCALE
- Protocol: NFS
- Proxmox storage ID: `truenas-backups`
- Allowed content: VZDump backup files only
- Access restricted to the Proxmox host
- NAS addressed by IP to avoid backup dependency on internal DNS

### Validation

- Proxmox detected the NFS export
- Storage showed as active
- Test file creation succeeded
- Test file deletion succeeded

### Future testing

- Create first VM backup
- Restore a VM into a new VM ID
- Validate guest boot and services
- Configure retention only after backup sizes are measured


## TrueNAS backup target validation

A dedicated NFS backup target was added to Proxmox.

### Validation

- TrueNAS NFS service active
- Proxmox detected the export
- Storage status displayed as active
- Backup content restricted to VZDump backup files
- System time and NTP confirmed before backup scheduling

### Next steps

- Create the first Windows Server VM
- Produce an initial test backup
- Restore the VM using a different VM ID
- Measure backup size and duration
- Create an appropriate retention policy