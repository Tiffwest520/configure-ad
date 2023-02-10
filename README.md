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

- Setup Resource in Azure
- Ensure Connectivity between the client and Domain Controller
- Install Active Directory
- Create an Admin and Normal User Account in AD
- Join Client-1 to your domain
- Setup Remote Desktop for non-admin users on Client-1
- Create bunch of additional users and attempts to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://imgur.com/OiiFMUv.png" height="80%" width="80%" alt="Azure Steps"/>
</p>
<p>
In Azure we will create a resource group that will host two virtual machines one for the client and one for the Domain Controller. The DC's NIC Private IP will be set to private.
</p>
<br />

<p>
<img src="https://imgur.com/BYj4h9l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Ensure connectiivity between the client and DC. First I pinged the DC's private IP. Following I enabled ICMOv4 in DC's local firewall to see the succesful pings.
</p>
<br />

<p>
<img src="https://imgur.com/aSwkAiI.png" height="80%" width="80%" />
</p>
<p>
In DC-1 install Active Directory domain services. Then set up a new forest domain. Then in AD users and computers create organizational Unit for employees and admins.
</p>
<br />

<p>
<img src="https://imgur.com/kwrr89p.png" height="80%" width="80%" />
</p>
<p>
Join Client-1 to the domain. From the Azure portal I set Client-1's DNS setting to DC's private IP address. Then from Client-1 join it to the domain. 
</p>
<br />

<p>
<img src="https://imgur.com/z9j8sv2.png" height="80%" width="80%" />
</p>
<p>
In DC-1 log in as the admin account that created. Then open Powershell as an admin. Add & run the script to create users.
</p>
<br />

<p>
<img src="https://imgur.com/uDEgMJ0.png" height="80%" width="80%" />
</p>
<p>
Log in to Client-1 as one of the users that was created in Active Directory and verify the user and host.
</p>
<br />
