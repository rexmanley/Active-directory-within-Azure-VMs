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
After the two VMS are set you want to log in to the domain controller. Here we will disable the firewall for the two VMS to connect. You can Start this by right clicking start (in the VM not your desktop) and then clicking "run" once it is up type "wf.msc" (Windows firewall) and then disable it from within. As Shown above. 

![image](https://github.com/user-attachments/assets/5c146a0e-c85b-4aa3-8d04-90393649c961)

Lastly we need to join the domain from the client VM to the domain controller. We can do this by changing the DNS servers to the private IP address. The route for this in Microsoft Azure is going to the Virtual machine - client-1 (the VM that is not the domain controller) -Network settings  and then changinging the DNS servers to custom so we can put our private IP address.(shown above)

![image](https://github.com/user-attachments/assets/4dbe9067-5372-4045-96aa-bb1326e7844d)

(DEPLOYING ACTIVE DIRECTORY) To deploy active directory we have to install Active directory domain services. To do so we will do it in the domain controller VM by going to the server manager. (shown above)

Now we have to setup the domain controller as a new forest "mydomain.com". We can do this in the same place as the server manager.Now that it is installed you now have to create a domain admin user within the domain.
![image](https://github.com/user-attachments/assets/71db4271-fc00-4cca-9dfc-9c4754a3ca3b)

In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”
Create a new OU named “_ADMINS”
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin” / Cyberlab123!
Add jane_admin to the “Domain Admins” Security Group
Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”
User jane_admin as your admin account from now on 
(the final product should look like the image above)
![image](https://github.com/user-attachments/assets/b2d50843-03d5-4531-b40f-051a79e2b86d)

Now we will Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)
Login to the Domain Controller and verify Client-1 shows up in ADUC
Create a new OU named “_CLIENTS” and drag Client-1 into there
(example above)

![image](https://github.com/user-attachments/assets/d3d800df-7631-4dee-9195-e761f1cf1a3e)

Setup Remote Desktop for non-administrative users on Client-1
Log into Client-1 as mydomain.com\jane_admin
Open system properties
Click “Remote Desktop”
Allow “domain users” access to remote desktop
You can now log into Client-1 as a normal, non-administrative user now
(example above)
![image](https://github.com/user-attachments/assets/0233cbed-63f2-4a7f-8727-2fb6bc12b35a)

(CREATING USERS WITH POWERSHELL)Create a bunch of additional users and attempt to log into client-1 with one of the users
—
Login to DC-1 as jane_admin
Open PowerShell_ise as an administrator
Create a new File and paste the contents of the script(https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1) provide into it
Run the script and observe the accounts being created
When finished, open ADUC and observe the accounts in the appropriate OU　(_EMPLOYEES)
attempt to log into Client-1 with one of the accounts (take note of the password in the script)
when it is finished it should be like the example above 






