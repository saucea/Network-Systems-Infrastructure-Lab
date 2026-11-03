# Troubleshooting Log

Real problems I hit while building and running this lab. Troubleshooting is the core of IT support, so I document how I diagnosed each one and what I took away from it.

## My Troubleshooting Toolkit

`ping` to check reachability, `nslookup` to check DNS, `tracert` to find where traffic stops, and reviewing firewall rules in order.

## Entries

### 1. VLANs not working or misconfigured
- **Symptom:** Devices on new VLANs had no connectivity or ended up on the wrong network.
- **Approach:** Rechecked VLAN assignments on ports and networks, then tested with `ping` from each VLAN.
- **Lesson:** Build and test one VLAN at a time.
- > **TODO:** Add the specific root cause for one example.

### 2. Gateway setup needed several resets
- **Symptom:** The new gateway had configuration problems that I could not undo cleanly.
- **Action:** Reset and reconfigured the gateway several times.
- **Lesson:** Export a backup of a known-good config before big changes.

### 3. Trunk port between UniFi and Netgear
- **Symptom:** Trunking between two different brands did not work, and I lost access to a switch.
- **Action:** Reset the switches and reconfigured the trunk with matching VLAN settings on both sides.
- **Lesson:** Different vendors use different terminology for tagged and untagged VLANs, so check both ends.

### 4. Camera stuck on "provisioning"
- **Symptom:** The camera never finished setup.
- **Action:** Troubleshot and re-set it up.
- > **TODO:** Add the actual cause and fix (VLAN, firewall, DHCP, firmware?).

### 5. DNS not working or sites blocked by accident
- **Symptom:** Websites failed to load, or devices could not resolve names.
- **Causes:** DNS not correctly set in DHCP, and blocklists blocking legitimate sites.
- **Approach:** Tested with `nslookup`, confirmed which DNS server clients were using, and checked what Pi-hole was blocking.
- **Lesson:** When "the internet is down," check DNS first.

### 6. Devices not showing up
- **Approach:** `ping` to test reachability, `nslookup` for name resolution, `tracert` to see where traffic stopped, then firewall rules.

### 7. VPN connected but could not reach some resources
- **Symptom:** The WireGuard tunnel was up, but some services were unreachable.
- **Approach:** Went through firewall rules to find what was blocking traffic.
- **Outcome:** I later moved to Tailscale to avoid opening ports (see [Remote Access](../remote-access/)).

### 8. Firmware update without a backup (in progress)
- **Symptom:** After a firmware update on the MacBook Pro Proxmox host, Ethernet stopped working.
- **Status:** Still troubleshooting.
- **Lesson:** Always back up before firmware or major updates. This is the reason I now take backups first.

### 9. Patching and backups across all servers
- **Challenge:** Keeping every server updated with security patches while protecting against data loss.
- **Practice:** Back up first, then update.
- > **TODO:** Describe your current routine (how often, what tool).
