# Active Directory Lab

___Start Date: 6 July 2025___

___End Date: current___

**Note:** [a] refers to the lettered screenshots on the [screenshots.md](/screenshots.md) file (you can click on letters for link navigation to screenshot)

## Objective

Apply basic functions in Active Directory such as creating and modifying groups, users, and devices as well as applying policies and more

## Setup

1. Created virtual machines (VMs) using VMWare Workstation Pro[^1]
2. Installed Microsoft Server 2022 on a VM[^2]
3. Added Active Directory as a feature on the server using Server Manager
4. Installed Microsoft Windows 10 Enterprise on another VM to test policies[^3]

## Key Concepts Learned

- Adding and utilizing Active Directory on Windows Server
- Creating Organizational Units (OUs) and adding objects to them such as Users, Computers and Servers [[a]](/screenshots.md#a)
- Creating Security groups
- Creating Distribution groups
- Creating Group Policy Objects (GPOs) including: password policies [[b]](/screenshots.md#b), drive mapping preferences [[c]](/screenshots.md#c), desktop wallpaper settings [[d]](/screenshots.md#d), restrict control panel access [[e]](/screenshots.md#e), disabling removeable storage [[f]](/screenshots.md#f), account lockout protocols [[g]](/screenshots.md#g)

## Secondary Concepts Learned

- Utilizing a VM environment through VMWare
- Installing Windows Server 2022 on a VM
- Installing Windows 10 Enterprise on a VM
- Utilizing Server Manager on Windows Server to manage services and features
- Creating documentation files using markdown
- Utilizing Git and GitHub to document changes
- Configuring IPv4 address settings [[h]](/screenshots.md#h)

## Challenges, Bugs & Fixes

- When I first added GPOs to my domain, they were affecting my administrator login as well (restricted my ability to access control panel features on domain controller account)
> GPO Troubleshooting:
> 1. Opened Active Directory Users & Computers to verify that the domain controller machine was listed within the domain controller OU
> 2. Opened Group Policy Management to verify that GPOs were not being applied to domain controller  
>   a. GPOs were being applied to all ['Authenticated Users'](/screenshots.md#gpo-troubleshooting-a) by default (included domain controller)  
>   b. Found a [microsoft documentation page][gpo-troubleshooting-microsoft-docs-solution] detailing security groups in Active Directory  
>   c. Added new security groups in my respective OUs that will include all users that are not administrators ('Sales', 'Accounting')  
>   d. Removed 'Authenticated Users' and [added all created security groups](/screenshots.md#gpo-troubleshooting-d) to all GPOs  
>   e. Restarted server VM to see if changes worked  
>   f. Solved! (for now)  
>   g. edit - password policy still seems to be applied to domain controller, will research more in the future

## Files

[Screenshots](/screenshots.md)
[Change Log](./notes/change-log.md)  
[Research](./notes/research.md)

## Next Steps

[^1]: Obtained access for VMWare through [Broadcom's][broadcom] free personal/educational access
[^2]: Obtained a [180-day evaluation copy][microsoft-server] for Windows Server 2022
[^3]: Obtained a [90-day free-trial][windows-10-enterprise] for Windows 10 Enterprise.

[broadcom]: https://knowledge.broadcom.com/external/article?articleNumber=368667
[microsoft-server]: https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022
[windows-10-enterprise]: https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise
[gpo-troubleshooting-microsoft-docs-solution]: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups