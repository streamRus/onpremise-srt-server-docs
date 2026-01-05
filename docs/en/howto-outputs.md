# HOWTO: Outputs

Outputs define where the device sends the stream.

## SRT outputs

Used for contribution/distribution over routed networks (including Internet).

Tips:
- Prefer clear naming: MAIN / BKP
- If sending to multiple broadcasters, replicate with multiple outputs

## UDP outputs (unicast / multicast)

### UDP unicast
- One destination IP per receiver.

### UDP multicast (headends / LAN distribution)
- One multicast group for many receivers on the same LAN.

If you have multiple NICs and need to force the multicast interface, use:

`LOCAL_INTERFACE_IP@MULTICAST_GROUP_IP`

Example:
`10.10.134.150@239.2.2.2`

## RTP over UDP note

Depending on the selected output mode, packaging may be preserved when relaying RTP over UDP workflows.
