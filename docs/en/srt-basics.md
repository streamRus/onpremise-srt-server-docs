# SRT basics (caller / listener / rendezvous)

SRT can operate in three connection modes:

## Listener
- The receiver (server side) listens on a UDP port.
- The sender connects as a Caller.

Typical:
- Server: `srt://0.0.0.0:PORT?mode=listener`
- Remote: `srt://PUBLIC_IP:PORT?mode=caller`

## Caller
- The device initiates the connection to a remote Listener.
- Used when the destination has a public IP/port reachable.

Typical:
- Device: `srt://REMOTE_IP:PORT?mode=caller`

## Rendezvous
- Both endpoints initiate a connection to each other.
- Useful in some NAT scenarios when direct inbound is hard.

Typical:
- Both sides use `mode=rendezvous` and the same port mapping rules.

---

## Ports (important)

- **One SRT session uses one UDP port.**
- If you need many simultaneous SRT streams, you must plan a UDP port range.
- For inbound SRT over the Internet:
  - Forward the chosen UDP port(s)/range to the device IP.
  - Avoid overlap with other services.

---

## Reliability vs latency (high level)

SRT can handle packet loss/jitter using buffers and retransmission.
Trade-off:
- Larger buffers = more resilience, more latency.
- Smaller buffers = less latency, less tolerance to loss/jitter.
