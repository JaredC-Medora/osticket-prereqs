# osticket-prereqs<p align="center">
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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to all required files: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Head to https://portal.azure.com/ and create a Virtual Machine running Windows 10 Pro, Version 22H2 -x64 Gen2. For the Size of the Virtual Machine select one with 2 vCPUs and 8 GiB memory.

Once the Machine is complete copy the Public ip address of the VM and use Remote Desktop Connection (windows) or the Windows app (macOS) to remote into the VM.
</p>
<br />
<h2>Step 2: Prepare the Environment</h2>
 - Download osTicket Installation Files
Download the osTicket-Installation-Files.zip and unzip it on your desktop. The extracted folder should be called osTicket-Installation-Files.


 - Install IIS and Enable CGI Support
To run PHP scripts, you'll need to install IIS (Internet Information Services) and enable CGI:


 - Go to Control Panel > Programs > Turn Windows Features On or Off.
 - Expand World Wide Web Services > Application Development Features, and check CGI.
Install PHP Manager for IIS


 - Navigate to the osTicket-Installation-Files folder and run PHPManagerForIIS_V1.5.0.msi.
Install the Rewrite Module


From the osTicket-Installation-Files folder, run rewrite_amd64_en-US.msi to install the URL Rewrite module for IIS.
<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
