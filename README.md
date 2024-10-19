<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Prepare Virtual Machines in Azure
- Install Microsoft Active Directory to Domain Controller
- 
- 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/b8d9f40e-2c2d-45b0-a5c3-4ebfaaf03e69" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into the VM (Virtual Machine) that was set up to be the Domain Controller and install Active Directory Domain Services. Then promote the VM to become a domain controller by selecting the flag icon at the top of the page and selecting the "promote" option. Finally, setup a new forest with your domain name and then restart the pc. In this tutorial I use "mydomain.com" as placeholder domain name to be used in examples.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/8249da7c-778e-4aa0-b720-9874ee698eb2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Active Directory Users and Computers (ADUC) to create Organizational Units (OU) for the directory. In the image above is an example of an OU being made for employees of an organization.
</p>
<p>
<img src="https://github.com/user-attachments/assets/c01744cb-5f8e-4c4c-91b7-254f01edb7a4" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<p>
Within an OU you can create a umber of different "objects", notice in the example above a User is created within an OU named "_ADMINS". During the User's creation a logon name and password are created and assigned to the object - providing the User with the credentials to log into the organizations domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
