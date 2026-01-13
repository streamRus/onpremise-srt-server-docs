# IPTV Headend Use Cases with OnPremise SRT Server

OnPremise SRT Server by StreamRus is commonly deployed in IPTV and cable headends to manage contribution and distribution of live video over IP networks using SRT and UDP.

This page describes typical real-world broadcast workflows.

---

## Use case 1: SRT contribution into an IPTV headend

**Problem**  
An operator needs to receive live feeds from remote locations over the Internet and inject them into a local IPTV headend.

**Why SRT**  
SRT provides encrypted, low-latency and packet-loss-resilient transport over unmanaged networks.

**How OnPremise SRT Server fits**  
OnPremise SRT Server by StreamRus receives incoming SRT streams and forwards them locally as UDP unicast or multicast to encoders, multiplexers or IPTV middleware.

---

## Use case 2: Point-to-multipoint SRT distribution

**Problem**  
A single live feed must be distributed to multiple remote sites (regional headends, affiliates, monitoring locations).

**Why SRT**  
SRT allows secure one-to-many distribution without multicast support in WAN networks.

**How OnPremise SRT Server fits**  
The server acts as a central SRT gateway, receiving one input and replicating it to multiple SRT outputs with independent network paths.

---

## Use case 3: Replacing UDP multicast over WAN

**Problem**  
UDP multicast cannot be routed reliably over WAN or Internet links.

**Why SRT**  
SRT replaces multicast with unicast encrypted transport, preserving low latency.

**How OnPremise SRT Server fits**  
OnPremise SRT Server converts local UDP multicast streams into SRT for WAN transport, then restores them as UDP multicast at the destination.

---

## Use case 4: Multi-network and VLAN separation

**Problem**  
Contribution and distribution networks must be isolated for security and operational reasons.

**How OnPremise SRT Server fits**  
The software supports multi-NIC and VLAN-based deployments, allowing separate physical or logical networks for input and output traffic.

---

## Use case 5: 24/7 broadcast operations

**Problem**  
Broadcast environments require deterministic behaviour and continuous operation.

**How OnPremise SRT Server fits**  
Designed for on-premise deployment, the server integrates into traditional headend monitoring and operational workflows.

---

## Related documentation
- [What is OnPremise SRT Server](what-is-onpremise-srt-server.md)
- [SRT gateway architecture](srt-gateway-architecture.md)
- [On-premise vs cloud SRT](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)
