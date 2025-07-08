>Making a network without regard to physical location
>-> Adding endpoints from remote places
>-> Segmenting a network into multiple networks

\*This note is linked with [[Cisco IOS|Cisco proprietary stuff]]

- Benefits when using `VLANs`, including:
	- **`Better Organization`**: Network administrators can group endpoints based on any common attribute they share.
	- **`Increased Security`**: Network segmentation disallows unauthorized members from sniffing network packets in other `VLANs`.
	- **`Simplified Administration`**: Network administrators do not have to worry about the physical locations of an endpoint.
	- **`Increased Performance`**: With reduced broadcast traffic for all endpoints, more bandwidth is made available for use by the network.
- Cisco switches provide the `VLAN` IDs/numbers 1-4094 

| ID Range  | Usage                                                    |
| --------- | -------------------------------------------------------- |
| 0         | Reserved and unusable                                    |
| 1         | default VLAN; Cannot be altered not deleted              |
| 2-1001    | Normal-range VLANs; Config stored in `vlan.dat`*         |
| 1002-1005 | Token Ring and Fiber Distributed Data Interface(?) VLANs |
| 1006-4094 | Extended-range VLANs; Customization not saved            |
\*Stored in `vlan.dat` can have parameters including name, type, state, and maximum transmission unit (`MTU`).

### Assigning VLANs

#### 1. Static
- Simplest
- Assign each port a VLAN
- Has to be done to all switches
#### 2. Dynamic
- Automatically assigns the endpoint its VLAN
- Based on MAC Addresses or protocols
- Can be configured in a centralized management service, `VLAN Membership Policy Server` (`VMPS`)
- Flexible but increased Administrator overhead

#### Security-wise
- Static safer because port is always bound to VLAN (unless changed manually)
- Dynamic, attacker can spoof the mac to change VLANs

### Types of Ports
#### 1. Access Port
- Only connects to one VLAN
- Everything going through here is assumed to be from the VLAN it is assigned to

#### 2. Trunk Port
- Can connect to multiple VLANs
- Trunk links connect trunk ports so VLANs can communicate with each other

### VLAN Identification
> 802.3 Ethernet doesn't have a way to keep track of VLAN information so VLAN-enabled stuff need to add themselves with different protocols

#### Inter-switch Link (ISL)
- Deprecated
- Cisco-proprietary
- Encapsulated entire Ethernet frame with VLAN tag and added its own 26 byte header and 4 byte trailer

#### IEEE 802.1Q
- Modified 802.3 Ethernet frame to accommodate VLAN
![[Pasted image 20240827134203.png]]
- Pair of 2 byte fields:
	- TPID:
		- Tag protocol identifier (`TPID`) is a 16-bit field always set to `0x8100` to identify the Ethernet frame as an `802.1Q`-tagged frame.
	- TCI:
		- Tag Control Information
		- Priority code point (`PCP`)
		- Drop eligible indicator (`DEI`) (previously known as `Canonical format indicator` (`CFI`))
		- VLAN identifier (`VID`)
			- 12 bits so 2^12 - 2 = 4094 VLANs
Extra:
- The practice of inserting multiple `802.1Q` tags within a single packet is known as `Double Tagging`, introduced by [802.1ad](https://standards.ieee.org/ieee/802.1Q/10323/). (Expands number of possible VLAN ID)
- `VLAN tagging` is the process of inserting `VLAN` information into an `802.1Q` `Ethernet header`
- `VLAN untagging` is the process of removing the `VLAN` information from an `802.1Q`-tagged `Ethernet` frame and forwarding the packet to the destined ports.

## VLAN-Capable NICs
>Not all NICs are capable of being assigned a VLAN interface
### Assigning VLAN in Linux
- Works by adding an interface on top of another, parent interface
- This interface tags and untags the packets
- Tools: [ip](https://man7.org/linux/man-pages/man8/ip.8.html), [nmcli](https://linux.die.net/man/1/nmcli), and [vconfig](https://linux.die.net/man/8/vconfig) (deprecated)
#### 1. Ensure kernel as 8021q module loaded
- `sudo modprobe 8021q`
- `lsmod | grep 8021q`
#### 2. Find Physical interface to make parent
- `ip a`
#### 3. Create the VLAN interface
- Using vconfig:
	- `sudo vconfig add eth0 20`
- Using ip:
	- `sudo ip link add link eth0 name eth0.20 type vlan id 20`
- Result:
``` SNIPPET
4: eth0.20@eth0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000 link/ether a6:ba:3b:08:3a:36 brd ff:ff:ff:ff:ff:ff
```
#### 4. Assign VLAN interface its own IP Address and Start
- `sudo ip addr add 192.168.1.1/24 dev eth.20` (IP addresses based on VLAN in local network)
- `sudo ip link set up eth0.20`
#### 5. Check interface is up
- `ip a | grep eth0.20`
``` SNIPPET
4: eth0.20@eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000 inet 192.168.1.1/24 scope global eth0.20
```

### Assigning VLAN in Windows
#### GUI
- Device Manager
- Ethernet adapter properties
- Advanced -> VLAN ID -> set the VLAN ID value
#### Powershell
- Get list of available network adapters
	- `Get-NetAdapter | Format-Table -AutoSize`
- Set the VLAN ID
	- `Set-NetAdapter -Name "Ethernet 2" -VlanID 10`
- Get the VLAN ID
	- `Get-NetAdapterAdvancedProperty -DisplayName "vlan id"`

### Analyzing VLAN tagged traffic
>Tools: Wireshark and `tshark`

#### Wireshark
- `vlan` filter to find VLAN tagged packets
- `vlan.id == {number}` filters specific VLAN ID packets
#### [tshark](https://www.wireshark.org/docs/man-pages/tshark.html)
- Can enumerate the VLAN IDs found in a packet capture
- `tshark -r "Capture.pcapng" -T fields -e vlan.id | sort -n -u`


## Security Implications and VLAN attacks

### VLAN Hopping
>Exploits Cisco's Dynamic Trunking Protocol (DTP) to see traffic from other VLANs

- DTP automatically creates Trunk Links between cisco devices
- Attacker makes host act like switch
- Physical connection to DTP-enabled switch
- Attacker spoofs 802.1q and DTP packets
- Automatic trunk link
- Tools: [Yersinia](https://linux.die.net/man/8/yersinia)

### Double Tagging VLAN Hopping
> Encapsulates 802.1q packet inside of Ethernet frame so trunk port thinks it is double tagged

- Attacker needs to be connected to port in same VLAN as the native VLAN of trunk port
- Native VLAN is the VLAN that untagged traffic goes to
- Attacker tags Ethernet frame with target VLAN
- First switch strips the actual VLAN tag because it is native VLAN
- Trunk port sends out the frame because it thinks it is a native VLAN frame
- Receiving Trunk port sees the artificial target VLAN tag and sends it out through it
- Tools: [Scapy](https://scapy.readthedocs.io/en/latest/usage.html#vlan-hopping)
![[Pasted image 20240830134804.png]]

## VXLAN

>Virtual eXtensible LAN: Ethernet over IP/UDP

- 12 bits of VID not enough for some use cases
- VXLAN has 24 bits of VXLAN segment ID\
- Solution from [RFC7348](https://datatracker.ietf.org/doc/html/rfc7348)
- SOLVES:
	- Limited size
	- C




