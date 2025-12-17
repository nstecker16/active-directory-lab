# Active Directory Lab v2.0

___Start Date: 15 December 2025___

___End Date: current___

# Page Links

[README](#) | [Screenshots](./notes/screenshots.md) | [Change Log](./notes/change-log.md) | [Research](./notes/research.md) | [Troubleshooting](./notes/troubleshooting.md) | [To Do](./notes/to-do.md)

**Note:** [a] refers to the lettered screenshots on the [screenshots.md](./notes/screenshots.md) file (you can click on letters for link navigation to screenshot)

## Update for v2.0: 15 December 2025

Re-visiting this project and making some changes:
- Basically re-creating project from scratch utilizing new evaluation copies
    - Now using a new Windows 11 Evaluation copy for mock user machines
- Utilizing Linux's in-built KVM/QEMU virtualization platform with Virtual Machine Manager instead of VMWare Workstation Pro
    - Current OS kernel is not supported by VMWare
- Modified README.md to reflect new status of project
    - Copied old README and moved to /notes/other-resources for reference
- All other /notes files have a line indicating where v2.0 begins

## Objective

Apply basic functions in Active Directory such as creating and modifying groups, users, and devices as well as applying policies and more

## Setup

1. Created virtual machines (VMs) using KVM/QEMU
2. Installed Microsoft Server 2022 on a VM[^1]
3. Added Active Directory as a feature on the server using Server Manager
4. Installed Microsoft Windows 10 Enterprise on another VM to test policies[^2]

## Key Concepts Learned

- Adding and utilizing Active Directory on Windows Server
- Creating Organizational Units (OUs) and adding objects to them such as Users, Computers and Servers [[a]](./notes/screenshots.md#a)
- Creating Security groups
- Creating Distribution groups
- Creating Group Policy Objects (GPOs) including: password policies [[b]](./notes/screenshots.md#b), drive mapping preferences [[c]](./notes/screenshots.md#c), desktop wallpaper settings [[d]](./notes/screenshots.md#d), restrict control panel access [[e]](./notes/screenshots.md#e), disabling removeable storage [[f]](./notes/screenshots.md#f), account lockout protocols [[g]](./notes/screenshots.md#g)

## Secondary Concepts Learned

- Utilizing a VM environment with Linux KVM/QEMU
- Installing Windows Server 2022 on a VM
- Installing Windows 11 Enterprise on a VM
- Utilizing Server Manager on Windows Server to manage services and features
- Creating documentation files using markdown
- Utilizing Git and GitHub to document changes

## Challenges, Bugs & Fixes

- When I first added GPOs to my domain, they were affecting my administrator login as well (restricted my ability to access control panel features on domain controller account) [GPO Troubleshooting](./notes/troubleshooting.md#GPOs-effecting-domain-controller)
- Windows Server VM was showing no internet connectiog [Internet Connectivity Troubleshooting](./notes/troubleshooting.md#windows-server-vm-showing-no-internet-connection-icon)
- IPv4 Static addressing configuration not saving in the Server VM [Static Addressing Troubleshooting](./notes/troubleshooting.md#manual-ipv4-address-configuration-not-sticking)
- Windows 10 Enterprise VM cannot resolve ActiveDirectoryPractice.local's IP address [Domain DNS troubleshooting](./notes/troubleshooting.md#Windows-10-Enterprise-VM-not-resolving-domain's-IP-address)

    --- BEGIN v2.0 ---
    
- Getting access for KVM/QEMU, the user libvirt-qemu, and the GUI program virt-manager to the mounted M.2 SSD where I have ISO images saved and wanted to store VM data was a challenge. [Here is how I did it.](./notes/other-resources/kvm-qemu-m2ssd-access.md)  

## Page Links

[Screenshots](./notes/screenshots.md)  
[Change Log](./notes/change-log.md)  
[Research](./notes/research.md)  
[Troubleshooting](./notes/troubleshooting.md)  
[To Do](./notes/to-do.md)  

## Next Steps

[^1]: Obtained a [180-day evaluation copy][microsoft-server] for Windows Server 2022  
[^2]: Obtained a [90-day free-trial][windows-11-enterprise] for Windows 11 Enterprise.

[microsoft-server]: https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022
[windows-11-enterprise]: https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise
[gpo-troubleshooting-microsoft-docs-solution]: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups