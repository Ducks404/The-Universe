> Makes easy to remember how to access servers with alphanumerical instead of numerical IP addresses

## Domain hierarchy
eg. www.admin.tryhackme.com
### Top Level Domain
- .com
There are two types:
- Generic TLD
- Country Code TLD

[List of all gTLD](https://data.iana.org/TLD/tlds-alpha-by-domain.txt)
### Second Level Domain
- tryhackme
Limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens

### Subdomain
- admin
Each subdomain limitations same as second level domain
Can have as many subdomains separated by periods

Total characters of domain <= 253

## **DNS Record Types**  

DNS isn't just for websites though, and multiple types of DNS record exist. We'll go over some of the most common ones that you're likely to come across.  

#### **A Record**
These records resolve to IPv4 addresses, for example 104.26.10.229
#### **AAAA Record**
These records resolve to IPv6 addresses, for example 2606:4700:20::681a:be5  
#### **CNAME Record**
These records **resolve to another domain name**, for example, TryHackMe's online shop has the subdomain name store.tryhackme.com which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.  
#### **MX Record**
These records resolve to the address of the servers that handle the **email** for the domain you are querying, for example an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com. These records also come with a priority flag. This tells the client in which order to try the servers, this is perfect for if the main server goes down and email needs to be sent to a backup server.
#### **TXT Record**
TXT records are free text fields where any text-based data can be stored. TXT records have multiple uses, but some common ones can be to list servers that have the authority to send an email on behalf of the domain (this can help in the battle against spam and spoofed email). They can also be used to verify ownership of the domain name when signing up for third party services.

## Making requests
1. Goes to local cache
2. Goes to recursive DNS, provided by ISP, usually has cache
3. Root DNS, backbone of DNS, stores servers of TLDs
4. TLD server holds record to find authoritative server
5. Authoritative server holds all records of a domain name including changes and such

## Commands
`nslookup domain.name.com`

| DNS Type | Commands |
| ---- | ---- |
| A | --type=A |
| CNAME | --type=CNAME |
| MX | --type=MX<br> |
| TXT | --type=TXT |