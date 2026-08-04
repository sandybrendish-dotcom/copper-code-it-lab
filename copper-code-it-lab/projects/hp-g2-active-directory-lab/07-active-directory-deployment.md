# Active Directory Deployment

## Planned domain

Use a lab-only namespace. Do not publish or reuse production credentials.

Example:

```text
ad.coppercode.test
```

## Organisational structure

- Management
- Administration
- Repairs
- Sales
- Workstations
- Servers
- Service Accounts

## Deployment checklist

- [ ] AD DS role installed
- [ ] DNS role installed
- [ ] New forest created
- [ ] Domain controller restarted
- [ ] DNS tested
- [ ] Organisational units created
- [ ] Security groups created
- [ ] Test users created
- [ ] Client joined to domain
- [ ] Domain login tested
- [ ] `dcdiag` reviewed
- [ ] Event logs reviewed

## PowerShell evidence

Save reusable scripts under:

```text
scripts/powershell/
```
