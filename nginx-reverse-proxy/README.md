# NGINX Reverse Proxy with Internal HTTPS

An NGINX server routes traffic to my internal services by hostname and serves them over HTTPS.

## How It Works

- Pi-hole's local DNS maps my custom internal hostnames to the NGINX server
- NGINX forwards each hostname to the right service and port
- I own a domain through Cloudflare and obtained TLS certificates for it, so internal services use valid HTTPS
- Services are only reachable locally; nothing is exposed to the internet

## Why

- One clean entry point instead of remembering IPs and ports
- Encrypted connections between my devices and my services
- Hides the internal IP structure from users

> **TODO:** How I obtained the certificates and how renewal works.
