# UDP multicast (unicast / multicast)

UDP outputs are commonly used for LAN distribution and headends.

## Unicast vs multicast

- **Unicast**: one destination IP per receiver.
- **Multicast**: one multicast group IP for many receivers on the same LAN (requires IGMP-aware network).

## Binding multicast to a specific NIC

In multi-NIC deployments (e.g., Internet on LAN1, headend on LAN2), you often need to force multicast traffic out of a specific interface.

Use the format:

`LOCAL_INTERFACE_IP@MULTICAST_GROUP_IP`

Example:

`10.10.134.150@239.2.2.2`

Then set the UDP port normally (e.g., `:5000` depending on the UI field layout).

## Notes for headends

- Ensure the LAN switch/router supports multicast and IGMP.
- Keep multicast distribution inside the LAN (not across the public Internet).
- Validate on a receiver/IRD that joins the group.
