# On-Premise vs Cloud SRT Gateways

Broadcast and IPTV workflows often require an SRT gateway. The key decision is whether to deploy it on-premise or in the cloud.

This page compares both approaches.

---

## On-premise SRT gateway

**What it means**  
The SRT gateway runs on local hardware inside the operator or broadcaster infrastructure.

**Typical advantages**
- Predictable latency
- Full control of networking and routing
- No recurring cloud traffic costs
- Easier integration with IPTV headends (local multicast/unicast)
- Security policies fully controlled on-site

**Typical limitations**
- Requires local hardware
- Requires internal operations/maintenance

---

## Cloud SRT gateway

**What it means**  
The gateway is hosted by a third-party cloud provider and accessed over the Internet.

**Typical advantages**
- Fast initial deployment
- No local hardware required
- Useful for temporary events

**Typical limitations**
- Recurring bandwidth costs
- Extra latency due to cloud routing
- Less control over network paths and policies
- Can be less suitable for large-scale IPTV distribution

---

## When on-premise is usually preferred

- IPTV/cable headends distributing many channels
- Environments where deterministic latency is critical
- Operators who must control traffic costs and routing
- Installations with strict security/network segmentation requirements

---

## Conclusion

OnPremise SRT Server by StreamRus is designed for broadcasters and IPTV operators who need an on-premise SRT gateway with full control over contribution and distribution workflows.

---

## Related documentation
- [What is OnPremise SRT Server](what-is-onpremise-srt-server.md)
- [IPTV headend use cases](use-cases-iptv-headend.md)
- [FAQ](faq.md)
