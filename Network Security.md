## Firewall
Monitors and filters incoming and outgoing traffic
Could be by:
- Whitelisting ports

#### Types
- Hardware or software or cloud-based
- **Stateless/packet-filtering:** (Straightforward)
	Filtering individual network packets **based on a set of rules** that would point to a source or destination IP address, ports and protocols. The firewall doesn’t consider any context of each connection when making decisions and effectively blocks denial–of–service attacks and port scans.

- **Stateful inspection:** 
	It is used to **track the state of network connections** and use this information to make filtering decisions. For example, if a packet being channelled to the network is part of an established connection, the stateful firewall will let it pass through. However, the packet will be blocked if it is not part of an established connection.

- **Proxy service:** 
	This firewall protects the network by filtering messages at the **application layer**, providing deep packet inspection and more granular control over traffic content. The firewall can block access to certain websites or block the transmission of specific types of files.

- **Web application firewall (WAF):** 
	This firewall is designed to protect web applications. WAFs block common web attacks such as SQL injection, cross-site scripting, and denial-of-service attacks.

- **Next-generation firewall:** 
	This firewall combines the functionalities of the stateless, stateful, and proxy firewalls with features such as intrusion detection and prevention and content filtering.

## Virtual Private Network (VPN)
Network security service that changes your public IP address and hides your virtual location Encapsulates and encrypts network packets and sends them to vpn server
### Protocols
- Wireguard
	- Newer, open source
	- Enhanced download speed
	- Remote access / site-to-site
- IPsec
	- Older more complex
	- Site-to-site

## Network Segmentation
Security Technique that divides the network into segments
Each segment has own access and rules
### Security Zone
Segment of network that protects internal network
- A barrier to internal networks
- Maintain privacy within corporate groups
- Prevent issues from spreading to the whole network

### Network Segments
*Between segments should be firewalls*
- Uncontrolled zone
- Controlled zone
	- Demilitarized zone, public facing
	- Internal network, self-explanatory
	- Restricted zone, highly confidential information

### Subnetting
Segmenting is done by subnetting a network
Separates network based on IP address and subnet mask

#### Classless Inter-Domain Routing notation
CIDR replaces the old class system of IP addresses and allows for network to be further segmented
x.x.x.x/x
Last number after slash is CIDR number which represents the IP range of the network

## Proxy servers
A server that fulfills a client's request by forwarding them to other servers
Sits between the internal network and the internet
Has different IP address than internal network
Temporary memory of common data requested by internet servers
### Types
- ##### Forward Proxy
	- Avoid browsing restrictions
	- Block access to certain content
	- Protect user identity online
	- *No one outside can trace back*
- ##### Reverse Proxy
	- Load Balancing
	- Protect from DDOS
	- Cache static content
	- Regulates internet's access to internal network
	- *No one outside can poke in*
- ##### Email Proxy
	- Filters spam
