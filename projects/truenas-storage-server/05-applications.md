# Applications

## Jellyfin

### Purpose

Provide local media streaming to computers and televisions.

### Work completed

- Installed Jellyfin
- Configured storage access
- Corrected ACL issues
- Fixed library scanning
- Configured hardware transcoding
- Connected television client
- Added a local DNS hostname
- Added a reverse-proxy host through Nginx Proxy Manager

### Validation

- Libraries visible
- Media playback works
- Hardware transcoding enabled
- Service survives reboot
- Local hostname resolves correctly
- Service loads without a visible application port

## Immich

### Purpose

Provide private photo management and browsing.

### Work completed

- Installed Immich
- Troubleshot PostgreSQL ownership mismatch
- Corrected dataset permissions
- Created an external library
- Confirmed photos indexed progressively
- Monitored server load during ingestion
- Added a local DNS hostname
- Added a reverse-proxy host through Nginx Proxy Manager

### Validation

- Web interface loads
- Photos appear
- External library scans
- Database remains healthy
- Application survives restart
- Local hostname resolves correctly
- Service loads without a visible application port

## AdGuard Home

### Purpose

Provide local DNS filtering, DNS query visibility and readable hostnames for homelab services.

### Work completed

- Installed AdGuard Home on TrueNAS
- Configured DNS service on the local network
- Updated EdgeRouter DHCP to distribute the TrueNAS server as the primary DNS server
- Confirmed client DNS queries appear in AdGuard Home
- Created local DNS rewrites for TrueNAS and application services
- Configured application hostnames using the `home.arpa` domain
- Kept the TrueNAS management hostname resolving directly to the NAS
- Pointed proxied application hostnames to the dedicated reverse-proxy address

### Local DNS records

- `truenas.home.arpa` points directly to the TrueNAS management address
- `jellyfin.home.arpa` points to Nginx Proxy Manager
- `immich.home.arpa` points to Nginx Proxy Manager
- `adguard.home.arpa` points to Nginx Proxy Manager

Exact production IP addresses and management ports are excluded from the public repository.

### Validation

- LAN clients receive the local DNS server through DHCP
- DNS queries appear in the AdGuard Home dashboard
- Local hostnames resolve correctly
- Public internet DNS resolution continues to work
- TrueNAS remains directly accessible if the reverse proxy is unavailable
- AdGuard Home loads through its local hostname

## Nginx Proxy Manager

### Purpose

Provide local reverse-proxy routing so applications can be accessed using readable hostnames without entering application port numbers.

### Work completed

- Installed Nginx Proxy Manager on TrueNAS
- Added a dedicated private LAN address for the reverse proxy
- Kept TrueNAS management on a separate private LAN address
- Bound Nginx Proxy Manager only to the dedicated proxy address
- Configured HTTP and HTTPS proxy ports
- Configured a separate administration port
- Added proxy hosts for Jellyfin, Immich and AdGuard Home
- Enabled WebSocket support for Jellyfin and Immich
- Enabled common exploit blocking
- Updated AdGuard Home DNS rewrites to send application traffic to the proxy
- Kept the TrueNAS management hostname outside the reverse proxy
- Confirmed no public router port forwarding was required
- Excluded the dedicated proxy address from the DHCP allocation range

### Proxy hosts

- `jellyfin.home.arpa` forwards to the Jellyfin application
- `immich.home.arpa` forwards to the Immich application
- `adguard.home.arpa` forwards to the AdGuard Home management interface

Exact production IP addresses and backend ports are excluded from the public repository.

### Reliability decisions

- Nginx Proxy Manager is not bound to `0.0.0.0`
- Ports 80 and 443 are not bound to the TrueNAS management address
- TrueNAS management bypasses the reverse proxy
- Direct backend access remains available for troubleshooting
- The services are not exposed directly to the public internet
- The current deployment uses local HTTP
- The dedicated proxy address is reserved outside the DHCP pool

### Validation

- Jellyfin loads through `jellyfin.home.arpa`
- Immich loads through `immich.home.arpa`
- AdGuard Home loads through `adguard.home.arpa`
- Application URLs work without visible port numbers
- TrueNAS remains directly accessible through its local management hostname
- Nginx Proxy Manager runs on the dedicated proxy address
- The setup survives application restart

## Tailscale

### Purpose

Provide private remote access to the server.

### Validation

- Server joins tailnet
- Remote connection succeeds
- No direct public port exposure required
