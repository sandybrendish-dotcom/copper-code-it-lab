# Pre-deployment Testing

## Test standard

The system must pass all essential tests before Proxmox is installed.

| Test | Tool | Duration | Result | Evidence |
|---|---|---:|---|---|
| Memory | MemTest86 | 4 passes | Pending | Add sanitised screenshot |
| CPU stability | OCCT or Prime95 | 60 minutes | Pending | Add result |
| Combined load | OCCT Power | 15-20 minutes | Pending | Add result |
| Storage SMART | CrystalDiskInfo | Inspection | Pending | Add result |
| Storage performance | CrystalDiskMark | One run | Pending | Add result |
| Network throughput | iperf3 | Both directions | Pending | Add result |
| Reboot testing | Manual | Multiple cycles | Pending | Notes |
| Cold boot | Manual | Power disconnected | Pending | Notes |

## Acceptance criteria

- Zero memory errors
- No CPU calculation errors
- No crashes, freezes or unexpected shutdowns
- No severe sustained thermal throttling
- Storage SMART data healthy
- Gigabit Ethernet negotiated successfully
- Approximately 900 Mbps or better over a healthy wired gigabit connection
- Reliable restarts and cold boots

## Recorded results

### Temperatures

| Test | Idle | Maximum | Notes |
|---|---:|---:|---|
| CPU | TBD | TBD | |
| SSD | TBD | TBD | |

### Benchmark baseline

| Benchmark | Result |
|---|---:|
| Cinebench single-core | TBD |
| Cinebench multi-core | TBD |
| 7-Zip total rating | TBD |
| SSD sequential read | TBD |
| SSD sequential write | TBD |
| iperf3 transmit | TBD |
| iperf3 receive | TBD |
