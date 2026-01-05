# Features (high level)

## Inputs (examples)

- RTMP/RTMPS pull
- RTSP pull
- HTTP pull
- HLS
- DASH
- UDP

## Outputs (examples)

- UDP (unicast/multicast)
- SRT (caller/listener/rendezvous)
- RTMP/RTMPS (e.g., YouTube)

## Transport

- UDP and SRT keep original Transport Streams as-is (no extra modification added).
- UDP and SRT are codec/resolution agnostic (can transport MPEG-2, etc.).

## Operations

- Real-time status visibility for your TV/Radio network.
- Editable elements, reassignment of outputs to other sources.
- Backup/restore of configuration to/from a file.
- One-click updates.

## Network / system

- DDNS support (DynDNS / No-IP)
- IPv4 and IPv6 dual stack
- mDNS (Bonjour) device discovery
- UPnP (router dependent)

## Users / API

- Admin and user roles
- REST API documented in Swagger 2.0
