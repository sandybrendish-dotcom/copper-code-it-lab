# Proxmox Installation

## Preparation

- [X] Hardware testing complete
- [X] BIOS updated if required
- [X] Intel VT-x enabled
- [X] Intel VT-d enabled if available
- [X] UEFI boot confirmed
- [X] Proxmox installer USB created
- [X] Existing Windows licence information recorded if required

## Installation record

| Item | Value |
|---|---|
| Proxmox version | 9.2.2 |
| Installation date | 5/08/26 |
| Hostname | g2-pve.home.arpa |
| Management address | Sanitised in public documentation |
| Storage layout | TBD |
| File system | TBD |

## Validation

- [X] Web interface accessible
- [X] Updates installed
- [X] Reboot successful
- [X] Storage detected
- [X] Network link stable
- [X] System time correct
- [ ] Backup destination planned


## Initial platform update

After the first successful login:

- Disabled the subscription-only enterprise repository
- Enabled the Proxmox no-subscription repository
- Refreshed package indexes
- Installed all available updates
- Rebooted the host
- Confirmed the node, storage and network returned successfully

### Validation

- Proxmox web interface accessible
- Package refresh completed without repository errors
- Node returned after reboot
- Management address remained reachable