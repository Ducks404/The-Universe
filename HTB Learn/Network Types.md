### WAN
> The Internet

- Can also be "Internal WAN" (also called Intranet, Airgap Network, etc.)
- WAN Specific routing protocol such as BGP
- IP Schema in use is not within RFC 1918 (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16) 

### LAN/WLAN


### VPN
>Making the user feel as if they were plugged into a different network

#### Site-to-site VPN
- Both client and server are network devices (router/firewall)
- Connect two networks together

#### Remote Access VPN
- Like OpenVPN
- As if user is plugged into network
Split-tunnel VPN:
	VPN interface only make routes in the network 
	- (good for HTB) 
	- (Not good for enterprise as network malware that reaches into internet won't go through the VPN network)

#### SSL VPN
>VPN inside web browser

### WPAN
In the context of the Internet of Things (IoT), WPANs are used to communicate control and monitor applications with low data rates. Protocols such as ==Insteon, Z-Wave, and ZigBee== were explicitly designed for smart homes and home automation.

