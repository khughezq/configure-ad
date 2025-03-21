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
<img width="467" alt="image" src="https://github.com/user-attachments/assets/3363e5fd-aa49-4051-9bf5-a7ec8b59d568" />



<img width="318" alt="image" src="https://github.com/user-attachments/assets/43c08dd9-cd17-4bd6-907a-b1261ac3e388" />


<img width="247" alt="image" src="https://github.com/user-attachments/assets/e24014e3-af31-4509-9570-e8a40e0bd577" />


</p>
<p>
5. Create a Domain Admin user within the domain. Start Menu, Windows Adminstrative Tools, Active Directory Users and Computers, and create an Organizational Unit by right clicking on mydomain and selecting new. Our new admin user is Jane Doe. To create her we go to our _ADMINS folder, right click on New, then User. 
</p>
<br />

<p>
<img width="299" alt="image" src="https://github.com/user-attachments/assets/a6cdcb4c-bb1b-4c48-be7c-b6f9906deb71" />

</p>
<p>
6. Add Jane Doe to the Domain Admins Security Group. To do this we right click on Jane's account, go to properties, member of, add, and then type in the object names which is 'domain admins'.
</p>
<br />

<p>
<img width="534" alt="image" src="https://github.com/user-attachments/assets/0f2d92da-4266-4bba-9621-e0e28bd499f3" />

</p>
<p>
7. To join Client-1 to the Domain we go to the start menu, select system, rename this PC, under Computer Name, you click Change, and then you add Client-1 as a member of in the Domain section 'mydomain.com'.
</p>
<br />

<p>
<img width="368" alt="image" src="https://github.com/user-attachments/assets/407b824d-e635-4fd8-ad79-9e0bfcf67600" />

</p>
<p>
8. Create a new Organizational Unit called Clients. 
</p>
<br />

<p>
<img width="335" alt="image" src="https://github.com/user-attachments/assets/335fd3d6-4c9e-46ee-9765-788bda6d65ec" />

</p>
<p>
9. Allow non-admin users to join our domain. We go to the Start menu, go to system, Remote Desktop, User Accounts, and then add 'Domain Users'. 
</p>
<br />

<p>
<img width="382" alt="image" src="https://github.com/user-attachments/assets/5148b367-f171-442f-9cc3-f9868fc4d73d" />


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
11. Finally, login in Client-1 as the new user. 'bat.hop' Opened Powershell to verify that we are a different domain user. For me it's bat.hop
</p>
<br />

