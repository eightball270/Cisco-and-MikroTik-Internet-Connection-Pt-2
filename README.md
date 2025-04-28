# Cisco and MikroTik Internet Connection Pt.2
This simulation is a modification of the [previous one](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection/?tab=readme-ov-file#cisco-and-mikrotik-internet-connection), where two routers are used. Some clients are still connected to the internet, even though the router directly connected to the client is not directly connected to the ISP.

This simulation also demonstrates how to restrict certain clients from connecting to the internet based on their network addresses using traffic filters.

## Technology Used
- GNS3

## Requirements
1. 2 routers and a switch
2. Client PCs
3. NAT cloud as ISP

## Configuration Completed
1. DHCP client on the main router interface that connects to the ISP
2. Inter-router connection
3. VLANs on client router and switch
4. NAT configuration on the main router and client router
5. Traffic filter on the router
6. DHCP server on the main router
7. DHCP relay on the client router

## Internet Connection Pt.2

### Cisco
Unlike the [previous configuration](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection/blob/main/README.md#cisco) where all clients have internet access, the ACL on the Cisco router is now configured to prevent the network address 192.168.170.128/25 (VLAN 20) from accessing the internet.

![Internet Connection Pt.2 (Cisco).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/Cisco/Internet%20Connection%20Pt.2%20(Cisco).png)

Project File Link : [Part1](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/Cisco/Internet%20Connection%20Pt.2%20(Cisco).gns3project.part1.rar) and [Part2](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/Cisco/Internet%20Connection%20Pt.2%20(Cisco).gns3project.part2.rar) (extract the separate archives into a single project file)

PC1 from the network address 192.168.170.0/25 (VLAN 10) is still able to access the internet.

![Internet Connection Pt.2 (Cisco) (1).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/Cisco/Internet%20Connection%20Pt.2%20(Cisco)%20(1).png)
![Internet Connection Pt.2 (Cisco) (2).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/Cisco/Internet%20Connection%20Pt.2%20(Cisco)%20(2).png)

Meanwhile, PC3 from the network address 192.168.170.128/25 (VLAN 20) does not have internet access.

![Internet Connection Pt.2 (Cisco) (3).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/Cisco/Internet%20Connection%20Pt.2%20(Cisco)%20(3).png)

### MikroTik
In Mikrotik, internet access for several clients can be limited based on network addresses by creating a firewall NAT rule that grants internet access to only one network address. Other network addresses will automatically be denied internet access, as they have not been granted permission. In this case, only the 192.168.150.128/25 (VLAN 20) network address is configured to have internet access, while all other network addresses are unable to access the internet.

![Internet Connection Pt.2 (MikroTik).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/MikroTik/Internet%20Connection%20Pt.2%20(MikroTik).png)

[Project File Link](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/MikroTik/Internet%20Connection%20Pt.2%20(MikroTik).gns3project.rar) (extract the file first)

PC1 from the network address 192.168.150.0/25 (VLAN 10), does not have internet access because the network address has not been granted permission to access the internet.

![Internet Connection Pt.2 (MikroTik) (1).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/MikroTik/Internet%20Connection%20Pt.2%20(MikroTik)%20(1).png)

Meanwhile, PC4 from the network address 192.168.150.128/25 (VLAN 20) has internet access.

![Internet Connection Pt.2 (MikroTik) (2).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/MikroTik/Internet%20Connection%20Pt.2%20(MikroTik)%20(2).png)
![Internet Connection Pt.2 (MikroTik) (3).png](https://github.com/eightball270/Cisco-and-MikroTik-Internet-Connection-Pt-2/blob/main/MikroTik/Internet%20Connection%20Pt.2%20(MikroTik)%20(3).png)
