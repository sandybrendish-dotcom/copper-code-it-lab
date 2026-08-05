# Troubleshooting Log

Record problems as they happen. Do not remove failed attempts; explain why they failed.

## Entry template

### Date

**Problem**

Describe the visible symptoms.

**Impact**

Explain what could not be completed.

**Initial hypothesis**

List the most likely causes before changing anything.

**Evidence gathered**

- Logs
- Error messages
- Commands
- Screenshots
- Configuration checks

**Actions taken**

1. First action
2. Second action
3. Third action

**Root cause**

State the confirmed cause, or clearly say it remains unconfirmed.

**Resolution**

Describe the final fix.

**Validation**

Explain how the fix was tested.

**Lesson learned**

Explain what you would do sooner or differently next time.


## Proxmox management interface unreachable

### Symptoms

The Proxmox console displayed the original installation address and the web interface could not be reached.

### Findings

The management bridge had been changed to `192.168.1.40/24`, but the physical network interface showed `NO-CARRIER` and `state DOWN`.

### Root cause

The Ethernet interface did not have an active physical link.

### Resolution

The physical network connection was corrected and the Proxmox web interface became reachable at:

`https://192.168.1.40:8006`

### Validation

- Management interface loaded successfully
- Proxmox login succeeded
- Host was reachable from another LAN device
