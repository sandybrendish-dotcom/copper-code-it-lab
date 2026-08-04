# Lessons Learned

## Reliability over complexity

A small server becomes more useful when it is understandable and recoverable.

## Permissions require structured troubleshooting

Storage permissions, SMB permissions and application permissions are related but not identical.

## A healthy application is not enough

Applications must also:

- access the correct storage;
- survive reboot;
- produce useful alerts;
- be included in backup planning;
- have a recovery process.

## Monitoring matters during heavy work

Initial indexing and library scans can create sustained load. Temperatures and resource usage should be observed rather than assumed safe.

## Backups must be tested

A completed backup job does not prove that recovery works. Restore tests provide the evidence.

## Future improvements

- complete UPS integration;
- add stronger off-device backups;
- document drive replacement;
- add Home Assistant carefully;
- improve monitoring and automated health reporting;
- maintain a sanitised public architecture diagram.
