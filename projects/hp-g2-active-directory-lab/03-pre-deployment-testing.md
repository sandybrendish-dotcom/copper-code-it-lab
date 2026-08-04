# Pre-deployment Testing

## Test standard

The system must pass all essential tests before Proxmox is installed.

| Test | Tool | Duration | Result | Evidence |
|---|---|---:|---|---|
| Memory | MemTest86 | 4 passes | Passed | Add sanitised screenshot |
| CPU stability | OCCT | 60 minutes | Passed | Add result |
| Combined load | OCCT Power | 15-20 minutes | Pending | Add result |
| Storage SMART | CrystalDiskInfo | Inspection | Passed | 71% Good |
| Storage performance | CrystalDiskMark | One run | Passed | 478.85MB/s Read, 138.12MB/s Write |
| Network throughput | iperf3 | Both directions | Passed | 945 Mbits/sec sender, 949 Mbet/sec receiver |
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
| Cinebench single-core | 388pts |
| Cinebench multi-core | 832pts |
| 7-Zip total rating | TBD |
| SSD sequential read | 478.85MB/s |
| SSD sequential write | 138.12MB/s |
| iperf3 transmit | 945 Mbits/sec |
| iperf3 receive | 949 Mbits/sec |
