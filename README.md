# Active Directory Simulation in Oracle VirtualBox
![Title Image](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/0f273490-2d38-49e3-a2cb-39faf0a4abe1)


## Summary and Purpose

In this project, Oracle VirtualBox was utilized to create a simulated corporate environment. The environment consisted of a Virtual Machine (VM) running Windows Server 2019, a VM running Windows 10 Pro, and a VM running Ubuntu. The Windows Server 2019 VM served as the Domain Controller and hosted the Active Directory service. A custom PowerShell script was executed to populate Active Directory with 1000 users. Each user was given a fictional name and a default password. The Windows 10 Pro VM and the Ubuntu VM were then configured and joined to the domain. Active Directory was then used to create Organizational Units, Group Policies, and Security Groups. In conclusion, Active Directory was configured to act as a centralized management system for user accounts, computers, and other network resources.

<br />

## Technologies and Components Used:

- Active Directory
- Active Directory Domain Service
- Network Address Translation (NAT)
- Domain Name Service (DNS)
- Dynamic Host Configuration Protocol (DHCP)
- File and Storage Services
- Internet Information Services (IIS)
- PowerShell
- Oracle VirtualBox
- Windows Server 2019
- Windows 10 Pro
- Ubuntu 22.04.1

<br />

## Windows Server 2019 and Active Directory Configuration

Two network adapters were used to separate internal and external traffic.

![1 NIC1](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/f0198477-427b-4784-9031-824a7652671c)
![2 NIC2](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/9fb626b2-f6e4-410f-b32b-e57aed6e9fd2)


The following roles and services for Active Directory and the Domain Controller were configured.

![3 Configurations](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/25d70bde-a64a-4de3-bf8d-4ade4bd69542)


Two custom PowerShell scripts were executed. The first script generated 1000 fictional names.   Ultimately, 1,000 users were created within the matter of minutes. 

![4 Create names](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/e98c7950-3434-4db9-b398-260b29231173)

My name was then placed at the top of the generated file to ensure the next script correctly generated the users within Active Directory.
![5 names list](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/d29ccd07-18c7-4eb3-878c-1090a457355d)

The second script was executed to actually populate Active Directory. This script parsed the names list and created users by using the first letter of the first name and the last name.

![6 PS ScriptCapture](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/5825fdc9-1e0b-4871-9784-dcfc2e730c4a)

The total amount of users, including Active Directory's pre-generated users, was 1,052.
![7 1000 Users, red line bottom left](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/1674806f-4b73-45eb-9800-b1fdde4c5eac)

<br />

## Joining Windows 10 Pro and Ubuntu VMs to the Domain

For both VMs, an ISO image was used to install the operating system on the VM. The Network Adapter was set to "Internal Network" to ensure all network traffic would only flow through the Domain Controller.
On the Windows VM, a local account was created to access the machine. The previously created domain, mydomain.com, was pinged and a connection was verified. The machine was then joined to the domain.
The connection was fully verified by picking five (5) random users and logging into the Windows VM with their credentials. 

![8 client machine connected](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/a1426043-8177-467e-9794-d3c56e85d5b1)
![9 join domain](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/205e0dbb-d0af-49f3-861d-085c8851b359)
![testing](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/f5631d2c-3300-4d89-8a21-b8794c11750e)


The same process and testing was followed for the Ubuntu VM, utilizing the command line interface.

Within the Domain Controller, Active Directory was checked to verify the clients were populated correctly.

![10 leases](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/277aa65a-637b-4482-98aa-4405970db9c5)
![11 computers](https://github.com/TylerDeaver/ActiveDirectory/assets/149614301/0d9283a2-4639-4755-bd18-85fe4cb88e32)  

## Reflection
This project gave me valuable insight into the proper configuration of Active Directory. I was also able to play around within Active Directory and get hands-on experience in a variety of Active Directory's capabilities. I was able to use my previous knowledge of Organizational Units, Group Policies, and Security Groups to leverage more out of this lab. By experimenting with Active Directory, I was able to learn more about the powerful tool and gain further insight into a corporate IT environment.

<br />
