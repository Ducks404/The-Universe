#networkfundamentals 
## Port Forwarding
- Enables services being served on a computer to be accessed outside of its local network
- **Outside network can access a computer using public IP**
- Configured at the router

## Firewalls
- Border control for the network
- Either denies or accepts packets
- Examples of questions:
	- From where
	- To where
	- Which port
	- What protocol
- Two - Five types:
	- Stateful
		- Inspects the whole connection
	- Stateless
		- Uses set rules to check each packet
- Operates at OSI Network and Transport layers

## VPN
- Connects two distant networks securely by using a dedicated path, or tunnel
#### Advantages

| **Benefit** | **Description** |
| ---- | ---- |
| Allows networks in different geographical locations to be connected. | For example, a business with multiple offices will find VPNs beneficial, as it means that resources like servers/infrastructure can be accessed from another office. |
| Offers privacy. | VPN technology uses encryption to protect data. This means that it can only be understood between the devices it was being sent from and is destined for, meaning the data isn't vulnerable to sniffing.<br><br>This encryption is useful in places with public WiFi, where no encryption is provided by the network. You can use a VPN to protect your traffic from being viewed by other people. |
| Offers anonymity. | Journalists and activists depend upon VPNs to safely report on global issues in countries where freedom of speech is controlled.<br><br>Usually, your traffic can be viewed by your ISP and other intermediaries and, therefore, tracked. <br><br>The level of anonymity a VPN provides is only as much as how other devices on the network respect privacy. For example, a VPN that logs all of your data/history is essentially the same as not using a VPN in this regard. |
#### Technologies

|**VPN Technology**|**Description**|
|---|---|
|PPP|This technology is used by PPTP (explained below) to allow for **authentication and provide encryption of data**. VPNs work by using a private key and public certificate (similar to **SSH**). A private key & certificate must match for you to connect.<br><br>This technology is not capable of leaving a network by itself (non-routable). |
|PPTP|The **P**oint-to-**P**oint **T**unneling **P**rotocol (**PPTP**) is the technology that allows the data from PPP to travel and leave a network. <br><br>PPTP is very easy to set up and is supported by most devices. It is, however, weakly encrypted in comparison to alternatives.|
|IPSec|Internet Protocol Security (IPsec) encrypts data using the existing **I**nternet **P**rotocol (**IP**) framework.<br><br>IPSec is difficult to set up in comparison to alternatives; however, if successful, it boasts strong encryption and is also supported on many devices.|

## LAN networking devices

### Router

### Switches
- Layer 2 Switches
- Layer 3 Switches
	- Also does separation of networks aka **VLAN**


