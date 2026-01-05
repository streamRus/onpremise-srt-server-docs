# Troubleshooting

This page lists common causes when a stream does not connect, drops, or does not appear on the receiver side.

## 1) SRT does not connect (caller/listener)

Checklist:
- Confirm the correct mode on both ends (caller vs listener).
- Confirm the correct IP/port:
  - caller must dial the listener IP:port
- Confirm UDP reachability:
  - firewall rules allow UDP
  - NAT/port-forward is configured (for inbound listener ports)
- Avoid port conflicts:
  - one SRT session uses one UDP port

Quick test:
- Try a different UDP port temporarily to rule out port conflicts.

## 2) SRT connects but stream is unstable

Common causes:
- Packet loss or jitter on the path
- Too aggressive latency/buffer settings

What to do (high level):
- Increase buffer/latency settings to improve resilience (at the cost of latency).
- Check link quality and congestion.
- Verify total bitrate vs available bandwidth.

## 3) UDP multicast not received on the LAN

Checklist:
- Confirm IGMP/multicast support in the switch/router.
- Confirm receivers are joining the group.
- Confirm the multicast group/port is correct.
- In multi-NIC systems, force the correct interface:

`LOCAL_INTERFACE_IP@MULTICAST_GROUP_IP`

Example:
`10.10.134.150@239.2.2.2`

## 4) Works locally but not from the Internet (NAT)

Checklist:
- Public IP really belongs to your router (no CGNAT).
- UDP port range forwarded to the device.
- ISP/router is not blocking inbound UDP.
- If public inbound is not possible, consider rendezvous setups (depending on your topology).

## 5) Licensing issues

Symptoms:
- Channels run only a few minutes
- New channels cannot start

Checklist:
- DNS configured correctly in Network settings.
- Device has Internet connectivity to reach the licensing server.
- The system has not been offline for too long.
