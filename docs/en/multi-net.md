# Multi-network installation (multi-NIC)

This guide explains how to install and configure OnPremise SRT Server in an environment with multiple physical network interfaces, connected to different LANs or VLANs (untagged).

## Installation

Before installing the ISO image, connect the LAN that has Internet access to **LAN1** of the target machine.

If you don’t know which port is LAN1, connect one at random. During installation, the system will indicate whether it can configure it via DHCP. If not, connect another port and request automatic configuration again until you find the correct one.

## Network configuration

In the web panel, open the **Network** tab and click **LAN/WLAN Interfaces**.

If the page appears empty, switch to another tab and back again. The network configuration should load.

You will see **LAN1** connected and configured by DHCP. The rest of interfaces will be empty (no IP assigned).

For each additional interface, you only need to assign:
- IP address
- Netmask

You **do not** need to assign gateways for LAN2 and above.

Example IPs:
- `192.168.100.44/24`
- `192.168.110.44/24`
- `192.168.120.44/24`

Set the IPs and press **Save** on each interface.

Then go to **System** and press **Reboot** to restart with the multi-network configuration.

After reboot, you can connect LAN2 and above to their respective subnets.

## Interface assignment for streams

Any INPUT or OUTPUT created in the **Streams** tab can be assigned to receive/send packets only through one of the available interfaces.

However, this is strictly necessary only for **UDP multicast**. Other protocols use unicast addresses, so routing rules determine which interface is used without needing to specify it.

If you do not assign the interface for UDP multicast, the system will listen/send on all available interfaces.

To force the interface in UDP multicast, use this format in the protocol **Address** field:

`LOCAL_LAN_IP@MULTICAST_GROUP_IP`

Example:
If you want to send multicast to `238.0.0.5` using LAN2 with IP `192.168.100.40`, then:

`192.168.100.40@238.0.0.5`
