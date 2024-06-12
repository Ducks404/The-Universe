### Transmission medium layout
>How physical devices are placed and wired
### Logical layout
>How the signals interact with each other

Can be broken to 3 areas
## Connections
>Wired/Wireless --> Cable/wifi
## Nodes - Network Interface Controller
>Repeated/Router/Switch/etc
## Classifications
> Structure of network | Physical does not have to correlate with logical

Common types

| Point-to-Point | Bus         |
| -------------- | ----------- |
| Star           | Ring        |
| Mesh           | Tree        |
| Hybrid         | Daisy Chain |
## Point-to-point
> Link between two hosts | Not peer2peer

## Bus
> All devices connected to bus cable without network device in the middle
> Only 1 send and else receive

## Star
> Central networking device connected to all hosts
> High traffic on the device

## Ring
> Physical: Devices connected with one input and one output wire forming a ring
> Logical: Based on star physical, packets sent through sequential ports with token

## Mesh
> Many nodes decides on the physical and logical level so not really fixed
> Fully meshes: Every host connected to each other
> Partially meshes: Not all host connected to each other

## Tree
> Extended star
> Hierarchy of star topologies basically

## Hybrid
> Mix of two or more topologies

## Daisy-chain
> Line of nodes connected not like ring
> Based on physical and not logical like ring tokens
