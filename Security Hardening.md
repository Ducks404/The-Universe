## OS Hardening
#### Regularly done
-  Updates, patch installation,
-  backups, and
-  keeping an up-to-date list of devices and authorized users.
-  Properly disposing hardware and software
-  Password Policy

#### Once in awhile 
-  Configuring a device setting to fit a secure encryption standard

### Baseline
**Documented set of specifications** within a system that is used as a **basis** for future builds, releases, and updates. 

## Network Hardening
#### Regularly done
- Firewall rules maintenance
- Network log analysis
- Patch updates
- Server backups

#### Once in awhile
- Port filtering <br>
  Only ports that are needed should be allowed
- Network access privileges <br>
  [[Network Security##Network Segmentation|Network Segmentation]]
- Encryption over networks

### Network Security Tools
- [[Network Security##Firewall|Firewall]]
- [[Logs and SIEM Tools#SIEM Tools|SIEM Tools]]
- Intrusion Detection System
- Intrusion Protection System

## Cloud Hardening
#### Shared responsibility model
Both CSP and organization using their services should understand their responsibilities in the security of the network. e.g. CSP secures cloud and physical servers while organizations secures configuration rules, etc
- Customers can request CSP audit

#### Cloud Security Considerations
- Identity Access Management
- Proper configuration:
  - Responsibility of organization to configure correctly
- Attack surfaces:
  - Clouds could have a lot of services used
- Zero-days:
  - CSPs would know sooner
- Visibility and tracking:
  - CSPs provide tracking services but not as much control as local 
- Things change fast in cloud

##### Techniques
- Identity Access Management
  - Manage user roles and access
- Hypervisors
  - Type 1: Run on hardware (used by CSP)
  - Type 2: Run on software
  - Vuln: misconfiguration may lead to VM escape
- Baselining
- Cryptography

#### Cryptography in Cloud
- Encryption
  - Scrambles data to ciphertext
  - Rely on secrecy of key rather than alg
- Cryptographic erasure
  - Shredding key so data is undecipherable
- Key management
  - Trusted platform module (TPM). Computer chip to securely store
  - Cloud hardware security module (CloudHSM). Computing device that provides secure storage and processes cryptographic operations
