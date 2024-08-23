<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHPManagerForIIS_V1.5.0.msi
- Rewrite Module (rewrite_amd64_en-US.msi)
- PHP 7.3.8 (unzip and import contents)
- VC_redist.x86.exe
- MySQL 5.5.62 (mysql-5.5.62-win32.msi)

<h2>Installation Steps</h2>
Log into Azure and create a resource group, within it, create a virtual machine with at least 2 VCPUs and name it VM1. Then after the creation of the virtual machine, log into it using Remote Desktop.

We first need to enable IIS in Windows with CGI. Go to Control Panel> Program> Turn Windows features on or off> World Wide Web Services>Web Management Tools> IIS Management Console (tick the box). Also tick CGI and CommonHTTP Featuers. 

![image](https://github.com/user-attachments/assets/4c47f0ef-7cb5-4de9-9083-e24bc562dc53)
  
- Install PHPManagerForIIS_V1.5.0.msi, 
- Install Rewrite Module (rewrite_amd64_en-US.msi)
- Then create a file directory C:\PHP, then download PHP 7.3.8 (unzip and import contents into C:\PHP)
- Now Install VC_redist.x86.exe, Typical Setup>Launch Configuration Wizard> Standard configuration.

Open IIS as an admin and register PHP from within IIS, and reload each time you make changes.
- Install osTicket v1.15.8
- Download osTicket from the Installation Files Folder
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

- Go to sites -> Default -> osTicket
- On the right, click “Browse *:80”

Note that some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
 * Enable: php_imap.dll
 * Enable: php_intl.dll
 * Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All


Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
