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
Steps Taken:
1. Checked Network & Internet Settings
a. Showing that device was connected to the internet via Ethernet on the ActiveDirectoryPractice.local domain
a. Showing no internet connection
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