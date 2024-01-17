#networkfundamentals 
## TCP
- Stateful - establishes a connection 

### Advantage vs Disadvantage
| Advantage | Disadvantage |
| ---- | ---- |
| Data Integrity | Stable connection is needed. If a small bit is corrupted, the whole part has to get sent again. |
| Syncs data to prevent flooding data | Slow connection bottlenecks a device as the connection will still be on there |
| More processes for reliability | Slower and more work than UDP |

### Packet Headers
| Header | Description |
| ---- | ---- |
| Source IP | IP of sender |
| Source Port | Port opened for TCP connection by sender. <br>*Chosen Randomly* |
| Destination IP | IP of receiver |
| Destination Port | Port that the service/application is being served on |
| Time to live | Number of sends left before die |
| Sequence Number (ISN) | Random number given to a packet for [[Packets & Frames#Three-way Handshake\|synchronisation]] purposes |
| Acknowledgement Number | Sequence Number + 1, used to acknowledge  |
| Checksum | Number derived mathematically from data to check for errors |
| Data | Data bytes |
| Flag | Explains how data should be handled |

### Three-way Handshake

#### Syn - Sender sends a packet to server (with ISN)
#### Syn/Ack - Receiver acknowledges sender (with AckNum) and sends its own Syn packet (with its own ISN)
#### Ack - Sender acknowledges receiver's Syn packet (with AckNum)

##### Data - Sender and receiver sends data
##### Fin - Sent when connection is to be closed
##### RST - sent when connection is forcibly closed

## UDP
- Stateless - doesn't establish a connection

### Advantage vs Disadvantage
| Advantages | Disadvantages |
| ---- | ---- |
| Faster than TCP | UDP doesn't care what arrives and what doesn't |
| UDP leaves applications to decide if there is any control over how fast packets are sent | It is quite flexible |
| Doesn't reserve connection like TCP | Unstable connection is terrible for user |

### Packet Headers
| Header | Description |
| ---- | ---- |
| Source IP | IP of sender |
| Source Port | Port opened for TCP connection by sender. <br>*Chosen Randomly* |
| Destination IP | IP of receiver |
| Destination Port | Port that the service/application is being served on |
| Time to live | Number of sends left before die |
| Data | Data bytes |
