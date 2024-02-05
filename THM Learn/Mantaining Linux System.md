## Automation: Cron

`crontabs` - starts on boot and manages cronjobs
Set up one by making a special file that is recognized by crontab
Edit with `crontab -e`

| Value (needed for crontab) | Description |
| ---- | ---- |
| MIN | What minute to execute at |
| HOUR | What hour to execute at |
| DOM | What day of the month to execute at |
| MON | What month of the year to execute at |
| DOW | What day of the week to execute at |
| CMD | The actual command that will be executed. |
eg. `0 */12 * * * cp -R /home/dewa/documents/var/backups`
Resources:
- [Crontab Generator](https://crontab-generator.org/)
- [Cron guru](https://crontab.guru/)

What is `@reboot`?

## Package Management
>Open Source Software and User accessibility
>Packages are small pieces of software that make up applications

- Devs upload their tools to an 'apt' and once approved are sent out to the wild
- There is a list of sources that the OS downloads the packages from
- There are official debian sources, community sources, and it can be configured by the user
### Adding/Removing packages
- Repositories can be added with `add-apt-repository`
- Apt is a command that has many package management utilities
- Apt not only updates a package but also checks for source updates
#### Adding
- GPG (GNU Privacy Guard) keys ensure integrity of the download
- Example, Adding Sublime Text:
	- **1.** Let's download the GPG key and use apt-key to trust it:  
	`wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -`
	- **2.** Now that we have added this key to our trusted list, we can now add Sublime Text 3's repository to our apt sources list. A good practice is to have a separate file for every different community/3rd party repository that we add.
		- **2.1.** Let's create a file named **sublime-text.list** in **/etc/apt/sources.list.d** and enter the repository information like so:
		![](https://assets.tryhackme.com/additional/linux-fundamentals/part3/sources1.png)
		- **2.2.** And now use Nano or a text editor of your choice to add & save the Sublime Text 3 repository into this newly created file:
		![](https://assets.tryhackme.com/additional/linux-fundamentals/part3/sources2.png) 
		- **2.3.** After we have added this entry, we need to update apt to recognise this new entry -- this is done using the `apt update` command
		- **2.4.** Once successfully updated, we can now proceed to install the software that we have trusted and added to apt using `apt install sublime-text`
#### Removing
- `add-apt-repository --remove ppa:PPA_Name/ppa` command or by manually deleting the file that we previously added to. 
- Once removed, we can just use `apt remove [software-name-here]` i.e. `apt remove sublime-text`
# [[Logs and SIEM Tools#Logs|Logs]]
>Can be found in /var/log

Stored logs of applications.
Examples:
- web server logs capture their access

