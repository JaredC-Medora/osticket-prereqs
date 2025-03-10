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


 1. Download osTicket Installation Files
     - Download the osTicket Installation Files.zip and unzip it on your desktop. The extracted folder should be called (osTicket Installation Files).

 2. Install IIS and Enable CGI Support
    To run PHP scripts, you'll need to install IIS (Internet Information Services) and enable CGI:
     - Go to Control Panel > Programs > Turn Windows Features On or Off.
     - Expand World Wide Web Services > Application Development Features, and check CGI.

 3. Install PHP Manager for IIS
     - Navigate to the osTicket-Installation-Files folder and run PHPManagerForIIS_V1.5.0.msi.

 4. Install the Rewrite Module
     - From the osTicket-Installation-Files folder, run rewrite_amd64_en-US.msi to install the URL Rewrite module for IIS.
<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>Step 3: Install PHP and Dependencies</h2>


 1. Create a PHP Directory
     - Create a directory C:\PHP on your system.
 
 2. Install PHP
     - From the osTicket-Installation-Files folder, unzip php-7.3.8-nts-Win32-VC15-x86.zip into C:\PHP.

 3. Install Visual C++ Redistributable
     - From the osTicket-Installation-Files folder, run VC_redist.x86.exe to install the required C++ redistributable.
 
 4. Install MySQL
     - From the osTicket-Installation-Files folder, run mysql-5.5.62-win32.msi.
     - Choose Typical Setup and Launch Configuration Wizard after installation.
     - Set the MySQL Password. (For this example I used ROOT)




  <h2>Step 4: Configure IIS and PHP</h2> 
   
   
  1. Register PHP in IIS
     - Open IIS as an Administrator.
     - In IIS, go to PHP Manager, click Register PHP, and point it to C:\PHP\php-cgi.exe.
  
  2. Restart IIS
     - In IIS, click Stop and then Start to reload the server with the new configurations.




<h2>Step 5: Intall osTicket</h2>
  
  
  1. Unzip osTicket Files
      - From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip.
      - Copy the upload folder to C:\inetpub\wwwroot.

  2. Rename the upload Folder
      - In C:\inetpub\wwwroot, rename the upload folder to osTicket.

  3. Restart IIS Again
      - Stop and start IIS to ensure the new changes are applied.



<h2>Step 6: Configure PHP Extensions</h2>


1. Enable Required PHP Extensions
    - In IIS, under Sites > Default > osTicket, double-click on PHP Manager.
    - Click Enable or disable an extension and enable the following extensions:
       - php_imap.dll
       - php_intl.dll
       - php_opcache.dll

2. Refresh the osTicket Site
    - Refresh the osTicket site in your browser to apply the changes.




<h2>Step 7: Final Configuration</h2>


1. Rename and Set Permissions for Configuration File
    - Rename ost-sampleconfig.php to ost-config.php in the directory C:\inetpub\wwwroot\osTicket\include.
    - Set file permissions for ost-config.php:
      - Right-click on ost-config.php, select Properties.
      - Go to Security > Advanced, disable inheritance, and remove all existing permissions.
      - Set new permissions for Everyone with Full Control.

2. Set Up osTicket in the Browser
   - Open a browser and go to http://localhost/osTicket.
   - Complete the osTicket setup by providing the following details:
      - Helpdesk Name: Your desired name.
      - Default Email: The email that will receive customer emails.




<h2>Step 8: Set Up MySQL Database</h2>


1. Install HeidiSQL
   - From the osTicket-Installation-Files folder, install HeidiSQL.
   - Open HeidiSQL and create a new session using the following credentials:
      - Username: root
      - Password: root
   - Connect to the session and create a new database called osTicket.

2. Continue osTicket Setup
   - Back in the browser, enter the following database information:
     - MySQL Database: osTicket
     - MySQL Username: root
     - MySQL Password: root
   - Click Install Now! to finish the installation.




<h2>Step 9: Access osTicket</h2>


1. Helpdesk Login Page
   After installation, navigate to the helpdesk login page:

   - URL: http://localhost/osTicket/scp/login.php

2. End User osTicket URL
   The URL for your end users to access osTicket is:

   - URL: http://localhost/osTicket/
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
