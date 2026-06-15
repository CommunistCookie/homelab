# Laptop NAS Setup (Ubuntu Server 24.04.3 LTS)

## Overview
A spare laptop repurposed as a secondary NAS running Ubuntu Server 24.04.3 LTS,
connected to the QNAP TS-212 for extended and unified file access across the network.

## OS Setup
- Installed Ubuntu Server 24.04.3 LTS (minimal install, no GUI)
- Disabled sleep and lid-close suspend so the laptop stays on as a server
- Configured static IP for consistent network access

## Samba (SMB) Share
Installed and configured Samba to expose the laptop's storage as a network share,
accessible from Windows, macOS, and Linux devices on the same network.

```bash
sudo apt install samba
sudo nano /etc/samba/smb.conf
```

Example share config added to smb.conf:
```
[laptop-nas]
path = /srv/nas
browseable = yes
read only = no
guest ok = no
valid users = sarthak
```

## Mounting QNAP NAS
The QNAP NAS shared folder is mounted on the laptop for unified file access:

```bash
sudo mount -t cifs //192.168.1.x/shared /mnt/qnap -o username=admin,password=<password>
```

Added to /etc/fstab for auto-mount on boot:
```
//192.168.1.x/shared /mnt/qnap cifs username=admin,password=<password>,iocharset=utf8 0 0
```

## Notes
- Lid close suspend disabled via /etc/systemd/logind.conf (HandleLidSwitch=ignore)
- SSH enabled for headless remote management
- UFW firewall configured to allow only Samba and SSH traffic
