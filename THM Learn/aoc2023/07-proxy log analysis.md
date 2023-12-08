## Logs
Contextualise the events

## Proxies
Intermediary between your computer or device and the internet
- Example of Malicious Activity

Attack Technique|Potential Indicator|
|-----|-----|
Download attempt of a malicious binary|Connection to a known malicious URL binary (e.g. www[.]evil[.]com/malicious[.]exe)
Data exfiltration	| High count of outbound bandwidth due to file upload (e.g. outbound connection to OneDrive)
Continuous C2 connection|High count of outbound connections to a single domain in regular intervals (e.g. connections every five minutes to a single domain)

## Linux parsing
`nl` - numbers the lines
`cut -d " " -f2,3,6 example.log` - splits lines to collumns, delimiter is " ", position is 2
`|`
`grep`
`sort`
`uniq`
`wc` - give line, word, character count

## Analysing proxy logs for use cases
