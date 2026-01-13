# SRT Gateway Architecture (OnPremise SRT Server)

This document describes the typical architecture of an on-premise SRT gateway used in IPTV headends and broadcast environments.

---

## High-level architecture

OnPremise SRT Server by StreamRus sits between contribution networks and distribution networks, acting as a controlled demarcation point.

Remote Encoders
|
SRT
|
+----------------------+
| OnPremise SRT Server |
+----------------------+
|
UDP / SRT
|
IPTV Headend / Remote Sites


---

## Contribution side

- Incoming SRT streams from encoders, OB vans, studios or remote locations
- Encrypted and authenticated transport
- Internet or private IP connectivity

---

## Processing layer

- Stream replication (one-to-many)
- Network interface selection
- Routing based on operator configuration
- Monitoring and operational control

---

## Distribution side

- UDP unicast or multicast for local headends
- SRT outputs for WAN or Internet distribution
- Separation of output paths per destination

---

## Multi-NIC and VLAN deployments

OnPremise SRT Server supports:
- Multiple physical network interfaces
- VLAN-based traffic segregation
- Independent routing for input and output flows

This is especially important in broadcast headends where contribution, management and distribution networks must remain isolated.

---

## Operational characteristics

- Designed for continuous 24/7 operation
- Predictable latency behaviour
- Integration with existing broadcast monitoring tools

---

## Related documentation
- [IPTV headend use cases](use-cases-iptv-headend.md)
- [On-premise vs cloud SRT](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)
