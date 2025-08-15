# Page Links

[README](/README.md) | [Screenshots](./notes/screenshots.md) | [Change Log](./notes/change-log.md) | [Research](./notes/research.md) | [Troubleshooting](./notes/troubleshooting.md) | [To Do](./notes/to-do.md)

# Change Log

## 2025-7-6 @ 23:50

**Setup:** Installed VMWare Workstation Pro and created a new VM called 'Windows Server 2022'  
**Setup:** Installed Windows Server 2022 (Desktop Experience) onto VM using ISO  
**Setup:** In Server Manager, added Active Directory Domain Services and Group Policy Management as features to the server  
**Setup:** Promoted server to the domain controller and added a new forest with the root domain name of ActiveDirectoryPractice.local  
**Reboot:** Restarted VM to fully install new features.  

## 2025-7-7 @ 00:00

**Created:** Three OUs within the domain for different regions (USA, Europe, Asia)  
**Created:** 'Nathan A. Stecker' as a User within the Users OU of USA region  
**Created:** 'IT' as a global security group within the Users OU of USA region  
**Created:** 'DL-ITAdmins' as a global distribution group within the Users OU of USA region - DL stands for distribution list  

## 2025-7-8 @ 09:00

**Change:** Migrated all lab files to a new directory '\active-directory-lab' that was created with a new local git repository  
**Change:** Linked local git repository with a new repository on GitHub  

## 2025-7-10 @ 15:55

**Change:** Changed names of established OUs (USA, Europe, Asia) to Sales, Accounting, IT  
**Created:** A new Group Policy Object (GPO) called 'Password Policy' in the Group Policy Management Console (GPMC) to ensure proper password protocols  
**Created:** A new GPO called 'Drive Mapping' in GPMC to ensure consistent resource access  
**Edited:** README.md so that screen shots is at the bottom of the page  
**Created:** A new GPO called 'Desktop Wallpaper' in GPMC to standardize workstation wallpapers  
**Created:** A new GPO called 'Disable USB devices' to restrict the connection of removeable USB storage  
**Created:** A new GPO called 'Account Lockout' to lock an account for 30 minutes after 3 invalid logon attempts to prevent brute force network attacks

## 2025-7-15 @ 22:00

**Change:** Added screenshots.md to hold project screenshots (added links on README.md to the screenshots)  
**Created:** New VM (Windows 10 Enterprise OS to test GPOs)  
**Created:** Added vm-meta-info.md to store VM login info  
**Change:** Added - in place of all spaces in file names  
**Added:** Security and Distribution Groups 'Sales', 'Accounting', 'DL-Sales', 'DL-Accounting'  
**Change:** Removed 'Authenticated Users' from security filtering within all GPOs, added the newly created security groups  
**Change:** Changed password of admin account to admin-pass123  

## 2025-8-13 @ 21:50  

**Change:** Configured Windows Server machine's IPv4 address to a static address  

## 2025-8-14 @ 19:00

**Troubleshooting:** Network connectivity issues on VM
**Added:** Troubleshooting.md to detail steps taken
**Added:** To-Do.md to list actions that I need to take

## 2025-8-14 @ 20:50

**Editing:** Messing with markdown links on troubleshooting.md to see how to get them to work in GitHub pages
