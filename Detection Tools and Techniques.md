## Intrusion Detection Systems
### Host-based IDS
	Installed on Endpoints
A HIDS monitors internal activity happening on the host to identify any unauthorized or abnormal behavior. If anything unusual is detected, such as the installation of an unauthorized application, the HIDS logs it and sends out an alert. 

In addition to monitoring inbound and outbound traffic flows, HIDS can have additional capabilities, such as monitoring file systems, system resource usage, user activity, and more.

### Network-based IDS
	Installed on a network
A **network-based intrusion detection system** **(NIDS)** is an application that collects and monitors network traffic and network data. NIDS software is installed on devices located at specific parts of the network that you want to monitor. The NIDS application inspects network traffic from different devices on the network. If any malicious network traffic is detected, the NIDS logs it and generates an alert.

#### NIDS Rules
1. Action (to take)
	Example: Send out alert 
2. Header (containing signature packet's information)
	Example: tcp 10.10.10.10 any -> 198.162.00.17 80
3. Rule Options (to add parameters)
	(msh: "This is a message"; sid: 12345; rev:1)

#### Example
[[Suricata]]

## Detection Techniques
### Signature based
Uses set IOC
#### **Advantages**
- **Low rate of false positives:** Signature-based analysis is very efficient at detecting known threats because it is simply comparing activity to signatures. This leads to fewer false positives. Remember that a **false positive** is an alert that incorrectly detects the presence of a threat.

#### **Disadvantages**
- **Signatures can be evaded:** Signatures are unique, and attackers can modify their attack behaviors to bypass the signatures. For example, attackers can make slight modifications to malware code to alter its signature and avoid detection.

- **Signatures require updates:** Signature-based analysis relies on a database of signatures to detect threats. Each time a new exploit or attack is discovered, new signatures must be created and added to the signature database.

- **Inability to detect unknown threats:** Signature-based analysis relies on detecting known threats through signatures. Unknown threats can't be detected, such as new malware families or **zero-day** attacks, which are exploits that were previously unknown.

### Anomaly based
Trained on baseline and it detects anomalies from baseline
#### **Advantages**
- **Ability to detect new and evolving threats:** Unlike signature-based analysis, which uses known patterns to detect threats, anomaly-based analysis _can_ detect unknown threats.

#### **Disadvantages**
- **High rate of false positives:** Any behavior that deviates from the baseline can be flagged as abnormal, including non-malicious behaviors. This leads to a high rate of false positives.

- **Pre-existing compromise:** The existence of an attacker during the training phase will include malicious behavior in the baseline. This can lead to missing a pre-existing attacker.