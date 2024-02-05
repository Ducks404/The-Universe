## Text Editors
- #### Nano
- #### VIM

## Utilities
- #### Download (wget)
- #### Transfer Files (scp)
- #### Serving files (python -m http.server)
- #### Serving files ([what'supdog](https://github.com/sc0tfree/updog))

## Processes
>Programs running on computer

#### Viewing processes
- `ps aux`
- `top` real-time stats
#### Managing Processes
- `kill [pid]`
- Signals:
	- SIGTERM - kill but allow to cleanup
	- SIGKILL - kill and just kill
	- SIGSTOP - stop/suspend
#### Where do they start
##### Namespaces
>Slices up resources for processes
- Good for security

Systemd (process between os and user) is the first process that starts and all other processes are a **child** of this process.
#### Start on boot
>Useful for web servers and the like
- `systemctl [option] [service]`
	- `start`
	- `stop`
	- `enable`
	- `disable`
#### Background and Foregrounding process
##### Background
- `[command] &`
- `ctrl + z`
##### Foreground
- `fg`