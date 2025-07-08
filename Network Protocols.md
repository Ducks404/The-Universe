Network protocols are a set of **rules** used by two or more devices on a network to describe the **order of delivery** and the **structure** of the data
## Categories
- Communication
- Management
- Security

| Protocol | Port                               | Layer (OSI)    | Description                                                                                           |
| -------- | ---------------------------------- | -------------- | ----------------------------------------------------------------------------------------------------- |
| [[DNS]]  | UDP/53                             | Application(7) | Resolves Domain Names into IP address using table                                                     |
| DHCP     | UDP/67(server)<br>UDP/68(client)   | Application(7) | Assigns IP address to devices and configures DNS server and default gateway                           |
| HTTP     | 80                                 | Application(7) | Provides communication between client and web server. (INSECURE)                                      |
| Telnet   | TCP/23                             | Application(7) | Allows device to communicate over network. Sends all in clear text (INSECURE)                         |
| SNMP     |                                    | Application(7) | Monitoring and managing devices on a network                                                          |
| HTTPS    | 443                                | Application(7) | HTTP but with SSL/TLS encryption to make it secure                                                    |
| SSH      | 22                                 | Application(7) | Create secure connection with remote device                                                           |
| SFTP     | 22                                 | Application(7) | Transfers files through SSH                                                                           |
| POP3     | 110(unencrypted)<br>995(encrypted) | Application(7) | Manage and receive emails from email server                                                           |
| IMAP     | 143(unencrypted)<br>993(encrypted) | Application(7) | Incoming email, downloads header                                                                      |
| SMTP     | 587                                | Application(7) | Transmit and route email                                                                              |
| TCP      |                                    | Transport(4)   | Used to make connection between two devices through a three-way handshake.<br>Syn --> Syn/Ack --> Ack |
| UDP      |                                    | Transport(4)   | Does not establish a connection before sending data, less reliable but faster                         |
| NAT      |                                    | Network(3)     | Changes private IP to public IP in IP header                                                          |
| ARP      |                                    | Network(3)     | Resolves IP address into Mac address                                                                  |
| ICMP     |                                    | Network(3)     | Used by devices to tell each other about data transmission error                                      |

## Wireless protocols
#### IEEE 802.11 also known as wifi

- #### WEP
	*Wired Equivalent Privacy*
	Oldest and most insecure
- #### WPA
	*Wifi Protected Access*
	Solves:
	- Uses Temporal Key Integrity Protocol
	- Uses larger secret keys
	- Include message integrity check
	Vulnerability:
	- Key Reinstallation Attack, Insert themselves in WPA authentication process and change encryption key
- #### WPA2
	*Wifi Protected Access V2*
	Solves:
	- Use Advanced Encryption Standard (AES)
	- Use CCMP instead of TKIP, encapsulates and include message integrity and authentication
	- Standard of wifi security
	Vulnerability:
	- KRACK
	Two types:
	- Personal, easier to set up
	- Enterprise, more manageable for businesses
- #### WPA3
	*Wifi Protected Access V3*
	Solves:
	- WPA3 addresses the authentication handshake vulnerability to KRACK attacks, which is present in WPA2. 
	- WPA3 uses Simultaneous Authentication of Equals (SAE), a password-authenticated, cipher-key-sharing agreement. This prevents attackers from downloading data from wireless network connections to their systems to attempt to decode it.
	- WPA3 has increased encryption to make passwords more secure  by using 128-bit encryption, with WPA3-Enterprise mode offering optional 192-bit encryption.

