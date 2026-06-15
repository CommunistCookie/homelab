# Changelog

All notable changes and additions to the homelab setup are documented here.

---

## [Current] - 2025

### Added
- WireGuard VPN configured on QNAP NAS for secure remote access from anywhere
- Pi-hole set up as network-wide DNS sinkhole, blocking ads and trackers across all devices
- Pi-hole optionally configured as DHCP server for centralized IP management
- Jellyfin and Plex both running on QNAP NAS for local and remote media streaming
- KasaOS installed on QNAP for a friendlier management interface
- UNV NVR (NVR301-16S3) connected via SecureEye PoE switch with UNV IPC322LB-SF28-A camera
- NVR to NAS storage overflow configured so footage automatically archives to QNAP when NVR storage fills
- Laptop NAS set up running Ubuntu Server 24.04.3 LTS, mounted and connected to QNAP NAS for unified file access
- D-Link DES-10160 switch configured for network switching and device segmentation

---

## [Initial Setup]

### Added
- QNAP TS-212 deployed as the core NAS and services hub
- Basic network setup with router, switch, and NAS connectivity
- Shared folders created on QNAP for general file storage and access

---

## Planned / In Progress

- Proper network diagram using draw.io
- VLAN segmentation to isolate IoT and surveillance devices from main network
- Centralized logging with a syslog server or lightweight SIEM
- Automated NAS backup to an offsite or secondary location
- Exploring Grafana and Prometheus for network monitoring dashboards
