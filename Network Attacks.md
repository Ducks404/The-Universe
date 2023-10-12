## Brute Force
Randomly guessing passwords

#### Type of Attacks
- Simple
  	Attacker uses passwords they can think of
- Dictionary Attack
  	Attacker uses a list of common passwords or passwords that relate to target
#### Prevention
- Multi-factor authentication
- Salting and Hashing passwords
- CAPTCHA OR reCAPTCHA
- Password policies

## Packet Sniffing
Capturing unauthorized network packets

#### Type of Attacks
- Passive
	Packets are read in transit
- Active
	Packets are manipulated in transit
#### Prevention
- Use VPN
- Avoid public wifi

## DDOS
Sending overwhelming packets to server as to take it down

#### Types of Attacks
- SYN Flood
  	Attacker sends a lot of SYN packets and server can't handle it
- ICMP Flood
  	Attacker sends a lot of ICMP packets
- Ping of Death
  	Attacker send ICMP packet that's more that 64kb in size
 
## IP Spoofing
Changing source IP in packet to impersonate 

#### Types of Attacks
- On-path
	Man in the middle where threat actor sits in the middle of a connection and impersonates either end of the conversation

- Replay
	Capturing a packet and sending it out again at a later time, this could be used to disrupt of impersonate

- Smurf
	DoS + IP Spoof
