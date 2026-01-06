# SRT → UDP/RTP for Cable Headends (Full Manual)

> Source PDF: [SRT_to_UDP-RTP_for_cable_headends_ENG.pdf](../pdf/SRT_to_UDP-RTP_for_cable_headends_ENG.pdf)

## Page 1

SRT to UDP/RTP for Cable Headends Introduction We will show the typical configuration used by cable operators in their headends to incorporate signals received via SRT through LAN1 over the Internet, and output

them via UDP/RTP multicast through LAN2. The equipment we are using for these tests is a Minisforum GK41 with 2 LAN ports. The Ethernet port closest to the power cable is LAN1, while the

furthest one (next to the HDMI) is LAN2. LAN1 is expected to connect to the Internet gateway, which in this example will have the IP address 192.168.1.1. We will assign LAN1 a static IP of

192.168.1.99/24. For LAN2, since we will connect it to the multicast network via a switch with IGMP snooping and possibly an IGMP querier, we will assign a static IP of

10.10.134.150/24, and no gateway will be necessary. Let’s see how everything is configured in the Network tab. If your network has IPv6 with SLAAC, you may see the AUTO mode, along

with pre-set addresses for address and gateway. On LAN2, even though the placeholder displays the shadowed address 192.168.1.1, it is not being applied. 1


## Page 2

Now, we will configure the SRT Listener input on LAN1, which in our case is the interface enp2s0 with the IP address 192.168.1.99 2


## Page 3

If you want to use caller mode, you will enter the IP of the Internet SRT server to connect to, and the connection will go through LAN1, which has the default gateway. For listener mode, if you leave the Address field blank,

or set it to 0.0.0.0 or ::, SRT will be able to connect through any of the device's LANs. We set the LAN1 IP to ensure that it connects only through that interface.

Now, we will configure the multicast output over UDP/RTP on LAN2. 3


## Page 4

To do this, we will use the multicast address 239.2.2.2:5000 and ensure it only exits through LAN2 with the IP 10.10.134.150. We set the Address to 10.10.134.150@239.2.2.2, and also specify the port and set the UDP type to

multicast. Now the UDP/RTP packets will exit only through LAN2 towards the multicast network. 4


## Page 5

So, is the output in UDP or RTP? The OnPremise SRT server is transparent to the packaging, meaning it does not modify, remove, or create headers. Therefore, if the incoming SRT packets contain

RTP headers, the UDP output will carry the exact same headers. RTP, after all, is simply UDP packets with specific headers for particular networks like MPEG-TS, Barix, Dante, Ravena, etc. OnPremise preserves these headers bit by bit, without

any modification. If you want to create RTP over SRT at the source, you can use OnPremise SRT as the source, with a UDP input that will capture the original RTP headers and package them in SRT for transmission over SRT to the Internet.

5
