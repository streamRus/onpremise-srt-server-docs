# HOWTO: Inputs

Inputs define how the device receives a stream.

## Common patterns

### SRT Listener (recommended for inbound contribution)
- Use a dedicated UDP port per stream.
- If receiving from the public Internet:
  - forward the UDP port (or planned range) to the device

### SRT Caller (when the remote side is listener)
- The device initiates the connection to a reachable remote IP:port.

### UDP input (LAN source)
- Used when a stream is already present in the LAN as UDP unicast/multicast.

## Reliability checklist (SRT)

- Confirm correct mode: caller/listener/rendezvous
- Confirm port reachability (firewall/NAT)
- Balance latency vs resilience using buffers (higher buffer = more latency)
