Key 1
Needed hint
ROBOTS.txt

Key 2
Needed walkthrough
gobuster then hydra

I should've sorted and filtered out the unique words in the wordlist

Found wordpress login

wordpress --> edit appearance themes --> php revshell

shell as daemon

found password hash in home/robot --> searched online

Found key 2 in home/robot

Key 3
Privesc to root

find suid binaries

`find / -perm -u=s -type f 2>/dev/null`

nmap with suid binary

used gtfobin to escalate nmap

got final key in /root