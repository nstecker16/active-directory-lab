# Getting KVM/QEMU Access to a Mounted NTFS Drive

## Problem

After I installed KVM/QEMU and the Virtual Machine Manager to my Linux machine and tried to create a VM using an ISO saved on a mounted M.2 SSD drive (NTFS partition) and create storage space for the VM on that same drive, I ran into several errors related to Linux security and access measures.  

Linux's file permission system, libvirt's AppArmor profile, and the fact that the mounted drive was an NTFS (Windows) partition were all blocking access for both KVM/QEMU and Virtual Machine Manager from accessing the files they needed in my system.  

### What Needed to be Fixed

- virt-manager (Virtual Machine Manager GUI application, running under my user account) needed to be able to browse ISO and VM directories on the mounted drive  
    - Needed r+x permissions on all parent directories  
- libvert-qemu (user associated with KVM/QEMU) needed to be able to read ISOs and write VM disk storage on the mounted drive
    - Needed r for ISO file locations, rwk permissions for VM disk directories
    - Also needed AppArmor permission to r ISOs and rwk VM disk directories

## Background Info

[Here is a good article][red-hat-linux-perms] explaining Linux file permissions and how to understand them.  

## Solution Steps

1. Allow libvirt-qemu access to read and traverse files in the mounted directories  
    - The permissions for mounted files was listed as /media/(username)  drwxr-x---  root root  
    - Therefore, 'others' (including libvirt-qemu) were not allowed to read, write, or execute/traverse within mounted files  
    - Changed permissions using command `sudo chmod o+rx /media/(username)`  
    - Now others can read and traverse these files and directories  
2. Give permissions in AppArmor profile  
    - AppArmor was blocking libvirt from accessing mounted ISO and VM disk files  
    - Added `/media/(username)/(M.2 SSD)/ r,` and `/media/(username)/(M.2 SSD)/** r` to the AppArmor profile (between the { }) so that libvirt could read ISO files from those directories  
    - Added `/media/(username)/(M.2 SSD)/(directory for VM disks)/ r,` and `/media/(username)/(M.2 SSD)/(directory for VM disks)/** rwk,` to the AppArmor profile so that libvirt could read, write, and create VM disk storage  
    - Reload and validate AppArmor profile using command `sudo apparmor_parser -r /etc/apparmor.d/usr.sbin.libvirtd`

[paste links below here]: #

[red-hat-linux-perms]: https://www.redhat.com/en/blog/linux-file-permissions-explained