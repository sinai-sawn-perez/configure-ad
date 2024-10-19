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
- Joining Private Domains
- 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/b8d9f40e-2c2d-45b0-a5c3-4ebfaaf03e69" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into the VM (Virtual Machine) that was setup to be the Domain Controller and install Active Directory Domain Services. Then promote the VM to become a domain controller by selecting the flag icon at the top of the page and selecting the "promote" option. Finally, setup a new forest with your domain name and then restart the pc. In this tutorial I use "mydomain.com" as placeholder domain name to be used in examples.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/8249da7c-778e-4aa0-b720-9874ee698eb2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Active Directory Users and Computers (ADUC) to create Organizational Units (OU) for the directory. In the image above is an example of an OU named "_EMPLOYEES" is made for the staff of an organization. 
</p>
<p>
<img src="https://github.com/user-attachments/assets/c01744cb-5f8e-4c4c-91b7-254f01edb7a4" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<p>
Within an OU you can create a umber of different "objects", notice in the example above a User is created within an OU named "_ADMINS". During the User's creation a logon name and password are created and assigned to the object - providing the User with the credentials to log into the organizations domain.
</p>
<p>
<img src="https://github.com/user-attachments/assets/976935e4-ef83-4ee5-aa4c-3f08ff1442df" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
A User's Security Group can also be adjusted within ADUC. Notice in the image shown above that the Jane Doe user created in the preivious example has been added to the "Domain Admins" Security Group. When a user is added or removed from a Security Group their permissions will be altered to match thos of the group they are in.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/e2b5ddbb-8cf0-49f2-8fd8-851b3e9b002a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Make sure that VM inteded to be setup as the Client PC has its DNS settings set to the Domain Controller's Private IP address before continuing. Log into the VM setup to act as the Client and join it to the Domain Controller by opening settings> rename this pc (advanced)> change, then type in the name of the domain you wish to join. Again in the example the placeholder used is "mydomain.com".
</p>
<p>
<img src="https://github.com/user-attachments/assets/548e0711-4737-487a-b6c5-0d2dc77140c3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Domain Controller VM, open ADUC and select the "Computers" folder to confirm the Client VM has been connected to the Domain Controller. The name of the Client PC should appear as shown in the image above.
</p>
<p>
<img src="https://github.com/user-attachments/assets/8db741b5-6f0a-41a0-b26e-cd963889a196" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the systems properties of the Client PC, select "Remote Desktop" and allow "domain users" access to remote desktop. Completing this step grants any normal, non-administrative user the ability to log into the Client PC. In other words, if an organization had computers on-site connected to a Domain Controller any user with a login & password registered to that domain would be able to sign into those computers. To grant these permissions to many systems at once a Group Policy would need to be put in place - this is not covered in this tutorial.
</p>
<br />
