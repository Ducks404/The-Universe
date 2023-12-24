## Diamond Model
[THM room on it](https://tryhackme.com/room/diamondmodelrmuwwg42)
### 4 Components
- #### Adversary
Individual or groups that want to disrupt other operations
- #### Infrastructure
Tools, i.e. software/hardware, used by adversary
- #### Capabilities
Tactics, Techniques, and Procedures
- #### Victim
Target of adversary

### 2 Defensive Methods
- #### Vulnerability Management
Keeping the infrastructure according to the security posture of the company

- #### Threat Hunting
Continuous and regular search for active attacks

## Defense Infrastructure
### [[Network Security#Firewall|Firewalls]]
#### Default ufw installed on Ubuntu
Check for firewall status
`sudo ufw status` --> `Status Inactive`
Allow/Deny as a default
`sudo ufw default allow outgoing`
`sudo ufw default deny incoming`
Allow/Deny specific port
`sudo ufw allow 22/tcp`
Allow/Deny specific IP Address 
`sudo ufw deny from [IP Address]`
Allow/Deny specific IP Address and Interface
`sudo ufw deny in on eth0 from [IP Address]`
Enable firewall
`sudo ufw enable`
Check for rules
`sudo ufw status verbose`
Reset to defaults
`sudo ufw reset`

### Honeypot
