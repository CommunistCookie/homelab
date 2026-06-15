# homelab
Home network lab featuring NAS, VPN, DNS filtering, and IP surveillance

# Home Network & Security Lab

A personal homelab built around a QNAP NAS as the central node, with network-level ad blocking, VPN remote access, IP surveillance with overflow storage, and a secondary laptop-based NAS running Ubuntu Server.

---

## Hardware

| Device | Model | Role |
|---|---|---|
| NAS | QNAP TS-212 | Core storage and services hub |
| Laptop NAS | Ubuntu Server 24.04.3 LTS | Secondary NAS, connected to QNAP for extended storage |
| Switch | D-Link DES-10160 | Network switching and segmentation |
| NVR | UNV NVR301-16S3 | IP camera recording and management |
| PoE Switch | SecureEye PoE Switch | Powers and connects IP cameras |
| IP Camera | UNV IPC322LB-SF28-A | Fixed surveillance camera |

---

## Software & Services

### Pi-hole
Running on the QNAP NAS as a DNS sinkhole, blocking ads and trackers at the network level before they reach any device. Also configured optionally as a DHCP server to manage IP assignments across the network.

### WireGuard VPN
Set up for secure remote access from anywhere. Allows full tunnel access into the home network without exposing any services directly to the internet.

### Jellyfin and Plex
Both media servers are running off the QNAP NAS for local and remote streaming of the media library.

### KasaOS
Installed as a friendlier management UI on top of the QNAP NAS, making day-to-day administration easier without always dropping into the command line.

---

## Network Layout

```
Internet
   |
Router
   |
D-Link DES-10160 Switch
   |
   +--- QNAP TS-212 NAS (Pi-hole, WireGuard, Jellyfin, Plex, KasaOS)
   |
   +--- Laptop NAS (Ubuntu Server 24.04.3 LTS) --> linked to QNAP for shared file access
   |
   +--- SecureEye PoE Switch
           |
           +--- UNV IPC322LB-SF28-A Camera(s)
           |
           +--- UNV NVR301-16S3 --> overflow storage to QNAP NAS
```

---

## Surveillance Storage Overflow

The UNV NVR handles local recording from the camera feed. Once its local storage fills up, recorded and playback footage automatically transfers over to the QNAP NAS. This gives the system effectively unlimited local storage for video retention without needing a cloud subscription.

---

## Laptop NAS

A spare laptop running Ubuntu Server 24.04.3 LTS was set up as a secondary NAS and connected to the QNAP unit. This extends available storage and allows both devices to be accessed from the same network share, making file access straightforward from any device on the network.

---

## Skills Demonstrated

- NAS deployment and administration (QNAP TS-212)
- DNS-level network filtering with Pi-hole
- VPN configuration and remote access with WireGuard
- IP surveillance setup including NVR, PoE switching, and camera configuration
- Automated storage overflow from NVR to NAS
- Ubuntu Server setup and NAS integration
- Network switching and device configuration (D-Link)
- Running and managing self-hosted services (Jellyfin, Plex)
