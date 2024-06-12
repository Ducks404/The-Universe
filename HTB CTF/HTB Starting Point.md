# Meow
Telnet into the machine with basic usernames like
`admin
`administrator
`root`

# Fawn
FTP into machine with `anonymous`
`get flag.txt`

# SMBCLIENT

- ADMIN$ - Administrative shares are hidden network shares created by the Windows NT family of operating systems that allow system administrators to have remote access to every disk volume on a network-connected system. These shares may not be permanently deleted but may be disabled. 
- C$ - Administrative share for the C:\ disk volume. This is where the operating system is hosted. 
- IPC$ - The inter-process communication share. Used for inter-process communication via named pipes and is not part of the file system. 
- WorkShares - Custom share.

`smbclient \\\\{IP}\\WorkShares`