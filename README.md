# Active-directory-within-Azure-VMs<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Preparing Active Directory
- Step 2: Deploying Active Directory
- Step 3: Creating Users with Powershell
- Step 4: Group Policy and Managing Accounts

<h2>Preparing Active Directory and Deployment Steps</h2>

<p>

<img src="![image](https://github.com/user-attachments/assets/a4f59af1-6444-4c97-a95e-ad1a2996ad2d)
/>
</p>

</p>
One of the first things to do when preparing Active Directory is to make a VM. (virtual machine) Two of them to be exact. One of these VMs will be the Domain controller which IP addresss will be set to static. This is important because we don't want the private IP address to change. You can do this in Microsoft Azure by going the VM created for domain controller by going to Networking - Network settings - Network interface - ipconfig1   

<p>

</p>
<br />

<p>
<img src="![image](https://cdn.discordapp.com/attachments/400782808970428418/1337880484189048844/Static.JPG?ex=67a90dcc&is=67a7bc4c&hm=7e0314ac95c2d8cdc61ce44e8588e954ef3bef2229e7769946e11cbc6a9aa674&)
" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
