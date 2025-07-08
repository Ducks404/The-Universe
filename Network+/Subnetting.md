>Virtually dividing a network into subnetworks by separating network addresses
## Binary maths
## IPv4 addresses
### IP Address
192.168.1.142
### Subnet mask
>Defines subnet
>255.255.255.0
### Default gateway
>Router that allows to go out
>192.168.1.1
### Loopback address
>Troubleshoot to send ping back to self
>127.0.0.1
### Reserved address
>Class E, don't use there
### Virtual IP Address
>Self explanatory
## Getting the addresses
### Dynamic Host Configuration Protocol
>Gives IP Address to a device
### Automatic Private IP Address
>Only can talk to inside subnet
>Range: 169.254.0.1 - 169.254.255.254
>Functional: 169.254.1.0 - 169.254.254.255
>Automatic assigned and ARP asks if address being used

## Classful subnetting

| Class         | Leading bits     | Network Bits | Remaining Bits | No. Networks | Host/Network | Default Subnet Mask |
| ------------- | ---------------- | ------------ | -------------- | ------------ | ------------ | ------------------- |
| A             | 0xxx (1-127)     | 8            | 24             | 128          | 16,777,214   | 255.0.0.0           |
| B             | 10xx (128-191)   | 16           | 16             | 16,384       | 65,534       | 255.255.0.0         |
| C             | 110x (192-223)   | 24           | 8              | 2,097,152    | 254          | 255.255.255.0       |
| D (multicast) | 1110 (224-239)   | Not defined  | Not defined    | Not defined  | Not defined  | Not defined         |
| E (reserved)  | 1111 (240-254)   | Not defined  | Not defined    | Not defined  | Not defined  | Not defined         |
|               | IIIIIIIIIIIIIIII |              |                |              |              |                     |
