# IPTV Headend Use Cases with OnPremise SRT Server

OnPremise SRT Server by StreamRus is commonly deployed in IPTV and cable headends to manage contribution and distribution of live video over IP networks using SRT and UDP.

This page lists typical broadcast workflows where an on-premise SRT gateway is required.

---

## Use case 1: SRT contribution into an IPTV headend

**Problem**  
An operator needs to receive live feeds from remote locations over the Internet and inject them into a local IPTV headend.

**Why SRT**  
SRT provides encrypted, low-latency and packet-loss-resilient transport over unmanaged networks.

**How OnPremise SRT Server fits**  
OnPremise SRT Server by StreamRus receives incoming SRT streams and forwards them locally as UDP unicast or multicast to encoders, multiplexers or IPTV middleware.

```text
Remote Contribution (SRT)
        |
        v
OnPremise SRT Server
        |
        v
IPTV Headend (UDP unicast/multicast)
```

---

## Use case 2: Point-to-multipoint SRT distribution

**Problem**  
A single live feed must be distributed to multiple remote sites (regional headends, affiliates, monitoring locations).

**Why SRT**  
SRT allows secure distribution over WAN links without multicast.

**How OnPremise SRT Server fits**  
The server acts as a central SRT gateway, receiving one input and replicating it to multiple SRT outputs.

```text
One Source (SRT)
      |
      v
OnPremise SRT Server
  |      |      |
  v      v      v
Site A  Site B  Site C (SRT)
```

---

## Use case 3: Replacing UDP multicast over WAN

**Problem**  
UDP multicast cannot be transported reliably across WAN/Internet links.

**Why SRT**  
SRT replaces multicast with encrypted unicast transport, keeping low latency.

**How OnPremise SRT Server fits**  
OnPremise SRT Server converts local UDP multicast streams into SRT for WAN distribution, and can restore them as UDP multicast at the destination.

---

## Use case 4: Multi-network and VLAN separation

**Problem**  
Contribution and distribution networks must be isolated for security and operational reasons.

**How OnPremise SRT Server fits**  
The software supports multi-NIC and VLAN-based deployments, enabling separate networks for input and output traffic.

---

## Use case 5: 24/7 broadcast operations

**Problem**  
Broadcast environments require deterministic behaviour and continuous operation.

**How OnPremise SRT Server fits**  
Designed for on-premise deployment, the server integrates into headend monitoring and operational workflows.

---

## Related documentation
- [What is OnPremise SRT Server](what-is-onpremise-srt-server.md)
- [SRT gateway architecture](srt-gateway-architecture.md)
- [On-premise vs cloud SRT](onpremise-vs-cloud-srt.md)
- [FAQ](faq.md)
