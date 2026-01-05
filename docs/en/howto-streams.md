# HOWTO: Streams (basic workflow)

This page explains the core workflow used in OnPremise SRT Server.

## Concept

- Create an **INPUT** (where the stream comes from).
- Create one or more **OUTPUTs** (where the stream must go).
- Link OUTPUT(s) to the INPUT to replicate the stream.

## One-to-one

- 1 INPUT → 1 OUTPUT

Typical when you need a single destination (e.g., a decoder or a remote receiver).

## One-to-many (replication)

- 1 INPUT → multiple OUTPUTs

Typical when you need:
- main + backup destinations
- multiple affiliates
- SRT for remote + UDP multicast for headend

## Operational tips

- Plan your UDP port ranges (especially for SRT Listener).
- Keep naming consistent:
  - `CH01_MAIN_IN`, `CH01_OUT_MCAST`, `CH01_OUT_SRT_BKP`, etc.
- Validate each leg independently:
  - INPUT connected/receiving
  - OUTPUT sending
  - receiver side decoding/joining multicast
