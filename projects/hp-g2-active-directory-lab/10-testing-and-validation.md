# Testing and Validation

## Functional tests

- [ ] Client obtains correct network settings
- [ ] Client resolves domain DNS records
- [ ] Client joins domain
- [ ] Domain user can sign in
- [ ] Group Policy applies
- [ ] Authorised user can access permitted share
- [ ] Unauthorised user is denied
- [ ] PowerShell script completes successfully
- [ ] Backup completes
- [ ] Restore succeeds

## Useful commands

```powershell
ipconfig /all
nslookup ad.coppercode.test
Test-NetConnection CC-DC01 -Port 53
whoami
gpresult /r
```

```powershell
dcdiag
Get-ADDomain
Get-ADForest
Get-ADUser -Filter *
```

## Final acceptance

Document the evidence, unexpected behaviour and corrective actions for every failed test.
