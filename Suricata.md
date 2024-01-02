> Intrusion Detection System, Intrusion Prevention System, Network Security Monitor

It's [website](https://suricata.io/)
Google Cybersecurity on Coursera (Course 6 Module 4) for more info
Home folder: `/etc/suricata`

Has signature rule templates that can be customized to assist in setting it up

## NIDS Language
eg `alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)`
### Action
- pass
- drop (only in IPS mode)
- reject
- alert
### Header
`http $HOME_NET any -> $EXTERNAL_NET any`
- protocol
- source IP
- source port
- -> indicates direction
- destination IP
- destination port
### Rule Options
`(msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)`
- The `msg:` option provides the alert text. In this case, the alert will print out the text `“GET on wire”`, which specifies why the alert was triggered.
- The `flow:established,to_server` option determines that packets from the client to the server should be matched. (In this instance, a server is defined as the device responding to the initial SYN packet with a SYN-ACK packet.)
- The `content:"GET"` option tells Suricata to look for the word `GET` in the content of the `http.method` portion of the packet.
- The `sid:12345` (signature ID) option is a unique numerical value that identifies the rule.
- The `rev:3` option indicates the signature's revision which is used to identify the signature's version. Here, the revision version is 3.
## Output Logs
> EVE JSON can be read with `jq`
### Alert Logs
Logs detected from signature
### Network Telemetry Logs
Logs about general network activity

#### Notes
`flow_id` is the suricata-given ID for network connections