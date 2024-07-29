<p align="center">
<img src="https://www.synaxiom.com/wp-content/uploads/2016/06/osticket.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites, and Installation</h1>
This guide details the necessary requirements and steps for installing osTicket, an open-source help desk ticketing system.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- VC_redistx86
- MySQL 5.5.62
- Rewrite Module
- Heidi SQL

<h2>Installation Steps</h2>
<p>
<h3>Create a Virtual Machine on Azure</h3>
The first step is to create a virtual machine  in Azure. 
Choose the image or base operating machine as Windows 10 Pro, version 22H2.</p>
<p>
<img width="1128" alt="image" src="https://github.com/user-attachments/assets/d9f44a8b-69c6-4ebd-8b36-ae969a288c51">
</p>
<h3>Connect to your VM using the Remote Desktop Connection app</h3>
<p>Open your Remote Desktop Connection app and paste the VM's IP and login with the same login credentials used to create the VM.</p>
<img width="306" alt="image" src="https://github.com/user-attachments/assets/586e3072-9c48-4adc-91d3-e60fe2d40f50">

</p>
<h3>Enable IIS </h3>
<p> Once the VM is open, we will have to install / enable IIS. Go to the Control Panel and open the programs applet. Under programs, select "Turn Windows features on or off".</p>
<p> 
  <img width="552" alt="CONTROL PANEL PROGRAMS" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/52defb88-4165-4b34-bbea-8292bc2890c8">
</p>
<p>Then you will have to enable and expand the following features:</p>
<p>
  <img width="295" alt="Checklist 2" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/0b7b096f-43e7-47a8-a3ef-5500a360453d">
</p>
<p> [X] Internet Information Services</p>
<p>[X] Web Management Tools </p>
<p>[X] IIS Management Console </p>
<p>[X] World Wide Web Services  </p>
<p>[X] Application Development Features </p>
<p>[X] CGI</p>
<p>[X] Common HTTP Features</p>
<p> Click okay and the features should be enabled.</p>
<p> <strong> NOTE: To quickly test if the changes were applied succesfully, simply type 127.0.0.1 on your browser and the page below should appear. </strong></p>
<img width="1094" alt="WINDOWS IIS" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/4836fb28-6fcf-403d-853b-f412c707295c">

<h3>Download and Install PHP Manager</h3>
<p> Simply download and install PHP manager from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a>(PHPManagerForIIS_V1.5.0.msi) 
</p>
<p><img width="386" alt="PHP Manager" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/566a1c1c-3731-4ff7-a74c-10a21b84a851">
</p> 
<h3>Download and Install the Rewrite Module</h3>
<p> Download and install the rewrite module (rewrite_amd64_en-US.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a> </p>
<p><img width="386" alt="rewrite module" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/177cc396-71e3-4658-9084-3e6fae94c1a5"></p>
<h3>Create a new directory</h3>
<p>Proceed to File Explorer and create the directory C:\PHP </p>
<img width="647" alt="PHP" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/683aa120-d73c-4bce-bf6d-f58309fdac5c">

<h3>Download and install php-7.3.8-nts-Win32-VC15-x86.zip </h3>
<p> Download and install php-7.3.8-nts-Win32-VC15-x86.zip from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a> and unzip the contents into the newly created C:\PHP </p>
<img width="631" alt="PHP zip" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/b43949f3-78a7-4ab8-a526-dfd4f159d2d6">
<h3>Download and install VC_redist.x86.exe </h3>
<h3>Download and install MySQL 5.5.62 </h3>
<p> Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a>  and select the following configurations; </p>
<p> [X] Typical Setup</p>
<p>[X] Launch Configuration Wizard after install </p>
<p>[X]Standard Configuration 
</p>
<img width="383" alt="mysql" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/964a5ada-7d58-4efd-a0f2-6744610d999d">
<h3>Launch IIS as an administrator</h3>
<p> Search for IIS in the windows search bar and right click it and select open as administrator</p>
<h3>Register PHP Manager </h3>
<img width="682" alt="PHP registration 2" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/a3282eb4-90ea-474b-9259-33bfa4d01957">
<p><strong> NOTE: Registration will require you to provide a path to "php-cgie.exe". Simply lead it to the PHP folder previously created and you will find the file it is asking for. 
</strong></p>
<img width="623" alt="PHP path " src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/ac6d2463-c9ef-4803-b3d6-3e5d4a9bc177">
<h3>Restart the IIS server</h3>
<p> The restart button can be found on the right side of the window.</p>
<img width="623" alt="Restart IIS" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/89c60a3c-2556-4909-ad78-4ae501b38da1">
<h3>Download and install osTicket</h3>
<p> Download and install osTicket v1.15.8 from the installation files and extract the contents to c:\inetpub\wwwroot </p>
<img width="547" alt="inetpub" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/bea57cd3-27f4-4564-9cb4-1bfd7492b6ca">
<p> Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”</p>
<h3>Restart the IIS server again.</h3>
<img width="623" alt="Restart IIS" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/89c60a3c-2556-4909-ad78-4ae501b38da1">
<h3>Launch osTicket </h3>
<p>On the left hand side of IIS, Expand on the VM name -> Sites - > Default Website -> osTicket </p>
<img width="623" alt="osTicket" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/93165771-1d49-430c-a66a-cc2cf3c87e93">
<p><strong>NOTE: Make sure to click on osTicket</strong></p>
<h3>Click on Browse *80 to launch osTicket</h3>
<p> On the right side of the window, click on browse *80 </p>
<img width="623" alt="browse80" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/53e70118-0357-4f5e-aa56-77560edec238">
<p><strong>This should then lead to your browser opening osTicket</strong>.</p>
<img width="664" alt="osTicket browser" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/258689e2-a099-43e1-a555-a70eb7ad1e9d">
<h3>Enable extensions</h3>
<p>Open IIS and click on PHP Manager and select "enable or disable extension". </p>
<p>Enable the following extensions:</p>
<p>[X]Enable: php_imap.dll</p>
<p>[X]Enable: php_intl.dll</p>
<p>[X]Enable: php_opcache.dll</p>
<img width="273" alt="php enable 2" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/f384957a-2228-47d9-9249-987c929eb691">
<h3>Refresh osTicket</h3>
<p>Refresh the osTicket page on the browser and notice some extensions will now appear active.</p>
<img width="608" alt="OSticket changes" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/5d6aded2-86bf-44b8-b20f-5035e912cd44">
<h3>Rename ost-config.ph</h3>
<p> Under C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename "ost-sampleconfig.ph" to "ost-config.ph"</p>
<img width="527" alt="ostconfig rename" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/1dcd19e8-6b76-4d83-9d59-17dc4ef5b28f">
<h3>Change ost-config.ph permissions</h3>
<p>Change ost-config.php permissions by right clicking and selecting</p>
<p>Properties -> Security -> Advance -> Disable inheritance</p> 
<p>Select remove all inherited permissions and add everyone as a principal. Select all boxes to ensure all permissions are granted. </p>
<img width="571" alt="Permissions" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/d634bc06-dcc0-4b41-814d-1f7de0afa0bf">
<h3>Continue osTicket installation</h3>
<p> Continue the osTicket installer on your browser by filling the first half of the page.</p>
<img width="611" alt="osticket signup" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/1df4ef77-85f3-4f36-bf93-44ce3e910d64">
<p><strong>NOTE: Don't worry about the database credentials. We'll fill those out later.</strong> </p>

<h3>Download and install Heidi SQL from the installation files</h3>

<p>Open Heidi SQL and create a new session. Make sure to fill in the username as root and create a password. After filling up your credentials now click open and a new session should show up.
</p>

<h3>Create new database </h3>

<p>On the left side of the window, right click on "Unnamed" and click create new database and name it "osTicket".</p>
<img width="512" alt="SQL" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/eaa5aa61-2eea-4406-a7d7-fa77616dbe16">


<h3>Finish signing up</h3>
<p>Then go back to your osTicket browser and fill up the missing credentials. 
It should look something like this.</p>
<img width="308" alt="osticket final signup" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/a185574b-775a-49fb-9468-c5d82033e823">

<h3>Finalize osTicket installation</h3>

<p>Click install and osTicket should begin setting up. </p>
