# DNS with Pi-hole

Pi-hole runs on a Raspberry Pi and serves as the DNS server for the whole network.

## What It Does

- Provides DNS for all VLANs, handed out through DHCP on the gateway
- Blocks ads and trackers using configured blocklists
- Runs local DNS records so I can use names instead of IP addresses
- Maps custom local domains to my NGINX reverse proxy so internal services work over HTTPS (see [NGINX Reverse Proxy](../nginx-reverse-proxy/))
- Guest and IoT VLANs are isolated from everything else but are allowed to reach Pi-hole for DNS

## Common Issues I Troubleshoot

- DNS not resolving because DHCP was not handing out the Pi-hole address correctly
- Legitimate websites getting blocked by a blocklist
- Devices not resolving local names

Tools: `nslookup`, `ping`, Pi-hole's web interface. More detail is in the [Troubleshooting Log](../troubleshooting-log/).

> **TODO:** Add a screenshot of the Pi-hole dashboard and a (redacted) local DNS records page.
