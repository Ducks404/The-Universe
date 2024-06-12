## Enumeration

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-06-10 00:32 EDT
Nmap scan report for 10.10.241.225
Host is up (0.20s latency).
Not shown: 995 closed tcp ports (conn-refused)
PORT      STATE    SERVICE VERSION
22/tcp    open     ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.4 (Ubuntu Linux; protocol 2.0)
80/tcp    open     http    Apache httpd 2.4.18 ((Ubuntu))
110/tcp   open     pop3    Dovecot pop3d
143/tcp   open     imap    Dovecot imapd
22939/tcp filtered unknown
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

## OSINT
Website got pwned

List of passwords in md5 hashes
mauer@fowsniff:mailcall
mustikka@fowsniff:bilbo101
tegel@fowsniff:1dc352435fecca338acfd4be10984009
baksteen@fowsniff:19f5af754c31f1e2651edde9250d69bb
seina@fowsniff:90dc16d47114aa13671c697fd506cf26
stone@fowsniff:a92b8a29ef1183192e3d35187e0cfabd
mursten@fowsniff:0e9588cb62f4b6f27e33d449e2ba0b3b
parede@fowsniff:4d6e42f56e127803285a0a7649b5ab11
sciana@fowsniff:f7fd98d380735e859f8b2ffbbede5a7e

hydra using the usernames and passwords

got into seina

used telnet to get into pop3

found email containing ssh password
`S1ck3nBluff+secureshell`

got inot with baksteen

found executable that could be edited and run by root

rooted