>Uses Radio Frequency over different ranges/bands

eg. 
- LAN --> Wifi
- WAN --> LTE/3G/4G/5G

Need to be **in range** and have **credentials**

## WIFI
> 2.4 GHz or 5 GHz
> Credentials: Service Set ID / SSID and Password
> Protocol: IEEE 802.11

### Process Overview:
- Device communicates with Wireless Access Point
- WAP grants permission
- Device sends Data as RF signals
- Received by other devices/WAP and gets converted back to usable data

Limits:
- Transmitter's power
- Presence of obstacles
- Density of RF
Techniques to mitigate:
- Spread spectrum transmission
- Error correction

### Process

1. Device sends a ==connection request frame== /association request using IEEE 802.11

| `MAC address`                  | A unique identifier for the device's wireless adapter.                                       |
| ------------------------------ | -------------------------------------------------------------------------------------------- |
| `SSID`                         | The network name, also known as the `Service Set Identifier` of the WiFi network.            |
| `Supported data rates`         | A list of the data rates the device can communicate.                                         |
| `Supported channels`           | A list of the `channels` (frequencies) on which the device can communicate.                  |
| `Supported security protocols` | A list of the security protocols that the device is capable of using, such as `WPA2`/`WPA3`. |
*SSID can be hidden (doesn't make it more secure because devices still broadcast SSID)

2. Wireless adapter of device configured and connection with WAP is made

### WEP (Old and Vulnerable) Challenge Response Handshake

| **Step** | **Who**  | **Description**                                                                                                                              |
| -------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 1        | `Client` | Sends an association request packet to the WAP, requesting access.                                                                           |
| 2        | `WAP`    | Responds with an association response packet to the client, which includes a challenge string.                                               |
| 3        | `Client` | Calculates a response to the challenge string and a shared secret key and sends it back to the WAP.                                          |
| 4        | `WAP`    | Calculates the expected response to the challenge with the same shared secret key and sends an authentication response packet to the client. |
Error detection with Cyclic Redundancy Check

### WPA (Still outdated) TKIP


### WPA2 AES


### WPA3 AES


## Authentication Protocols

### Extensible Authentication Protocol (EAP)
Authentication framework (not a protocol) meaning that it is a "format" of authentication using different protocols so different EAP types exist

Taken from [criticaldesign](https://www.criticaldesign.net/post/peap-vs-eap-tls)
```
We have three components to think about:

1. **Supplicant:** This is a fancy way of saying “client” or “endpoint” or typically “workstation”. A supplicant is a client-side application.
    
2. **Authenticator:** The Authenticator is the device that facilitates the authentication. E.g. A Switch or WLC is an Authenticator. The Authenticator accepts or rejects access based on what the Authentication Server has to say.
    
3. **Authentication Server:** This is the server that actually verifies the authentication is valid. E.g. The ISE Server.
```
### Light EAP 
>Uses a shared key
- Same key for encryption and authentication
- Sends username in clear and encrypted password, vulnerable to dictionary attacks
### Protected EAP
>Uses tunneled Transport Layer Security (TLS)
- Server has a digital certificate to authenticate encryption
- Encrypted tunnel to communicate
- Authenticates with password

### EAP-TLS
> Same as PEAP but both server and client use certificates
- User and Server has digital certificates to authenticate each other

## Authentication Servers

### TACACS+
>Authentication protocol used to administrate networking devices
- Whole packets are encrypted used configured encryption (TLS/IPSec)
### RADIUS
>Authentication protocol used for user authentication
- Learn more in [Rublon](https://rublon.com/blog/radius-vs-tacacs/#:~:text=The%20main%20difference%20between%20RADIUS,devices%20like%20routers%20and%20switches.)

## Disassociation Attack
> Forces client to disconnect to WAP
- Disassociation packet is used to disconnect a client
- Disrupts client's connection
- Can be used as a precursor to attacks such as MITM

## Wireless Hardening

### Wifi Protected Access
>Provides strong encryption and authentication for wireless communications

1. WPA-Personal
	- designed for home and small business networks
2. WPA-Enterprise
	- designed for larger organizations and uses a centralized authentication server (e.g., RADIUS or TACACS+) to verify the identity of clients.
### MAC Filtering
>White/Black listing MAC Addresses

### Deploying [[Wireless Network#EAP-TLS|EAP-TLS]]
>Uses digital certificates and a PKI for authentication and encryption


Extra Notes:
- [How does WPA and EAP relate to each other](https://superuser.com/questions/373453/802-1x-what-exactly-is-it-regarding-wpa-and-eap)