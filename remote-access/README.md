# Remote Access with Tailscale

## Evolution

1. **WireGuard (original):** I ran a WireGuard VPN server on the home network. It connected, but some resources were not reachable, which meant tracing through firewall rules.
2. **Tailscale (current):** I moved to Tailscale because it does not require opening ports on my network, which reduces the attack surface.

## Current Setup

- The NAS is part of the Tailscale network and is the main remote-access point
- Friends and family can reach shared services like Vaultwarden securely from anywhere
- No inbound ports are opened on the gateway

## Skills

- Choosing a remote-access method based on security tradeoffs
- Troubleshooting connectivity that "connects but can't reach everything"
- Onboarding non-technical users to a secure service

> **TODO:** Add a screenshot of the Tailscale admin machines list (hide names and IPs).
