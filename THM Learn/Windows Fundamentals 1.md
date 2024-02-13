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


## User Accounts, Profiles, Permissions


## User Account Control


## Settings and Control Panel


## Task Manager
