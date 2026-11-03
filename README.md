# Active Directory

## Project Overview

Designed and configured a simulated business IT environment using Windows Server 2022, Active Directory Domain Services, Windows 10, and Oracle VirtualBox.

The lab simulates centralized IT administration for a fictional company with multiple departments, employee accounts, security groups, organizations units, and Windows workstations.

The project focuses on Active Directory administration, Group Policy management, delegated Helpdesk responsibilities, user support, and network troubleshooting.

## Project Objectives

- Deploy and configure Active Directory Domain Services
- Create organizational units, user accounts, and security groups
- Configure delegated Helpdesk permissions
- Implement and test Group Policy Objects
- Join Windows clients to the domain
- Department File Shares
- Network Drive Mapping
- Simulate common IT Helpdesk support requests

## Lab Environment

| Component                                        |            Configuration         |
|-----------------------------------------------|----------------------------|
| Hypervisor                       | Oracle VirtualBox |
| Server OS       | Windows Server 2022|
| Client OS                    | Windows 10 |
| Domain                     | ad.cranburypark.test |
| Domain Controller                    | DC01 |
| Domain Services                   | AD DS, DNS, DHCP |
| Network                    | VirtualBox NAT and Internal Network |
| Internal Server IP                   | 192.168.13.1 |

## Project Sections

1. **Active Directory Setup:** Domain controller configuration and verification.
2. **Orgnaizational Units, Users and Groups**: Department structure and account management.
3. **Helpdesk Delegation:** Password reset permissions and least privilege administration.
4. **Group Policy Management:** Workstation security and department restrictions.
5. **File Sharing and Network Map Drive:** Creation of department shares with access controlled through security groups.
6. **IT Helpdesk Tickets:** Simulated end user support incidents and resolutions.

