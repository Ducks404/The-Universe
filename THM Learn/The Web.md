- Request a website, 
- Uses [[DNS]] to know the IP address of the server to talk to. 
- Talks to the web server using a special set of commands called the [[HTTP]] protocol; 
- The [[websites|webserver]] then returns HTML, JavaScript, CSS, Images.
- Which your browser then uses to correctly format and display the website to you.

## Extra components

### Load Balancer
Uses:
- Ensuring high traffic websites can handle the load
- Providing a failover if a server becomes unresponsive
How it works:
- Acts as proxy before requests goes to web servers
- Uses algorithms to decide where to forward the request
- Example:
	- Round robin
Extra:
- Also checks if each server is running well; **Health Check**

### Content Delivery Machine
Uses:
- Hosts static websites all throughout the servers of the world
- Decides which server is physically close to the request
- Example: Cloudflare

### Databases
Uses:
- Server that is used for storing information that webservers call
Extra:
- Can be in form of simple document or multitude of high speed servers
- Common databases: MySQL, MSSQL, MongoDB, GraphQL, Postgres, and more; each has its specific features.

### Web Application Firewall
Use:
- Protects web server from DDOS/hacking
- Analyses requests to know if it came from bot or genuine browser
- **Rate limiting** to prevent excessive requests, limited by request per IP