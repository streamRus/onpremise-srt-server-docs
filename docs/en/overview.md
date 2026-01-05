# Overview

OnPremise SRT Server is an on-premises solution (software + OS image) designed to build and operate professional broadcast/IPTV contribution and distribution workflows.

It is operated from a web interface on the local network and is intended to run on physical x64 hardware.

## Core concept

- Create **INPUTs** (sources): SRT/UDP/pull-based sources.
- Create **OUTPUTs** (destinations): SRT/UDP (unicast/multicast) and related gateway workflows.
- Link OUTPUTs to INPUTs to replicate streams (one-to-one or one-to-many).
- Monitor status and activity from the web panel.

## Typical use cases

- Contribution over the public Internet using **SRT**.
- Distribution inside a LAN using **UDP multicast / RTP over UDP** for headends.
- Point-to-point and point-to-multipoint relay.
- Multi-network deployments with multiple NICs (separate Internet + multicast networks).

## What this repo contains

Documentation, FAQs and practical notes only. The software itself is proprietary and distributed separately.
