Network Infrastructure and Segmentation

Designed and implemented a segmented home network using a custom router, managed switch, and wireless access points.

Key Features:
+ Configured VLANs for network segmentation:
  - Main network
  - Server network
  - Wi-Fi network
+ Implemented VLAN tagging across network devices
+ Applied ACLs to control inter-VLAN communication
+ Improved network security and isolation

Skills Demonstrated:
+ Network design and architecture
+ VLAN configuration and tagging
+ Access Control Lists (ACLs)
+ Router and switch configuration

## Overview

> Note: This diagram is a simplified representation of the home lab network. Sensitive details such as public IPs, domain names, and access configurations are intentionally omitted for security.

```mermaid
flowchart TD

%% =========================
%% Internet & Modem
A[Internet] --> B[ISP Modem]
B --> C[Router]

%% Router Ports
C --> R2[Port 2 - LAN Trunk to Switch]
C --> R3[Port 3 - AP VLAN 30]
C --> R4[Port 4 - Unused]
C --> R5[Port 5 - Unused]

%% Switch
R2 --> S1[Managed Switch]

%% Switch Ports
S1 --> S2[Port 2 - VLAN 10 Main PC]
S1 --> S3[Port 3 - VLAN 20 Pi-hole]
S1 --> S4[Port 4 - VLAN 20 NAS]
S1 --> S5[Port 5 - VLAN 20 Proxmox]

%% VLANs (Sanitized)
S2 --> V1[VLAN 10 - Main\n192.168.10.0/XX]
S3 --> V2[VLAN 20 - Servers\n192.168.20.0/XX]
S4 --> V2
S5 --> V2
R3 --> V3[VLAN 30 - WiFi\n192.168.30.0/XX]

%% WiFi VLAN Components
V3 --> AP[Access Point]
V3 --> WC[WiFi Clients]

%% Proxmox VMs
S5 --> PX[Proxmox Host]
PX --> VM1[NGINX Reverse Proxy]
PX --> VM2[Game Server]
PX --> VM3[Docker - Zammad]

%% Core Services
V2 --> DNS[Pi-hole DNS]
V2 --> NAS[NAS Storage]

%% VPN for Remote Access
EXT[Remote User] --> VPN[WireGuard VPN]
VPN --> C

%% =========================
%% Inter-VLAN Rules (Sanitized)
%% =========================
V1 -->|Allowed| V2
V1 -->|Allowed| V3

V3 -->|Allowed| V2
V3 -.->|Blocked| V1

V2 -.->|Blocked| V1
V2 -.->|Blocked| V3

%% Servers -> Internet
V2 -->|Allowed| A
```
