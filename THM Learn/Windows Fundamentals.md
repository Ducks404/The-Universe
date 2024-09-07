## History
#### End-user
- Windows xp 👍
- Windows vista 👎
- Windows 7 👍
	- End of life of windows xp made vendors panic to make sure their stuff works with Windows 7
- Windows 8.x 👎
- Windows 10 👍
	- Home and Pro ([Differences](https://www.microsoft.com/en-us/windows/compare-windows-10-home-vs-pro))
- [Windows 11](https://www.microsoft.com/en-us/windows?wa=wsignin1.0)
#### Server
- [Windows server 2019](https://www.microsoft.com/en-us/windows-server)

## GUI
- Pass login screen first
	- Authentication for windows account on the system/Active Directory

#### 1. The Desktop
- Filled with shortcuts
- Background can be changed
#### 2. Start Menu
![[Pasted image 20240213183341.png]]
1. Shortcuts to account, document folder, photos folder, settings, power
2. Installed programs alphabetically
3. Tiles of programs, can be added with `pin to start`
#### 3. Search Box (Cortana)
#### 4. Task View
#### 5. Taskbar
#### 6. Toolbars
#### 7. Notification Area

## File System
>Uses New Technology File System ([NTFS](https://docs.microsoft.com/en-us/windows-server/storage/file-server/ntfs-overview))

- Used to be FAT16/FAT32 (File Allocation Table) or HPFS (High Performance File System)

### NTFS
- In case of failure, can automatically repair files/folders using a log file
#### Fixes from previous
- Supports files larger than 4GB
- Set specific permissions on folders and files
- Folder and file compression
- Encryption ([Encryption File System](https://docs.microsoft.com/en-us/windows/win32/fileio/file-encryption) or **EFS**)
#### Permissions
| Permissions | Folder | File |
| ---- | ---- | ---- |
| Read | View and list subfolders and files | View or access file |
| Write | Add files/subfolders | Write to file |
| Read & Execute | Read + execution of files (inherited by files and folders) | Read + execute file |
| List Folder Contents | Read & Execute (inherited by folders only) | N/A |
| Modify | Read + Write + Deletion of folder | Read + Write + Deletion |
| Full Access | All of the above | All of the above |
- Properties > Security > Group or user to view permissions of
#### Alternate Data Streams
- Allows a file to have more than one data stream ($DATA)
- Malicious actors have hidden in ADS
- Could be used for extra information such as 'Downloaded from internet'
- Extra learn:
	- [ADS](https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/)
	- [THM Room](https://tryhackme.com/room/adventofcyber2)


## Windows/System32 Folder
- Operating system stored in `C:\Windows`
- `System Environment Variable` for Windows directory is `%windir%`
- Per [Microsoft](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.1), "_Environment variables store information about the operating system environment. This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders_".
- `System32` is a folder in `Windows` which contains critical files for the OS
- [DON'T DELETE IT](https://www.howtogeek.com/346997/what-is-the-system32-directory-and-why-you-shouldnt-delete-it/)

## User Accounts, Profiles, Permissions
### User Accounts
#### Administrator
- Can make changes to the system:
	- add users, 
	- delete users, 
	- modify groups, 
	- modify settings on the system, 
	- etc.
#### Standard User
- Can only change files/folders attributed to the user
- Can't perform system level changes such as installing programs
#### Local User and Group Management
- `run` ->`lusrmgr.msc`
## User Account Control
>Standard users don't need escalated privileges to do normal tasks and in an escalated state, malware can affect a system more

UAC was made to protect against this.
It works by making when an administrator is logged in, it doesn't run with escalated privileges. It needs to be confirmed by the user when they try to do something that needs higher priviliges.

You can see this in action with the small shield icon.
Read more: [UAC](https://docs.microsoft.com/en-us/windows/security/identity-protection/user-account-control/how-user-account-control-works)

*Settings can be changed in [[Windows Fundamentals#Tools|System Configuration]] with the UAC tool*

## Settings and Control Panel
>Making changes to the OS can be made from settings and control panel

- Control panel has more complex changes
- Settings was made in windows 8
- Now settings is used more

## Task Manager
>Provides information about the applications and processes currently running on the system. 

Other information is also available, such as **how much CPU and RAM** are being utilized, which falls under **Performance**.

Read more:
- [Task Manager](https://www.howtogeek.com/405806/windows-task-manager-the-complete-guide/)
- THM Room: [Core windows processes](https://tryhackme.com/jr/btwindowsinternals) ([[Core Windows Processes|Notes]])

## System Configuration
>Advanced Troubleshooting to help diagnose startup issues

[MSconfig docs](https://docs.microsoft.com/en-us/troubleshoot/windows-client/performance/system-configuration-utility-troubleshoot-configuration-errors)

### General
- Decides which services to start on startup:
	  - Normal
	  - Diagnostic
	  - Selective
### Boot
- Settings for booting the OS
### Services
- Lists all services set for the system,
- Services are special programs that run in the background
### Startup
- Go to task manager to make changes to applications on startup
### Tools
- Various tools to run to configure the operating system further
- Examples:
	- Change UAC
	- Computer management

## Computer Management
>`compmgmt`

### System tools
- Task Scheduler:
	- We can set up a task to do something with triggers and actions
- Event Viewer:
	- Basically a place to look for logs
	- Useful for debugging
	- Event Viewer has three panes:
		1. The pane on the left provides a hierarchical tree **listing of the event log providers.**
		2. The pane in the middle will display a **general overview and summary **of the events specific to a selected provider.
		3. The pane on the right is the **actions** pane.
	- Five types of events: ([Docs](https://docs.microsoft.com/en-us/windows/win32/eventlog/event-types))
	- Four types of standard logs: ([Docs](https://docs.microsoft.com/en-us/windows/win32/eventlog/eventlog-key))
	- [THM Room](https://tryhackme.com/room/windowseventlogs)
	- 
### Storage

### Services and Applications

