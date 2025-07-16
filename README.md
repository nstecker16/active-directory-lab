# Active Directory Lab

___Start Date: 6 July 2025___

___End Date: current___

**Note:** [#] refers to the numbered screenshots on the screenshots.md file (you can click on numbers for link navigation to screenshot)

## Objective

Learn basic functions in Active Directory such as creating and modifying groups, users, and devices as well as applying policies and more.

## Setup

1. Created a virtual machine (VM) using VMWare Workstation Pro.[^1]
2. Installed Microsoft Server 2022 on the VM. [^2]
3. Added Active Directory as a feature on the server using Server Manager.

## Key Concepts Learned

- Adding and utilizing Active Directory on Windows Server.
- Creating Organizational Units (OUs) and adding objects to them such as Users, Computers and Servers. [[a]](/screenshots.md#a)
- Creating Security groups.
- Creating Distribution groups.
- Creating Group Policy Objects (GPOs) including: password policies [[b]](/screenshots.md#b), drive mapping preferences [[c]](/screenshots.md#c), desktop wallpaper settings [[d]](/screenshots.md#d), restrict control panel access [[e]](/screenshots.md#e), disabling removeable storage [[f]](/screenshots.md#f), account lockout protocols [[g]](/screenshots.md#g)

## Secondary Concepts Learned

- Utilizing a VM environment through VMWare.
- Installing Windows Server 2022 on a VM.
- Utilizing Server Manager on Windows Server to manage services and features.
- Creating documentation files using markdown.
- Utilizing Git and GitHub to document changes

## Challenges, Bugs & Fixes

## Files

## Next Steps

[^1]: Obtained access for VMWare through [Broadcom's][broadcom] free personal/educational access.
[^2]: Obtained a [180-day evaluation copy][microsoft-server] for Windows Server 2022.

[broadcom]: https://knowledge.broadcom.com/external/article?articleNumber=368667
[microsoft-server]: https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022