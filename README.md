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

</p>
<p>
Head to https://portal.azure.com/ and create a Virtual Machine running Windows 10 Pro, Version 22H2 -x64 Gen2. For the Size of the Virtual Machine select one with 2 vCPUs and 8 GiB memory.

<img width="979" alt="Screenshot 2025-03-12 at 1 52 44 PM" src="https://github.com/user-attachments/assets/c19669a4-9510-43da-b9d7-1ed66ec7beeb" />


<img width="677" alt="Screenshot 2025-03-12 at 1 53 06 PM" src="https://github.com/user-attachments/assets/e99c8f51-8581-4877-8b74-4fa0fdcfc075" />


<img width="683" alt="Screenshot 2025-03-12 at 1 53 18 PM" src="https://github.com/user-attachments/assets/0b291ee1-d47e-45e7-87ca-56610e3b264b" />



Once the Machine is complete copy the Public ip address of the VM and use Remote Desktop Connection (windows) or the Windows app (macOS) to remote into the VM.
</p>
<br />
<h2>Step 2: Prepare the Environment</h2>


 1. Download osTicket Installation Files
     - Download the osTicket Installation Files.zip and unzip it on your desktop. The extracted folder should be called (osTicket Installation Files).

<img width="761" alt="Screenshot 2025-03-12 at 1 54 51 PM" src="https://github.com/user-attachments/assets/1b8eda47-f4e5-4409-b884-1ddb1a260209" />

 2. Install IIS and Enable CGI Support
    To run PHP scripts, you'll need to install IIS (Internet Information Services) and enable CGI:
     - Go to Control Panel > Programs > Turn Windows Features On or Off.
     - Expand World Wide Web Services > Application Development Features, and check CGI.

<img width="1013" alt="Screenshot 2025-03-12 at 1 55 58 PM" src="https://github.com/user-attachments/assets/fcc54877-f99c-4e14-aa0a-85f996665085" />

<img width="475" alt="Screenshot 2025-03-12 at 1 56 23 PM" src="https://github.com/user-attachments/assets/3773f571-9962-48f0-9fc6-7635c3c3e23d" />

<img width="171" alt="Screenshot 2025-03-12 at 1 56 35 PM" src="https://github.com/user-attachments/assets/ee21ae7f-a4cc-4065-8327-5f5512c39e94" />

<img width="352" alt="Screenshot 2025-03-12 at 1 57 19 PM" src="https://github.com/user-attachments/assets/0d774028-6dbe-4806-9354-a19859e93948" />

<img width="340" alt="Screenshot 2025-03-12 at 1 57 39 PM" src="https://github.com/user-attachments/assets/9087107d-0f0d-4162-8073-8b5edaee3c13" />

 3. Install PHP Manager for IIS
     - Navigate to the osTicket-Installation-Files folder and run PHPManagerForIIS_V1.5.0.msi.

<img width="448" alt="Screenshot 2025-03-12 at 1 58 40 PM" src="https://github.com/user-attachments/assets/10462a00-8d2f-4152-bd8e-136d57b54e4b" />

 4. Install the Rewrite Module
     - From the osTicket-Installation-Files folder, run rewrite_amd64_en-US.msi to install the URL Rewrite module for IIS.

<img width="445" alt="Screenshot 2025-03-12 at 1 59 07 PM" src="https://github.com/user-attachments/assets/1bce391b-3b2a-4974-bc08-53f287c582ae" />

<p>

</p>
<p>
<h2>Step 3: Install PHP and Dependencies</h2>


 1. Create a PHP Directory
     - Create a directory C:\PHP on your system.
 
 <img width="713" alt="Screenshot 2025-03-12 at 1 59 29 PM" src="https://github.com/user-attachments/assets/59cf2233-9017-4393-8b10-45fd361dfa43" />

 2. Install PHP
     - From the osTicket-Installation-Files folder, unzip php-7.3.8-nts-Win32-VC15-x86.zip into C:\PHP.

<img width="553" alt="Screenshot 2025-03-12 at 2 00 14 PM" src="https://github.com/user-attachments/assets/a6da174c-ee26-4ad2-8f09-7bc30d0de1b6" />

 3. Install Visual C++ Redistributable
     - From the osTicket-Installation-Files folder, run VC_redist.x86.exe to install the required C++ redistributable.

 <img width="429" alt="Screenshot 2025-03-12 at 2 00 40 PM" src="https://github.com/user-attachments/assets/fa7b60c5-7968-4ab8-8fce-3d488c80d62a" />

 4. Install MySQL
     - From the osTicket-Installation-Files folder, run mysql-5.5.62-win32.msi.
  <img width="444" alt="Screenshot 2025-03-12 at 2 00 57 PM" src="https://github.com/user-attachments/assets/a3b000f4-ac37-4111-ae29-59942c9d31a7" />

 - Choose Typical Setup and Launch Configuration Wizard after installation.
 - Set the MySQL Password. (For this example I used ROOT)

<img width="450" alt="Screenshot 2025-03-12 at 2 01 12 PM" src="https://github.com/user-attachments/assets/85965958-d8c9-4cda-95f1-08066ac8aa1a" />

  <h2>Step 4: Configure IIS and PHP</h2> 
   
   
  1. Register PHP in IIS
     - Open IIS as an Administrator.
   <img width="310" alt="Screenshot 2025-03-12 at 2 01 42 PM" src="https://github.com/user-attachments/assets/a7e48a7f-80f8-43d4-9def-00e5f2facdb9" />

   - In IIS, go to PHP Manager, click Register PHP, and point it to C:\PHP\php-cgi.exe.
  <img width="457" alt="Screenshot 2025-03-12 at 2 02 12 PM" src="https://github.com/user-attachments/assets/61635f21-822b-4f1b-8278-6d34b4cb5038" />

  2. Restart IIS
     - In IIS, click Stop and then Start to reload the server with the new configurations.
<img width="180" alt="Screenshot 2025-03-12 at 2 02 29 PM" src="https://github.com/user-attachments/assets/d17cc35f-19d3-45f1-8c4c-2470e519fc15" />




<h2>Step 5: Intall osTicket</h2>
  
  
  1. Unzip osTicket Files
      - From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip.
      - Copy the upload folder to C:\inetpub\wwwroot.

<img width="1013" alt="Screenshot 2025-03-12 at 2 03 43 PM" src="https://github.com/user-attachments/assets/8d655c9e-03fa-4303-a376-ef0275543a3c" />

  2. Rename the upload Folder
      - In C:\inetpub\wwwroot, rename the upload folder to osTicket.

<img width="622" alt="Screenshot 2025-03-12 at 2 04 03 PM" src="https://github.com/user-attachments/assets/5f50c9bb-9390-44c0-8bea-53c71634c763" />

  3. Restart IIS Again
      - Stop and start IIS to ensure the new changes are applied.

<img width="180" alt="Screenshot 2025-03-12 at 2 02 29 PM" src="https://github.com/user-attachments/assets/de5c5da7-750c-4429-9c7b-c4027b20609f" />


<h2>Step 6: Configure PHP Extensions</h2>


1. Enable Required PHP Extensions
  - In IIS, under Sites > Default > osTicket, double-click on PHP Manager.
<img width="181" alt="Screenshot 2025-03-12 at 2 05 14 PM" src="https://github.com/user-attachments/assets/ab37c145-d426-4ece-be2d-51e768081f28" />

- Click Enable or disable an extension and enable the following extensions:
  - php_imap.dll
  - php_intl.dll
  - php_opcache.dll

<img width="200" alt="Screenshot 2025-03-12 at 2 06 07 PM" src="https://github.com/user-attachments/assets/092b179d-c13c-49a6-b1b3-201265fe69f5" />
<img width="198" alt="Screenshot 2025-03-12 at 2 06 37 PM" src="https://github.com/user-attachments/assets/20408e6d-775c-4ed7-aac7-034da8f936c6" />
<img width="199" alt="Screenshot 2025-03-12 at 2 10 51 PM" src="https://github.com/user-attachments/assets/d1154aec-c9ae-4b4c-bcf5-2aaac0ef44b2" />
<img width="181" alt="Screenshot 2025-03-12 at 2 06 44 PM" src="https://github.com/user-attachments/assets/b1356897-1456-4284-93fd-d7f1c0fcd779" />

3. Refresh the osTicket Site
    - Refresh the osTicket site in your browser to apply the changes.

<img width="740" alt="Screenshot 2025-03-12 at 2 11 06 PM" src="https://github.com/user-attachments/assets/99ef5461-9e75-4e50-83ee-f6cca4ee884f" />




<h2>Step 7: Final Configuration</h2>


1. Rename and Set Permissions for Configuration File
     - Rename ost-sampleconfig.php to ost-config.php in the directory C:\inetpub\wwwroot\osTicket\include.

<img width="129" alt="Screenshot 2025-03-12 at 2 11 50 PM" src="https://github.com/user-attachments/assets/95d313bf-d81b-464f-bdc3-1aa6866fd003" />

  - Set file permissions for ost-config.php:
     
  - Right-click on ost-config.php, select Properties.
     
      <img width="251" alt="Screenshot 2025-03-12 at 2 12 07 PM" src="https://github.com/user-attachments/assets/1be4afb2-9fcd-451b-88ec-583753b6675b" />
 
  - Go to Security > Advanced, disable inheritance, and remove all existing permissions.
    
     <img width="691" alt="Screenshot 2025-03-12 at 2 12 24 PM" src="https://github.com/user-attachments/assets/27941a52-ce61-444e-a8b8-e9258e952e9a" />

  - Set new permissions for Everyone with Full Control.

<img width="826" alt="Screenshot 2025-03-12 at 2 13 00 PM" src="https://github.com/user-attachments/assets/084e125b-ce86-4e86-960e-9a08d96d2181" />


3. Set Up osTicket in the Browser
   - Open a browser and go to http://localhost/osTicket.
   - Complete the osTicket setup by providing the following details:
      - Helpdesk Name: Your desired name.
      - Default Email: The email that will receive customer emails.

<img width="1289" alt="Screenshot 2025-03-12 at 2 13 45 PM" src="https://github.com/user-attachments/assets/0d7cfca6-c664-49d4-8fe3-88f632cdc8eb" />



<h2>Step 8: Set Up MySQL Database</h2>


1. Install HeidiSQL
   - From the osTicket-Installation-Files folder, install HeidiSQL.

<img width="537" alt="Screenshot 2025-03-12 at 2 14 06 PM" src="https://github.com/user-attachments/assets/77674dfe-ab5a-4b80-9fcf-ff7c46e91560" />

   - Open HeidiSQL and create a new session using the following credentials:
      - Username: root
      - Password: root
  
   <img width="616" alt="Screenshot 2025-03-12 at 2 14 34 PM" src="https://github.com/user-attachments/assets/8045de15-a51d-4ceb-9173-a3518f0fa88d" />

   - Connect to the session and create a new database called osTicket.
<img width="842" alt="Screenshot 2025-03-12 at 2 14 58 PM" src="https://github.com/user-attachments/assets/23ee8e65-2e96-45f1-a3a5-5f951d2feab0" />
<img width="286" alt="Screenshot 2025-03-12 at 2 15 19 PM" src="https://github.com/user-attachments/assets/9047ceda-9f80-462e-94c8-586a36324313" />

3. Continue osTicket Setup
   - Back in the browser, enter the following database information:
     - MySQL Database: osTicket
     - MySQL Username: root
     - MySQL Password: root
<img width="743" alt="Screenshot 2025-03-12 at 2 15 36 PM" src="https://github.com/user-attachments/assets/a89c1bd5-db01-4551-999a-ae2bd5b28a2d" />

 - Click Install Now! to finish the installation.

<img width="739" alt="Screenshot 2025-03-12 at 2 15 50 PM" src="https://github.com/user-attachments/assets/b6486d74-2756-41a7-91bd-7756947249ca" />



<h2>Step 9: Access osTicket</h2>


1. Helpdesk Login Page
   After installation, navigate to the helpdesk login page:

   - URL: http://localhost/osTicket/scp/login.php

<img width="381" alt="Screenshot 2025-03-12 at 2 16 12 PM" src="https://github.com/user-attachments/assets/c09115e4-4b6c-4228-8e60-deeccaf30971" />
<img width="1295" alt="Screenshot 2025-03-12 at 2 16 28 PM" src="https://github.com/user-attachments/assets/b024a887-1063-4c5d-91c3-61b6e57acaae" />

2. End User osTicket URL
   The URL for your end users to access osTicket is:

   - URL: http://localhost/osTicket/
<img width="1296" alt="Screenshot 2025-03-12 at 2 16 49 PM" src="https://github.com/user-attachments/assets/71287b9c-f2cd-4577-95ec-7681eb1a9d3b" />

</p>
<br />

<p>

</p>
<p>
<h2>PLEASE DO NOT FORGET TO PAUSE OR DELETE ALL AZURE VM's TO REDUCE COSTS/CHARGES</h2>
</p>
<br />
