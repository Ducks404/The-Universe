## Importance of Network Layout

>Security-wise, a flat network will be insecure whilst a one equipped with cyber best practices will slow attackers down

#### Example 1: Segmentation
Making small networks and using access control lists
-> Surrounding house with fence
- can still jump over but is suspiscuous 
-> Why is printer talking to servers with **HTTP**
#### Example 2: Mapping purposes
Mapping out the purposes of each part of the network
-> Placing lights everywhere
- makes everything easier to see
-> Why is the printer communicating to the **Internet**
#### Example 3: Hiding ports
Installing [[Detection Tools and Techniques#Intrusion Detection Systems|IDS]] to detect port scans
-> Bushes in front of windows
- Deters from breaking into window
-> Why did port scan come from **printer**?
#### Pentester Story
>Misunderstood structure of network causes a database to be hidden from sight
- CIDR: /24 is full, /25 is half
Attacker found client with password on they're half but couldnt get high-value database on other half

#### Extra points

