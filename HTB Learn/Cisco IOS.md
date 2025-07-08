>Cisco networking devices' operating system

- Features required for the operation of modern networks, such as, but not limited to:
	- Support for IPv6
	- Quality of Service (QoS)
	- Security features such as encryption and authentication
	- Virtualization features such as Virtual Private LAN Service (VPLS)
	- Virtual Routing and Forwarding (VRF)

- Can be configured using CLI or GUI
- Supports various network protocols and services required for network operations. These include:

|**Protocol Type**|**Description**|
|---|---|
|`Routing protocols`|Such as [OSPF](https://en.wikipedia.org/wiki/Open_Shortest_Path_First) and [BGP](https://en.wikipedia.org/wiki/Border_Gateway_Protocol) are used to route data packets on a network.|
|`Switching protocols`|Such as [VLAN Trunking Protocol](https://en.wikipedia.org/wiki/VLAN_Trunking_Protocol) (`VTP`) and [Spanning Tree Protocol](https://en.wikipedia.org/wiki/Spanning_Tree_Protocol) (`STP`) is used to configure and manage switches on a network.|
|`Network services`|Such as [Dynamic Host Configuration Protocol](https://en.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol) (`DHCP`) are used to automatically provide clients on the network with IP addresses and other network configurations.|
|`Security features`|Such as [Access Control Lists](https://en.wikipedia.org/wiki/Access-control_list) (`ACLs`), which are used to control access to network resources and prevent security threats.|
- Different types of passwords are used for various purposes, for example:

| **Password Type** | **Description**                                                                                                                                                                                                                                                   |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `User`            | The [user](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/security/s1/sec-s1-cr-book/sec-cr-t2.html#wp2992613898) -> Restrict access to the network device and its features.                                                                                   |
| `Enable Password` | The [enable password](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/security/d1/sec-d1-cr-book/sec-cr-e1.html#wp3884449514) -> Access to advanced functions and settings.                                                                                     |
| `Secret`          | The [secret](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/security/s1/sec-s1-cr-book/sec-cr-s1.html#wp2622423174) -> Access to certain functions and services. It is often used to restrict access to remote management tools and services.                  |
| `Enable Secret`   | The [enable secret](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/security/d1/sec-d1-cr-book/sec-cr-e1.html#wp3438133060) is an extra-secure password used to secure access to "enable" mode, and they are stored encrypted to provide additional protection. |
- Can be accessed remotely with SSH/Telnet


## Cisco Discovery Protocol