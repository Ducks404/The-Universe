> Sits in the middle of a connection and acts as a **mediator** (can inspect on the packet)

## Forward Proxy
> A client makes a request to a computer, and that computer carries out the request. (Filters outcoming traffic)
- Malware would need to be proxy-aware to bypass with proxy (Most browsers use winsock while firefox uses libcurl)
- Monitoring DNS with sysmon also helps against malware
## Reverse Proxy
> Filters incoming traffic
> Goal: Listen in on an address and forward to a closed-off network
- Cloudflare is used because they have robust network that is good against DDOS
- Pentesters will turn infected endpoints into reverse proxies to 

## (Non) Transparent
> Transparent: Client doesn't know proxy exists | Doesn't modify packets
> Non-transparent: Client and service knows proxy exists | Modifies packets