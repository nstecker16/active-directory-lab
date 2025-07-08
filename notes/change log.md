# Change Log - Active Directory Lab

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