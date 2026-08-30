# DualStack-Enterprise-Network

Networking project created in Cisco Packet Tracer. Made by Mateusz Wołkowicz.

# Implemented Features

* IPv4 and IPv6 addressing
* LACP, HSRP redundancy
* Segmented network and dedicated VLANs for VoIP, management, native
* DHCPv4 and stateful DHCPv6 servers
* Dynamic OSPFv2 and OSPFv3 routing
* WLAN with multiple WLC-based access points

# Addressing Scheme

## IPv4

**192.168.1.0/26 VLAN 10** *(corporate)*
* 192.168.1.1 Virtual Gateway
* 192.168.1.2 Core1
* 192.168.1.3 Core2
* [DHCP] Worker1
* [DHCP] Worker2

**192.168.1.64/26 VLAN 20** *(voice)*
* 192.168.1.65 Virtual Gateway
* 192.168.1.66 Core1
* 192.168.1.67 Core2

**192.168.1.128/27 VLAN 30** *(guests)*
* 192.168.1.129 Virtual Gateway
* 192.168.1.130 Core1
* 192.168.1.131 Core2
* [DHCP] GuestPC

**192.168.1.160/28 VLAN 99** *(management)*
* 192.168.1.161 Core1
* 192.168.1.162 Core2
* 192.168.1.165 Virtual Gateway
* 192.168.1.166 S1
* 192.168.1.167 S2
* 192.168.1.168 WLC

**VLAN 100** *(native):* no addressing

**192.168.1.176/30 Net Core1-R1**
* 192.168.1.177 R1
* 192.168.1.178 Core1

**192.168.1.180/30 Net Core2-R2**
* 192.168.1.181 R2
* 192.168.1.182 Core2

**192.168.1.184/30 Net R1-R2**
* 192.168.1.185 R1
* 192.168.1.186 R2

**192.168.1.188/30 Net R1-ISP**
* 192.168.1.189 R1
* 192.168.1.190 ISP

**192.168.1.192/30 Net R2-ISP**
* 192.168.1.193 R2
* 192.168.1.194 ISP

## IPv6

# Note

Some features are missing due to limitations of Cisco Packet Tracer, however everything that is possible is configured properly:
* DHCPv6 server is configured but not in use, as CPT does not support Relay Agents
* random issues may occur that will fix after restarting Cisco Packet Tracer
