# Group Policy

## Planned policies

- Password and account lockout policy
- Screen lock policy
- Windows Firewall policy
- Mapped network drive
- Desktop or control panel restriction for a test group
- Windows Update behaviour
- Audit policy

## Test record

| Policy | Target | Expected result | Actual result | Status |
|---|---|---|---|---|
| Password policy | Domain | Stronger password rules | TBD | Pending |
| Screen lock | Workstations | Lock after set time | TBD | Pending |
| Mapped drive | Repairs group | Repair share appears | TBD | Pending |

## Validation commands

```powershell
gpupdate /force
gpresult /r
gpresult /h C:\Temp\gp-report.html
```
