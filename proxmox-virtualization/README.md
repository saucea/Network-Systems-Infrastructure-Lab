# Virtualization with Proxmox

Two headless servers run Proxmox as the hypervisor: a MacBook Pro and a Dell.

| Host | What it runs |
|---|---|
| MacBook Pro | Game servers (e.g. Minecraft) |
| Dell | Active Directory lab, NGINX reverse proxy, Prometheus + Grafana monitoring |

## Skills

- Creating and managing VMs and resource allocation
- Keeping hosts and VMs patched and backed up
- Running services in isolated VMs

## Lessons

I updated firmware on the MacBook without taking a backup first, and its Ethernet stopped working afterward. I'm still troubleshooting it. Since then I back up before any firmware or major update. Details in the [Troubleshooting Log](../troubleshooting-log/).

> **TODO:** Add VM specs table (name, OS, CPU, RAM) and a Proxmox dashboard screenshot.
