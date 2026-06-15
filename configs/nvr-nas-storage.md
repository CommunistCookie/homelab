# NVR to NAS Storage Overflow Setup

## Overview
The UNV NVR (NVR301-16S3) is configured to overflow recorded footage to the QNAP TS-212 NAS
once its local storage reaches capacity. This removes the need for a cloud subscription while
giving the system effectively unlimited local video retention.

## Hardware Involved
- NVR: UNV NVR301-16S3
- PoE Switch: SecureEye PoE Switch (powers and connects cameras)
- Camera: UNV IPC322LB-SF28-A
- Storage target: QNAP TS-212 NAS

## How It Works
1. Cameras connect to the SecureEye PoE switch, which powers them and passes video to the NVR
2. NVR records footage locally as normal
3. When local NVR storage fills up, oldest footage is pushed to a shared folder on the QNAP NAS
4. QNAP NAS acts as the long-term storage archive for playback and review

## NAS Share Setup (QNAP side)
- Created a dedicated shared folder: /surveillance
- Enabled SMB/CIFS sharing for NVR access
- Set folder permissions to allow NVR write access only

## Notes
- Keep NVR and NAS on the same VLAN or network segment for best transfer speeds
- Regularly check QNAP storage usage as footage can accumulate quickly
- Consider setting a retention policy (e.g. delete footage older than 30 days) to manage storage
