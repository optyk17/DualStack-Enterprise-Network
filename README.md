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

**192.168.2.0/24 Home Network**
* 192.168.2.1 HomeRouter
* 192.168.2.2 HomePC

**10.1.1.0/24 Net ISP-HomeRouter**
* 10.1.1.1 ISP
* 10.1.1.2 HomeRouter

## IPv6 GUA

**2001:DB8:FF1:10::/64 VLAN 10** *(corporate)*
* [Autoconfig] Virtual Gateway
* 2001:DB8:FF1:10::2/64 Core1
* 2001:DB8:FF1:10::3/64 Core2
* [Autoconfig] Worker1
* [Autoconfig] Worker2

**2001:DB8:FF1:20::/64 VLAN 20** *(voice)*
* [Autoconfig] Virtual Gateway
* 2001:DB8:FF1:20::2/64 Core1
* 2001:DB8:FF1:20::3/64 Core2

**2001:DB8:FF1:30::/64 VLAN 30** *(guests)*
* [Autoconfig] Virtual Gateway
* 2001:DB8:FF1:30::2 Core1
* 2001:DB8:FF1:30::3 Core2
* [Autoconfig] GuestPC

**VLAN 100** *(native):* no addressing

**2001:DB8:FF1:102::/64 Net Core1-R1**
* 2001:DB8:FF1:102::1/64 R1
* 2001:DB8:FF1:102::2/64 Core1

**2001:DB8:FF1:101::/64 Net Core2-R2**
* 2001:DB8:FF1:101::1 R2
* 2001:DB8:FF1:101::2 Core2

**2001:DB8:FF1:103::/64 Net R1-R2**
* 2001:DB8:FF1:103::1 R1
* 2001:DB8:FF1:103::2 R2

**2001:DB8:FF1:105::/64 Net R1-ISP**
* 2001:DB8:FF1:105::1 R1
* 2001:DB8:FF1:105::2 ISP

**2001:DB8:FF1:104::/64 Net R2-ISP**
* 2001:DB8:FF1:104::1 R2
* 2001:DB8:FF1:104::2 ISP

**2001:DB8:C:1::/64 Home Network**
* 2001:DB8:C:1::1 HomeRouter
* 2001:DB8:C:1::2 HomePC

**2001:DB8:C:101::/64 Net ISP-HomeRouter**
* 2001:DB8:C:101::1 ISP
* 2001:DB8:C:101::2 HomeRouter

# OSPFv3 router-IDs:

* 0.0.0.1 Core1
* 0.0.0.2 Core2
* 0.0.0.3 R1
* 0.0.0.4 R2
* 0.0.0.5 ISP
* 0.0.0.6 HomeRouter

# Note

Some features are missing due to limitations of Cisco Packet Tracer, however everything that is possible is configured properly:
* DHCPv6 server is configured but not in use, as CPT does not support Relay Agents
* random issues may occur that will fix themselves after restarting Cisco Packet Tracer
