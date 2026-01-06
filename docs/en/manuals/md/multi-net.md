# Multi-network installation (Full Manual)

> Source PDF: [MULTI-NET_ENG.pdf](../pdf/MULTI-NET_ENG.pdf)

## Page 1

### Multi-Lan Setup

Introduction We will now explain how to install and configure OnPremise SRT Server in an environment with several physical network interfaces, connected to different LANs or VLANs. (untagged).

Installation Before installing the ISO image, it is convenient to connect the LAN network that has Internet access, to the LAN1 of the computer on which we will install. If we do not know which one it is, we

will choose one at random, and during the installation, the system will tell us if it can configure it by DHCP or not. If not, we will have to connect another one, and we will ask again for its automatic

configuration, until we get it. Configuration When entering the Network tab of the OnPremise SRT Server panel, click on LAN/WLAN Interfaces, and if it appears empty, go to any other tab and come back, the network configuration

should be loaded. In it, we will see LAN1 connected and configured by DHCP.

### This is an example

The rest of the interfaces will appear empty, with no IP assigned. We just need to assign an IP and mask to each of them. You don’t need to assign Gateways. To do this, we have to be clear about which IP we are going to assign to each one according to

which LAN or VLAN they are going to connect to.

### In our example we are going to use these IPs

192.168.100.44/24 192.168.110.44/24 192.168.120.44/24


## Page 2

It is as simple as putting the IP addresses in their corresponding places and pressing the Save button to save them. Once all the available LAN interfaces are configured, go to System and click on Reboot to restart

the computer with this multi-lan configuration. We can now connect from LAN2 onwards to their respective subnets.


## Page 3

Interface assignment Any INPUT or OUTPUT that we create in the Streams tab can be assigned to receive or send packets only on one of the available interfaces. However, this is only strictly necessary in UDP

multicast. The rest of the protocols use unicast addresses, so the system knows using the routing table, from where to receive or where to send the stream, with no need to specify it.

In UDP multicast if we do not assign the interface to use, it will be understood that it should listen or send on all the available interfaces. To assign the interface to use, we will do it in the Address

field of the protocol, by putting first the IP of the LAN interface to use, followed by @ and then the IP of the multicast group to connect.

### Example

Let's say we are going to send multicast traffic to 238.0.0.5 using the LAN2 socket that in our example has the IP 192.168.100.40. Address should be 192.168.100.40@ 238.0.0.5 .


## Page 4

Final words In this way, we can get a stream from a LAN through an INPUT and send it to another LAN or other LANs through another/other OUTPUT(s), with no limits. It does not matter from which LAN

an INPUT we get the stream, nor to which LAN an OUTPUT we send it. The operation is just as simple, so that what enters through an INPUT is immediately copied to all its associated OUTPUTs,

as already explained in the HOWTO manual. TodoStreaming 2021
