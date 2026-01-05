# Headend example: SRT in → UDP/RTP multicast out

This is a common cable/IPTV headend workflow:

- **LAN1**: Internet side (SRT contribution coming from remote encoders)
- **LAN2**: Headend/IGMP LAN (UDP/RTP multicast distribution)

## Example network setup

LAN1 (Internet / router):
- Device IP: `192.168.1.99/24`
- Gateway: `192.168.1.1`
- DNS: configured (required for licensing refresh)

LAN2 (Headend / multicast LAN):
- Device IP: `10.10.134.150/24`
- No gateway required (LAN-only)

## Example multicast output

Multicast group:
- `239.2.2.2:5000`

Bind multicast to LAN2:
- `10.10.134.150@239.2.2.2`

## Workflow steps (high level)

1) Create an **INPUT**:
   - `SRT Listener` on a UDP port (within your planned port range)
2) Create an **OUTPUT**:
   - `UDP` with multicast group and port
   - Use `LOCAL_IP@MULTICAST_IP` to force the correct interface
3) Link OUTPUT to INPUT and start

## RTP note

If the incoming stream is **RTP over UDP**, the relay should preserve the packaging (transparent relay behavior) depending on the selected output mode.
