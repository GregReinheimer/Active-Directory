# Active Directory Setup

## Objective

Deploy and configure a Windows Server 2022 domain controller in a virtual lab environment to simulate a small business network. Establish centralized user authentication and network services using Active Directory Domain Services (AD DS), DNS, and DHCP.

## Environment and Tools Used

| Component | Detail |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Client OS | Windows 10 Pro |
| Domain Controller | DC01 |
| Domain | ad.cranburypark.test |
| Networking | NAT and Internal Network (192.186.13.0/24) |
| Server Roles | Active Directory Domain Services (AD DS), DNS, DHCP |
| Administrative Tools | Server Manager, Active Directory Users and Computers (ADUC), DNS Manager, DHCP Manager, Powershell |

DIAGRAM

## ***Steps Performed***

### Part 1: Prepare Windows Server 2022

#### Step 1.1: Rename the server and configure networking

Open the Server Manager, select **Local Server**. Change the computer name to **DC01**. Restart the server. To set up proper network configuration, open the internal network adapter's IPv4 properties. Assign `192.168.13.1`, assign subnet mask `255.255.255.0`. Leave the gateway blank. Set DNS to `192.168.13.1`. Verify the VirtualBox NAT is configured separately.

#### Step 1.2: Verify Network
Open Powershell and **type** `hostname` and `ipconfig /all` to verify hostname of server and all ip configuration (ip address, subnet mask, gateway, and DNS).

PICTURE

 SAMPLE  >**Note**: By adding the Command line column, you can observe the file path for each process's executable file, as well as       any command line options that were used to launch the program. For forensic investigators it can be a valuable source of  detailed information when attempting to analyze and isolate malware that has been running since the start of the system.
 
---
### Part 2: Install Active Directory
---

#### Step 2.1: Install Active Directory Domain Services (AD DS) 

In Server Manager, Select **Manage** --> choose **Roles and Features** from the list. Select **Role Based or feature based installation**. Select **DC01** --> choose **Active Directory Domain Services** from the list. Add any required features. Select **install**.

 PICTURE

---
#### Step 2.2: Promote the Domain Controller

Click the Server Manager notification flag. Select **Promote this server to a domain controller**. Choose **add a new forest**. Enter `ad.cranburypark.test`.
  
---
#### Step 2.3: Verify Domain Controller Options

Check the Forest and Domain functional levels are set to Windows Server 2022. Enable the **DNS Server** and **Global Catalog**. Leave **RODC** disabled. Set a secure DSRM password.

---
#### Step 2.4: Finish Promotion

Review the DNS warnings and confirm the NetBios name. Keep default database, log, and SYSVOL locations. Complete the prequisites check. Install and restart the server.

---
### Part 3: Verify Active Directory
---

#### Step 3.1: Verify ADUC and DNS

On the **Server Manager --> Tools --> Active Directory Users and Computers** confirm `ad.cranburypark.test` exists. Then inspect the default Users and Computers containers. 

>**Note** Leave the built-in system containers and objects intact.

Open **DNS Manager** and confirm the `ad.cranburypark.test` forward lookup zone.

#### Step 3.2: Run Health Checks

Check the domain, DNS zone, and domain controller health using `dcdialog`, `Get-ADDomain`, and `Get-ADForest`. Record any warnings and errors.

---

## Skills Learned

- **Active Directory Administration**: Installed and configured Windows Server 2022 as a domain controller, deploying AD DS to establish centralized domain authentication and management.
- **Network Services Configuration**: Configured DNS, DHCP, static IP addressing, and virtual network adapters to support communication between domain controllers and client computers.
- **Network Troubleshooting and Diagnostics**: Used `ipconfig`, `ping`, `nslookup`, and `dcdiag` to diagnose connectivity issues, verify DNS resolution, and troubleshoot DHCP configuration errors.
  

---
## Troubleshooting Logic??

| Symptoms | Potential Causes | Possible Resolution |
|---|---|---|
|  |  |  |
|  | |  |
|  | |  |


