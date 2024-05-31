## Statistics
- Most packets are of ***DNS*** and ***HTTP
Legend
- ==Suspicious==
### TCP
#### 10.10.29.186 --> 10.11.5.137
- Port 80 HTTP
- GET request of ==cdn[.]bandityeti[.]htm/mysterygift.exe==
- User-agent: ==windowspowershell==
- SHA256: 0ce160a54d10f8e81448d0360af5c2948ff6a4dbb493fe4be756fc3e2c3f900f
	- Virustotal results: 

#### 10.10.29.186 --> 10.10.114.77
- Port 80 HTTP
- GET request favicon.ico

#### 10.11.5.137 --> 10.10.29.186
- Port 54653 --> Port 3389
- ==Remote Desktop Protocol==
- Marked as suspicious as the origin IP address is the same as the destination of an HTTP conversation previously

### UDP
#### 10.10.29.186 --> 51.137.137.111
- Port 123 NTP(?)

#### 10.10.29.186 --> 10.10.106.46
- Port 62754 --> Port53 DNS
- DNS Query:
	- ==cdn[.]bandityeti[.]htm==
	- *Suspicious url*
- DNS Answer:
	- 10.11.5.137

#### 10.10.29.186 --> 10.10.106.46
- Port 50122 --> Port 53 DNS
- DNS Query:
	- ==bestfestivalcompany[.]thm==
	- *Suspicious url*
- DNS Answer:
	- 10.10.114.77

## Summary
APT: Bandit Yeti
Domains: cdn[.]bandityeti[.]htm
IP Address: 10.11.5.137
Shared files: 
- mysterygift.exe - malware
	- Host: 10.11.5.137

Suspected Timeline:
- Compromised machine downloaded `mysterygift.exe` from `cdn[.]bandityeti[.]htm`
- Malware made RDP possible
- `cdn[.]bandityeti[.]htm` server connected to compormised machine via RDP and did stuff on it