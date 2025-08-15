# Page Links

[README](../README.md) | [Screenshots](./screenshots.md) | [Change Log](./change-log.md) | [Research](./research.md) | [Troubleshooting](./troubleshooting.md) | [To Do](./to-do.md)

# Troubleshooting

## GPOs effecting domain controller
Steps Taken:
1. Opened Active Directory Users & Computers to verify that the domain controller machine was listed within the domain controller OU
2. Opened Group Policy Management to verify that GPOs were not being applied to domain controller  
a. GPOs were being applied to all ['Authenticated Users'](./screenshots.md#gpo-troubleshooting-a) by default (included domain controller)  
b. Found a [microsoft documentation page][gpo-troubleshooting-microsoft-docs-solution] detailing security groups in Active Directory  
c. Added new security groups in my respective OUs that will include all users that are not administrators ('Sales', 'Accounting')  
d. Removed 'Authenticated Users' and [added all created security groups](/screenshots.md#gpo-troubleshooting-d) to all GPOs  
e. Restarted server VM to see if changes worked  
f. Solved! (for now)  
g. edit - password policy still seems to be applied to domain controller, will research more in the future

## Windows Server VM showing no internet connection icon
Description of problem:  
When powering on the VM, the network connectivity icon in the tray showed no network connectivity  
Steps Taken:  
1. Checked Network & Internet Settings
a. Showing that device was connected to the internet via Ethernet on the ActiveDirectoryPractice.local domain
b. Showing no internet connection
2. Opened command prompt
a. Ran ipconfig - all information looked correct
b. pinged default gateway - worked
c. pinged DNS server - worked
d. pinged google.com - worked
3. Looked up issue online - apparently it could be an issue with DNS lookup not working properly
4. Opened command prompt
a. ran nslookup google.com - worked
5. Decided to [reset the network](./screenshots.md#network-troubleshooting)
6. After restarting VM, problem seems to be solved

## Manual IPv4 Address Configuration not 'sticking'
Description of the problem:  
After going through the process of manually configuring an IPv4 address as shown in the [screenshots](./screenshot-folder/AD_Server_Static_IP_Setup.png) several times, the setting didn't seem to save and was reverted back to automatic IP addressing.
Steps Taken:
1. Navigated through the menus to check for settings I was missing  
    a. Noticed [another menu](./screenshot-folder/AD_Server_Static_IP_Setup_Opt2.png) in which you can configure IP addressing  
    b. Input same static address info  
    c. Restarted machine to see if it stuck  
    d. Worked this way for some reason  