<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Set up virtual machine in azure 
- Install the osTicket requirements 
- Install osTicket itself


<h2>Installation Steps</h2>

<img width="717" alt="image" src="https://github.com/Scott8790/osticket-prereqs/assets/172638339/454d98f5-4f70-476a-af9c-986299c1daa1">


</p>
<p>
Within your created resource group, you create the virtual machine. Make sure to fill out all the necessary fields such as OS, location, size, etc. The more vCPUs the VM has, the better the performance you will receive from it.
<br />

<p>
<img width="403" alt="image" src="https://github.com/Scott8790/osticket-prereqs/assets/172638339/522dcdcc-7ea2-4622-acb0-157388798c52">

<img width="834" alt="IIS osTicket prereq" src="https://github.com/Scott8790/osticket-prereqs/assets/172638339/2ac7c2e1-52fa-4e76-9130-b0b0f5732430">

</p>
<p>
Prereqs for osTicket Install:
- Enable IIS in Windows with CGI
- Install PHP Manager for IIS
- Install the Rewrite Module
- Create the directory C:\PHP
- Download PHP file and unzip contents into C:\PHP
- Install VC redist file
- Install MySQL file
- Open IIS as Admin
- Register PHP from within IIS


</p>
<br />

<p>
<img width="584" alt="IIS osTicket install" src="https://github.com/Scott8790/osticket-prereqs/assets/172638339/e5ebf372-3b3b-4c0d-b961-1d3e3501f487">

</p>
<img width="1619" alt="IIS osTicket install2" src="https://github.com/Scott8790/osticket-prereqs/assets/172638339/005ecef1-7137-4275-b3fb-a8db42bfcdc5">

<p>
Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the Installation Files, download and install HeidiSQL.
Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”

Continue Setting up osticket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”

</p>
<br /># osticket-prereqs
