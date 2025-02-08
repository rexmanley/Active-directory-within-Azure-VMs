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

"![image](https://github.com/user-attachments/assets/a4f59af1-6444-4c97-a95e-ad1a2996ad2d)
/>
</p>

</p>
(PREPARING ACTIVE DIRECTORY)One of the first things to do when preparing Active Directory is to make a VM. (virtual machine) Two of them to be exact. One of these VMs will be the Domain controller which IP addresss will be set to static. This is important because we don't want the private IP address to change. You can do this in Microsoft Azure by going the VM created for domain controller by going to Networking - Network settings - Network interface - ipconfig1. As you can see in the image above if you follow the directory you can then set the domain to static.   

![image](https://github.com/user-attachments/assets/d87ab95b-ab25-4d6b-8193-0384e5c185ac)
</p>
<p>
After the two VMS are set you want to log in to the domain controller. Here we will disable the firewall for the two VMS to connect. You can Start this by right clicking start (in the VM not your desktop) and then clicking "run" once it is up type "wf.msc" (Windows firewall) and then disable it from within. As Shown above. /p>
<br />

<p>
<img src="![image](https://github.com/user-attachments/assets/29268dde-e084-4ddd-9e88-1991ae646014)
" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
