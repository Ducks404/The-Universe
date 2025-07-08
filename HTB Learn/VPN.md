>Connecting remote users into the local network

TCP/1723 for Point-to-point tunneling
UDP/500 for IKEv1 and IKEv2

- Encrypt the traffic
- Work by extra layer of encapsulation
- Connects remote employees to local network
- Connects branch offices into one private network

| **Requirement**  | **Description**                                                                                                                                                         |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `VPN Client`     | This is installed on the remote device and is used to establish and maintain a VPN connection with the VPN server. For example, this could be an OpenVPN client.        |
| `VPN Server`     | This is a computer or network device responsible for accepting VPN connections from VPN clients and routing traffic between the VPN clients and the private network.    |
| `Encryption`     | VPN connections are encrypted using a variety of encryption algorithms and protocols, such as AES and IPsec, to secure the connection and protect the transmitted data. |
| `Authentication` | The VPN server and client must authenticate each other using a shared secret, certificate, or another authentication method to establish a secure connection.           |

## IPSec
>Provides encryption and authentication to IP Packets

- Has an Authentication Header (AH) that is appended to the encrypted packet for integrity and authentication purposes
- Two protocols:
	1. Authentication Header (AH): Integrity and authenticity
	2. Encapsulating Security Payload (ESP): Encryption and _optional_ authenticity
#### 1. Transport Mode
> Encrypts only data payload

#### 2. Tunnel Mode
> Encrypts data payload with IP Header effectively encapsulation

#### Protocols needed for IPSec VPN
| **Protocol**                             | **Port**    | **Description**                                                                                                                                                                                                                                                                                          |
| ---------------------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Internet Protocol` (`IP`)               | `UDP/50-51` | This is the primary protocol that provides the foundation for all internet communication. It is used to route packets of data between the VPN client and the VPN server.                                                                                                                                 |
| `Internet Key Exchange` (`IKE`)          | `UDP/500`   | IKE is a protocol that is used to establish and maintain secure communication between the VPN client and the VPN server. It is based on the Diffie-Hellman key exchange algorithm, and it is used to negotiate and establish shared secret keys that can be used to encrypt and decrypt the VPN traffic. |
| `Encapsulating Security Payload` (`ESP`) | `UDP/4500`  | ESP is also a protocol that provides encryption and authentication for IP datagrams. It is used to encrypt the VPN traffic between the VPN client and the VPN server, using the keys that were negotiated with IKE.                                                                                      |

## PPTP (Point-to-point Tunneling Protocol)
>Establishes secure tunnel between VPN server and client
- KNOWN VULNERABLITIES, DEPRECATED
- Largely replaced by more secure VPN protocols like L2TP/IPsec, IPsec/IKEv2, and OpenVPN
- Authentication method, MSCHAPv2, employs the outdated DES encryption, which can be easily cracked with specialized hardware

Other more secure protocols:
- L2TP/IPsec, IPsec/IKEv2, and OpenVPN