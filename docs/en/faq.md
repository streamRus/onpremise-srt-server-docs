# FAQ

## Is this repository the software?
No. This repository contains documentation only. The software is proprietary and distributed separately.

## Can it run in a virtual machine?
It is intended for physical hardware deployments.

## Is it a transcoder?
No. It is designed as a relay/gateway for contribution and distribution workflows (no re-encoding).

## Can I do point-to-multipoint?
Yes. One INPUT can feed multiple OUTPUTs.

## How do I bind UDP multicast to a specific NIC?
Use:
`LOCAL_INTERFACE_IP@MULTICAST_GROUP_IP`

Example:
`10.10.134.150@239.2.2.2`

## How many simultaneous SRT streams can it handle?
It depends on CPU/network conditions and the total bitrate. Plan port ranges and test with real traffic patterns.

## Do I need DNS/Internet access?
Yes, DNS/Internet connectivity is required for licensing refresh in typical deployments.
