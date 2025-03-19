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

- Create the Domain Controller VM (Windows Server 2022) & Client VM (Windows 10)
- Connect the Client-1 VM DNS to the Domain Controller VM
- Install Active Directory Domain Services
- Promote the server to a domain controller
- Create a Domain Admin user
- Add Jane Doe to Domain Admins Security Group
- Join Client-1 to the Domain
- Create a new organizational unit called Clients and add Client-1
- Setup Remote Desktop for non-admin users on Client-1
- Create a bunch of additional users
- Test a new users access

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="935" alt="image" src="https://github.com/user-attachments/assets/144d277d-e6f1-4598-8d4d-7baa71006b60" />

</p>
<p>
1. After we create the Domain Controller and Client VM we want to set the Domain Controller’s NIC Private IP address to be static. We go to Networking, Network Settings, and then configure our Network Interface Card. 
</p>
<br />

<p>
<img width="553" alt="image" src="https://github.com/user-attachments/assets/d9553b51-eece-4d44-a690-0361fe7b8c55" />

</p>
<p>
2. Then we will set Client-1's DNS settings to DC-1's private IP address. After we retrieve DC-1's private IP address in our Client-1 VM we go to Networking, Network settings, click on the Network Interface Card, then go to DNS servers, and go to custom to input DC-1's private IP address.  
</p>
<br />

<p>
<img width="552" alt="image" src="https://github.com/user-attachments/assets/c78b54cf-9c35-4567-beb7-0c29a4c8bf5e" />

</p>
<p>
3. To Install Active Directory Domain Services. We go into the start menu, Server Manager, Add Roles and Features, Server Selection, click on DC-1, the Active Directory Domain Services, and Add Features.
</p>
<br />

<p>
<img width="343" alt="image" src="https://github.com/user-attachments/assets/f9300335-349e-499c-a82b-6ca93ded849c" />

</p>
<p>
4. Promote the server to a domain controller. Add a new forest, and add our Root domain name 'mydomain.com'. To do this in our Server Manager we go to Post-deployment Configuration.
</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/9418b48a-decd-4674-a01e-783767c841bd)
![image](https://github.com/user-attachments/assets/fc7630ef-25fe-4877-835e-5d586b25b814)
![image](https://github.com/user-attachments/assets/602c956b-b85e-4b1f-8946-39f40153a51b)

</p>
<p>
5. Create a Domain Admin user within the domain. Start Menu, Windows Adminstrative Tools, Active Directory Users and Computers, and create an Organizational Unit by right clicking on mydomain and selecting new. Our new admin user is Jane Doe. To create her we go to our _ADMINS folder, right click on New, then User. 
</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/7ad7e362-c456-4f92-aa56-aa71d9242892)

</p>
<p>
6. Add Jane Doe to the Domain Admins Security Group. To do this we right click on Jane's account, go to properties, member of, add, and then type in the object names which is 'domain admins'.
</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/ccd891bc-b41e-4ea4-b350-bb2ea54a8634)

</p>
<p>
7. To join Client-1 to the Domain we go to the start menu, select system, rename this PC, under Computer Name, you click Change, and then you add Client-1 as a member of in the Domain section 'mydomain.com'.
</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/2353dfb4-f7c3-4a93-9642-ed96f60f8fbc)

</p>
<p>
8. Create a new Organizational Unit called Clients. 
</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/95d3bc37-78a0-4827-99b0-76ed22f59bc7)

</p>
<p>
9. Allow non-admin users to join our domain. We go to the Start menu, go to system, Remote Desktop, User Accounts, and then add 'Domain Users'. 
</p>
<br />

<p>
![image](https://github.com/user-attachments/assets/9b74fe11-7591-4dcf-8696-b014a872fda2)

</p>
<p>
10. Create more users for our Active Directory in DC-1. Open Windows Powershell ISE as an admin, copy and paste the script, to get 1000 more users. We can now observe the new users in the Active Directory in the Employees OU. 
</p>
<br />

<p>
<img width="334" alt="image" src="https://github.com/user-attachments/assets/39141f08-da39-4705-9362-6ed721e99d79" />
  
<img width="305" alt="image" src="https://github.com/user-attachments/assets/816c6248-f0f8-44b6-9346-d341362a3067" />

</p>
<p>
11. Login in Client-1 as the new user. 'bat.hop' Opened Powershell to verify that we are a different domain user. For me it's bat.hop
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
