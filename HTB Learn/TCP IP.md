## Main Functions
|**Task**|**Protocol**|**Description**|
|---|---|---|
|`Logical Addressing`|`IP`|Due to many hosts in different networks, there is a need to structure the network topology and logical addressing. Within TCP/IP, IP takes over the logical addressing of networks and nodes. Data packets only reach the network where they are supposed to be. The methods to do so are `network classes`, `subnetting`, and `CIDR`.|
|`Routing`|`IP`|For each data packet, the next node is determined in each node on the way from the sender to the receiver. This way, a data packet is routed to its receiver, even if its location is unknown to the sender.|
|`Error & Control Flow`|`TCP`|The sender and receiver are frequently in touch with each other via a virtual connection. Therefore control messages are sent continuously to check if the connection is still established.|
|`Application Support`|`TCP`|TCP and UDP ports form a software abstraction to distinguish specific applications and their communication links.|
|`Name Resolution`|`DNS`|DNS provides name resolution through Fully Qualified Domain Names (FQDN) in IP addresses, enabling us to reach the desired host with the specified name on the internet.|
