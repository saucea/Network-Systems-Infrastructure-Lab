# NAS Storage and Self-Hosted Password Manager

A UGREEN 2-bay NAS with two 4 TB drives in RAID 1 (mirroring), used for central storage and a few Docker services.

## Setup

- RAID 1 across two 4 TB drives so a single drive failure does not lose data
- Docker running on the NAS
- **Vaultwarden** (self-hosted password manager) used by me and a few friends and family members
- Joined to **Tailscale** so users can reach it from outside my network without opening any ports (see [Remote Access](../remote-access/))

## Notes

- RAID 1 protects against a drive failure, not against deletion, corruption, or a bad update. It is not a backup.
- Supporting real users on a service I host has taught me to think about uptime, access, and communication.

> **TODO:** Describe your backup plan for the NAS (what gets backed up, where, and how often).
