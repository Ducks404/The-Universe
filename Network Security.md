## Firewall
Monitors and filters incoming and outgoing traffic
Could be by:
- Whitelisting ports

#### Types
- Hardware or software or cloud-based
- Stateless or Stateful
	Stateless: follow rules set by administrator (Less secure)
	Stateful: keeps track of information and proactively removes threats (More secure)
- NGFW (New Generation Firewalls)
	Most secure

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


# Network Attacks

### Brute Force
Randomly guessing passwords

#### Type of Attacks
- Simple
  	Attacker uses passwords they can think of
- Dictionary Attack
  	Attacker uses a list of common passwords or passwords that relate to target
#### Prevention
- Multi-factor authentication
- Salting and Hashing passwords
- CAPTCHA OR reCAPTCHA
- Password policies

### Packet Sniffing
Capturing unauthorized network packets

#### Type of Attacks
- Passive
	Packets are read in transit
- Active
	Packets are manipulated in transit
#### Prevention
- Use VPN
- Avoid public wifi

### DDOS
Sending overwhelming packets to server as to take it down

#### Types of Attacks
- SYN Flood
  	Attacker sends a lot of SYN packets and server can't handle it
- ICMP Flood
  	Attacker sends a lot of ICMP packets
- Ping of Death
  	Attacker send ICMP packet that's more that 64kb in size
 
### IP Spoofing
Changing source IP in packet to impersonate 

#### Types of Attacks
- On-path
	Man in the middle where threat actor sits in the middle of a connection and impersonates either end of the conversation

- Replay
	Capturing a packet and sending it out again at a later time, this could be used to disrupt of impersonate

- Smurf
	DoS + IP Spoof
