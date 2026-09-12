# Windows IT Help Desk & Active Directory Home Lab

## Project Overview

This project is a hands-on Windows IT Help Desk home lab designed to simulate a small business Windows domain environment.

I built the lab using Windows Server 2022 and Windows 11 virtual machines running in UTM on macOS. The project allowed me to practice common tasks performed in Help Desk, Desktop Support, and junior Systems Administration roles.

Throughout the lab, I configured Active Directory, user accounts, security groups, permissions, Group Policy, network shares, and endpoint management with Action1.

I also troubleshot several real configuration issues involving authentication, permissions, SMB connectivity, Windows Firewall, and endpoint deployment.

---

## Technologies Used

- Windows Server 2022
- Windows 11
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy
- NTFS Permissions
- SMB / Windows File Sharing
- Windows Administrative Shares
- Action1 Endpoint Management
- UTM Virtualization
- macOS

---

## Lab Environment

| Component | Configuration |
|---|---|
| Active Directory Domain | `coco.coco` |
| Domain Controller | `DC-01.coco.coco` |
| Windows 11 Client | `Desktop01.coco.coco` |
| Example Domain Users | Toto, Sammy |
| Endpoint Management | Action1 |

### Lab Architecture

```text
                       coco.coco
                           |
              +------------+------------+
              |                         |
            DC-01                   Desktop01
      Windows Server 2022             Windows 11
              |                         |
      Active Directory              Domain Joined
      DNS                           Action1 Agent
      Group Policy
      File Sharing
      Action1 Deployer

1. Windows Server Configuration
Configured Windows Server 2022 as the central server for the lab environment.
The server was used to provide Active Directory, DNS, Group Policy, shared resources, and administrative services for the Windows 11 client.

2. Active Directory Domain Services
Configured Active Directory Domain Services and created the domain:
coco.coco
The Windows Server system was configured as the Domain Controller for the lab.
I used Active Directory Users and Computers to manage users, computers, and security groups.

3. Users and Security Groups
Created domain users and organized access using Active Directory security groups.
Example users included:
- Toto
- Sammy
Instead of assigning permissions individually to every user, security groups were used to simplify access management.

4. NTFS and Folder Permissions
Configured NTFS permissions for shared folders.
This included:
- Assigning access through security groups
- Managing Modify, Read, and Write permissions
- Removing unnecessary broad user permissions
- Working with permission inheritance
- Testing access using different domain accounts

5. Group Policy
Used Group Policy Management to configure settings centrally for domain users and computers.
This demonstrated how administrators can manage workstation behavior without configuring each computer manually.

6. Network File Sharing
Configured and tested shared folders between the Windows Server and Windows 11 client.
I practiced:
- SMB file sharing
- Network paths
- Mapped network drives
- Share permissions
- NTFS permissions
- Testing access using domain accounts

7. Windows 11 Domain Client
Joined the Windows 11 workstation to the coco.coco Active Directory domain.
Domain users such as Toto and Sammy were able to authenticate using Active Directory accounts.
I also worked with Windows administrative shares such as:
\\Desktop01\C$
This provided experience with remotely accessing a Windows workstation using administrative credentials.

8. Action1 Endpoint Management
Configured Action1 for endpoint management and patch visibility.
The environment included:
- DC-01.coco.coco
- Desktop01.coco.coco
Both systems successfully connected to the Action1 management platform.
I configured the Action1 Deployer on the server and used Action1 to view managed endpoints, system status, vulnerabilities, updates, and reboot requirements.

Troubleshooting Experience
A major part of this project involved troubleshooting configuration problems rather than only completing successful setup steps.
Some of the issues I worked through included:
- Domain login problems
- Standard user vs administrator permissions
- NTFS permission inheritance
- Security group permissions
- Shared-folder access
- Network drive mapping
- SMB connectivity
- Windows Firewall rules
- Administrative share access
- Action1 agent deployment
- Action1 endpoint connectivity
Working through these issues helped me better understand how Windows infrastructure components interact in a domain environment.
Skills Demonstrated
- Active Directory Administration
- Windows Server Administration
- Windows 11 Administration
- Domain User Management
- Security Group Management
- DNS
- Group Policy
- NTFS Permissions
- SMB File Sharing
- Network Drive Mapping
- Windows Firewall
- Remote Administration
- Endpoint Management
- Patch Management
- Action1
- IT Troubleshooting
Key Takeaways
This lab gave me practical experience working with technologies commonly used in:
- IT Help Desk
- IT Support
- Desktop Support
- Windows Administration
- Junior Systems Administration
The most valuable part of the project was learning how to troubleshoot issues when configurations did not work immediately and understanding why a particular fix solved the problem.
Future Improvements
I plan to continue expanding this lab with:
- PowerShell automation
- Microsoft Entra ID
- Microsoft Intune
- Automated user provisioning
- Software deployment
- Additional Windows client machines
- Ticketing system integration
- More advanced Group Policy configurations
