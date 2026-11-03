# Network & Systems Infrastructure Lab

A hands-on home lab I built and maintain to develop practical IT support, networking, and systems administration skills. It runs on UniFi networking gear with segmented VLANs, two Proxmox hosts, network-wide DNS, a NAS, monitoring, and an Active Directory lab.

Everything here is documented the way I would document it for a team: what I built, why, what broke, and how I fixed it.

*Last updated: November 2026. Sensitive details (public IPs, domain names, credentials, exact firewall rules) are intentionally left out.*

## Lab at a Glance

| Layer | What I run |
|---|---|
| Networking | UniFi Dream Machine Pro, UniFi Pro Max 16 PoE switch, Netgear GS308EP, UniFi U7 access point, 6 VLANs |
| DNS | Pi-hole on a Raspberry Pi with local DNS records |
| Virtualization | Two headless Proxmox hosts (MacBook Pro and Dell) |
| Services | Active Directory lab, NGINX reverse proxy (HTTPS), Prometheus + Grafana, Minecraft/game servers, Zammad ticketing |
| Storage | UGREEN 2-bay NAS, RAID 1 (2x4 TB), Vaultwarden password manager |
| Remote access | Tailscale (replaced WireGuard) |
| Security | VLAN isolation, firewall rules, RADIUS Wi-Fi authentication, HTTPS internally |

## Projects

| Project | Summary |
|---|---|
| [Network Infrastructure](network-infrastructure/) | UniFi + Netgear rebuild with six VLANs, firewall policy, cross-vendor trunking |
| [DNS with Pi-hole](dns-pihole/) | Network-wide DNS, filtering, and local domain records |
| [NAS Storage](nas-storage/) | RAID 1 NAS hosting a self-hosted password manager |
| [Remote Access](remote-access/) | Moving from WireGuard to Tailscale to avoid opening ports |
| [NGINX Reverse Proxy](nginx-reverse-proxy/) | HTTPS for internal services using a domain I own |
| [Proxmox Virtualization](proxmox-virtualization/) | Two-host virtualization environment |
| [Active Directory Lab](active-directory-lab/) | Windows domain environment for practicing user and device administration |
| [Monitoring](monitoring/) | Prometheus and Grafana |
| [Ticketing System](ticketing-system/) | Self-hosted Zammad for tracking repair jobs |
| [Troubleshooting Log](troubleshooting-log/) | Real problems I hit, how I diagnosed them, and what I learned |
| [Website](sosatronics-website/) | Domain and website for my electronics repair side business (in progress) |

## How This Maps to IT Support Work

| Support skill | Where I practice it |
|---|---|
| Troubleshooting connectivity (ping, nslookup, tracert) | [Troubleshooting Log](troubleshooting-log/) |
| User and device management | [Active Directory Lab](active-directory-lab/) |
| Ticketing and documentation | [Ticketing System](ticketing-system/), this repository |
| Network and Wi-Fi support | [Network Infrastructure](network-infrastructure/), [DNS](dns-pihole/) |
| Backups and patching | [NAS Storage](nas-storage/), [Troubleshooting Log](troubleshooting-log/) |
| Supporting real users | Friends and family use my self-hosted services |
