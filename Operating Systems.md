Interface between computer hardware and user

Function: Make computer run as efficient as ever while still easy to use

## Common Operating Systems
### Linux
- Open-source
- Common vulns: [Common Vulnerabilities and Exposures (CVE) Report for Ubuntu](https://ubuntu.com/security/cves)

### Windows
- Closed-source
- Common vulns: [Microsoft Security Response Center (MSRC)](https://msrc.microsoft.com/update-guide/vulnerability)

### MacOS
- Partially open-source, eg kernel
- Common vulns: [Apple Security Updates](https://support.apple.com/en-us/HT201222)

### IOS
- Partially open source

### Chrome OS
- Partially open-source
- Common vulns: [Google Cloud Security Bulletin](https://cloud.google.com/support/bulletins)

### Android
- Open source

### Legacy operating systems
- May be vulnerable as they are not kept up-to-date although still used because of non-supported software

## How they work
### Starting
1. Press button
2. Starts Basic Input/Output System (BIOS) or Unified Extensible Firmware Interface (UEFI)
3. Loads bootloader
4. Bootloader starts the operating system

### Interactions
1. User interacts with application for specific task
2. Application sends requests to OS
3. OS interprets requests and directs to appropriate component in hardware
4. Hardware sends information to OS
5. OS sends to application

### Resource allocation
OS manages the resources and makes sure applications allocate and de-allocate the resources they use to make computer run efficiently

## Virtualization
- Virutal machines are virtual versions of physical computers.
- Uses software-defined versions of physical hardware
- It's just code

### Benefits
- Security
  - Guests are isolated from hosts
  - Used for analyzing malware and the such
  - **VM escapes are still possible**
- Efficiency
  - Using multiple VMs on same physical computer can streamline work
 
### Management
**Hypervisors** manage the VMs running on a computer
  - Connects the VMs to physical hardware
  - Allocating shared resources
  - **KVM** Kernel-based Virtual Machine is hypervisor built into Linux distros

### Others
 - Virtual servers
 - Virtual Networks
