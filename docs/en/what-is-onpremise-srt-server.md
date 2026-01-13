# What is OnPremise SRT Server (by StreamRus)?

OnPremise SRT Server by StreamRus is an on-premise IP video gateway for broadcast contribution and distribution.  
It receives and replicates professional video streams using SRT and other IP protocols, and it is designed for IPTV headends, TV studios, and operators who need deterministic 24/7 operation.

---

## Who it is for
- IPTV / cable headends
- TV studios and production facilities
- Broadcast integrators and operators

---

## Supported protocols (typical)
- Inputs: SRT, UDP (unicast/multicast), RTMP, RTSP, HLS, HTTP
- Outputs: SRT, UDP (unicast/multicast), RTMP

---

## Typical workflows
- SRT contribution → UDP/RTP (unicast or multicast) inside the headend
- One input → multiple outputs (point-to-multipoint distribution)
- Multi-NIC / VLAN separation between contribution and distribution networks

---

## Key features (high level)
- Multi-input / multi-output gateway (operator workflows)
- Multi-network setups (multiple NICs / VLAN)
- Monitoring and operational control
- REST API (external integration)

---

## Related documentation
- [SRT gateway architecture](srt-gateway-architecture.md)
- [IPTV headend use cases](use-cases-iptv-headend.md)
- [On-premise vs cloud SRT](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)

Official website: https://streamrus.com/
