# SMB and Permissions

## Purpose

SMB provides file access for Windows clients.

## Share categories

- personal files;
- shared public files;
- media;
- downloads;
- workstation backups.

## Permission principles

- grant only the access required;
- use groups where practical;
- avoid broad permissions as a troubleshooting shortcut;
- record ownership and ACL changes;
- test from a real client account;
- document the difference between dataset permissions and application permissions.

## Validation checklist

- [ ] Share appears on Windows
- [ ] Authorised user can read
- [ ] Authorised user can write
- [ ] Unauthorised user is denied
- [ ] Permissions survive reboot
- [ ] Mapped drive reconnects
- [ ] Application access remains functional
