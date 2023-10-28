## Architecture Components
### User
- Person interacting with computer
- Linux is multi-user
#### Root user
Super user that can do anything
- logging in as root user is bad practice, security issues, easy to make mistakes, accountbility
- `sudo` command to execute command as root
- Only users in sudoer file can use `sudo`
#### [[Linux commands#User|Commands]]

### Application
- Programs that perform specific tasks
- Some might be pre-installed but others need to be installed
- Use package manager to install, manage, remove packets
- Package is software that can be combined into applications

### Shell
Command line interpreter

### Filesystem Hierarchy Standard
- A way to organize data so that it can be found when the data is accessed by the system.
- EVERYTHING IS A FILE
- `man hier` to learn about FHS
#### Standard diretories
- `/home`
  - Place for each user
- `/bin`
  - Binaries and other executables
- `/tmp`
  - Temporary files
- `/etc`
  - System's config file
- `/mnt`
  - Mount, USB, hard drives, etc
#### [[Linux commands#File system|Commands]]

### Kernel
- Manages processes and memory
- Communicates with hardware to execute commands from shell
- Uses drivers to enable applications

### Hardware
- Physical components of computer
- Peripheral: attached and can be removed
- Internal: components required to run the computer

## Permissions
- Read, Write, Execute
- User, Group, other
- `drwxrwrwx`
#### Changing permissions
- `chmod u+x,g+w,o-r file.txt`

## Distributions (Distros/Flavors)
Different distributions might have different pre-installed programs, UI, etc.

### Kali Linux 
###### Debian-based, Penetration testing and digital forensics
#### Tools
- Metasploit
- Burp suite
- John the ripper
- TCPdump
- Wireshark
- Autopsy

### Ubuntu
###### Debian-based, General use
#### Notes
- CLI and GUI
- Large number of community resources

### Parrot
###### Debian-based, Penetration testing and digital forensics
#### Notes
- User-friendly, GUI and CLI

### Red Hat Enterprise Linux
###### ...-based, Enterprise use
#### Notes
- Not free
- Customer service

### CentOS
###### Red Hat-based, 

## Packages
Pieces of software that can be combined to make programs

### Package managers
- Help Install, Manage, Remove packages
- Specific package managers for specific parent distros; eg. dpkg for debian and rpm for red hat

### Package manager tools
- Programs that make is easy to install, manage, remove, update packages
- eg. APT and YUM
