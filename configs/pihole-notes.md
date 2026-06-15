# Pi-hole Configuration Notes

## Setup
Pi-hole is running on the QNAP TS-212 NAS via Docker container.
Acts as the primary DNS server for the entire network, blocking ads and trackers at the DNS level before they reach any device.

## DNS Settings
- Primary DNS: Pi-hole (192.168.x.x) -- set this as DNS on your router
- Upstream DNS: Cloudflare (1.1.1.1) and Google (8.8.8.8) as fallback
- DNSSEC: Enabled

## DHCP (Optional)
Pi-hole is also configured to optionally act as the DHCP server.
To enable, disable DHCP on your router first to avoid conflicts, then enable it in Pi-hole settings.

- DHCP Range: 192.168.1.100 - 192.168.1.200
- Router Gateway: 192.168.1.1
- Local domain: home.lan

## Blocklists Used
- Steven Black Unified Hosts (ads + malware)
- OISD Full List
- Hagezi Multi Pro

## WireGuard Integration
Clients connecting via WireGuard VPN point to Pi-hole as their DNS (10.0.0.2),
so ad blocking and DNS filtering applies even when accessing the network remotely.
