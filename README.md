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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5. Create a Domain Admin user within the domain. Start Menu, Windows Adminstrative Tools, Active Directory Users and Computers  
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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
