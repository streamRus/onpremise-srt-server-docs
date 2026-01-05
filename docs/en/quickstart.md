# Quickstart

This is a practical first-boot checklist to get a basic SRT ↔ UDP workflow running.

## 1) Find the device on the LAN

- Discover the IP address via **mDNS/Bonjour** on the local network.
- Open the web panel in your browser.

## 2) First login

- Log in to the web UI.
- Change default passwords after first access.

## 3) Network configuration

Recommended:
- Set a **static IP** outside the DHCP pool.
- Configure at least one **DNS server** (required for licensing refresh).
- If you have multiple NICs, keep Internet access on one interface and use others for dedicated LANs (e.g., multicast/headend).

## 4) SRT ports and NAT (if receiving from the Internet)

If you will receive SRT from remote sites over the public Internet:
- Choose a **UDP port range** for SRT listener connections (example: 5000–7000).
- Forward that UDP range on your router/firewall to the device IP.
- Ensure your public IP is reachable and not blocked by the ISP.

## 5) Create your first relay

Typical pattern:
1) Create an **INPUT**:
   - Example: `SRT Listener` (server side)
2) Create an **OUTPUT**:
   - Example: `UDP multicast` (for a headend LAN) or `SRT Caller` (to a remote receiver)
3) Link the OUTPUT to the INPUT and start the flow.

## 6) Quick validation

- Confirm the INPUT shows “connected/receiving”.
- Confirm the OUTPUT shows “running/sending”.
- Validate on the receiver side (decoder, IRD, headend, player) that the stream is present.
