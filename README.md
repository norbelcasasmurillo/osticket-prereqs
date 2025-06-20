<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and guides you through installing the osTicket help desk system on a Windows virtual machine.<br />

<h4>Sidenotes:</h4>

- The screenshots shown below are from Windows 10 (what I used for my personal computer and VM)
- Your personal computer can use any operating system


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Windows 10 Pro (VM)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Download [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) once inside the VM
- Active Microsoft Azure Subscription 
<h2>Installation Steps</h2>

<p align="center">
Log into Microsoft Azure and head to the virtual machines tab, then click on the + Create Button and press create Azure Virtual Machine. 
</p>
</p>

![image](https://github.com/user-attachments/assets/ca38e9ad-9c8c-4baa-a3d9-fcd8dd15cca8)


</p>
<br />

<p align="center">
  
- **Create a new resource group:** `osTicket`  
- **Virtual machine name:** `osticket-vm`  
- **Region:** East US 2
- **Operating System:** Windows 10 pro
- **Size:** 2 vCPUS or higher
- **Username:** labuser
- **Password:** osTicketPassword1!
- **Licensing checkbox:** checked
  
</p>
<p>
  
![image](https://github.com/user-attachments/assets/5020f5ff-4353-445f-80fe-1e47d42c9a80)

</p>
<br />

<p align="center">
Click on the "Review + Create" button.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/60bf27c6-813f-46a2-b03e-1e0ebb71da00)
  
</p>
<br />

<p align="center">
Next click on the Create button. 
</p>
</p>

![image](https://github.com/user-attachments/assets/0acf1155-957a-4ff2-a903-e12719706ffd)

</p>
<br />

<p align="center">
Log into the VM with Remote Desktop. Use the previous login information, and public IP address from the VM you created.

</p>
</p>

![image](https://github.com/user-attachments/assets/5bb961b1-39a3-4559-9641-fbb3aa03385d)


</p>
<br />

<p align="center">
Within the VM (osticket-vm), download the osTicket-Installation-Files.zip 
(https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
</p>
</p>
  
![image](https://github.com/user-attachments/assets/29e4247b-aa43-49b7-8816-1a89f394b9da)
 
</p>
<br />

<p align="center">
Unzip it onto your desktop.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/5de7bedc-26ff-4fdd-81f2-fe19358ac25f)
</p>
<br />

<p align="center">
The folder should be called “osTicket-Installation-Files”. We will use the files in this folder to install osTicket and some of the dependencies.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/8f904d8d-add2-437a-8c67-032203fd03ca)


</p>
<br />

<p align="center">
In order to Install / Enable IIS in Windows WITH CGI, first go to the Control Panel from the start menu and click on it. Then click on Program [Uninstall Program]


</p>
</p>
  
![image](https://github.com/user-attachments/assets/589b0f52-5de6-4e2a-b28e-6b961214b233)


</p>
<br />

<p align="center">
From there, click on "Turn Window Features On or Off"

</p>
</p>
  
![image](https://github.com/user-attachments/assets/6b3f0713-1d39-4392-9dfb-8882c4c9c46f)


</p>
<br />

<p align="center">
Check Internet Information Services box.


</p>
</p>
  
![image](https://github.com/user-attachments/assets/c739f2dd-3cd0-4c29-a27b-a743ceadd434)

</p>
<br />

<p align="center">
Expand that folder, then expand World Web Web Services folder, then expand Application Development Features, then click CGI. Then click OK. 

</p>
</p>
  
![image](https://github.com/user-attachments/assets/47f39111-96b5-4f0e-ac7a-261ce0323111)

</p>
<br />

<p align="center">
Type 127.0.0.1 in the address bar in a browser in the windows-vm, then press enter.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/b3abc05f-8f1c-4731-8ed5-dba7cee528a1)

</p>
<br />

<p align="center">
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) [Say yes to everything and install it]

</p>
</p>
  
![image](https://github.com/user-attachments/assets/4d11768e-02e5-4586-88eb-394a4e2a8103)


</p>
<br />

<p align="center">
In order to create the directory C:\PHP, first open a new file explorer folder. Go to the C drive within This PC icon. Create a new folder there, and name it PHP.
</p>
</p>
  
![image](https://github.com/user-attachments/assets/8dbdec81-26fe-4d49-a359-ff5a86771c29)

</p>
<br />



<p align="center">
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/6147e251-1ea3-47c2-b307-eb25364093a7)




</p>
<br />

<p align="center">
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

</p>
</p>

![image](https://github.com/user-attachments/assets/42b89cd5-5fa9-4112-88e0-6a8f854b42a9)

</p>
<br />

<p align="center">
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)


</p>
</p>

![image](https://github.com/user-attachments/assets/f7895a75-5a1d-4a71-93f5-5be482e1aec9)
</p>
<br />

<p align="center">
Choose Typical Setup.

</p>
</p>

![image](https://github.com/user-attachments/assets/905db936-52a6-47b3-a7f3-2d9bf958eb5a)
</p>
<br />

<p align="center">
Launch Configuration Wizard (after install). 

</p>
</p>

![image](https://github.com/user-attachments/assets/554a73e1-91b2-496d-9285-3f9bf4b1e774)
</p>
<br />

<p align="center">
Choose Standard Configuration, then next. Then choose "Install As Window Service", then click next. Follow by putting this login information in the setup: Username: root ; Password: root.

</p>
</p>

![image](https://github.com/user-attachments/assets/f9cc550a-d110-400d-9ead-f5e8e8d79421)


</p>
<br />

<p align="center">
Save login information on the desktop with notepad.

</p>
</p>

![image](https://github.com/user-attachments/assets/8a55ddb4-63c9-4762-b291-dc2edb10c7e8)

</p>
<br />

<p align="center">
Open IIS as an Admin

</p>
<p>

![image](https://github.com/user-attachments/assets/919fa441-ea8b-45c0-99ac-6d06b848f38f)

</p>
<br />

<p align="center">
In order to register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe), first open PHP Manager

</p>
</p>

![image](https://github.com/user-attachments/assets/1ecb9172-3512-4c30-afae-e7d13a6c5982)

</p>
<br />

<p align="center">
Select Register New PHP version.


</p>
</p>

![image](https://github.com/user-attachments/assets/28414cdb-21ba-4d41-a486-cea931fea6cf)


</p>
<br />

<p align="center">
Click the three dots to browse through it.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/22f7c401-d98d-4cc3-a0b6-ac9f329edf42)

</p>
<br />

<p align="center">
Go to C drive and into PHP folder. Then select php-cgi.exe. Then click OK.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/e67b3c9f-8c2e-4b58-8669-eb9c7dacc90d)

</p>
<br />

<p align="center">
in order to reload IIS (Open IIS, Stop and Start the server), click under the Connections left sidebar, where it says osticket-vm …

</p>
</p>

![image](https://github.com/user-attachments/assets/a5639752-4a87-4914-ae07-db15a65fe4b9)

</p>
<br />

<p align="center">
Then Under on the Right handed sidebar that says Action, click on stop. 


</p>
</p>
  
![image](https://github.com/user-attachments/assets/3a341204-0f54-4de4-a0ed-cede37dfc4b3)

</p>
<br />

<p align="center">
Then click start.


</p>
</p>

![image](https://github.com/user-attachments/assets/2e1150e3-8d3f-4a2a-ae0b-7d02d162394b)

</p>
<br />

<p align="center">
Then, in order to install osTicket v1.15.8, first from the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” (extract in the given place)


</p>
</p>
  
![image](https://github.com/user-attachments/assets/f2dc74e3-718e-4ae2-a851-e00b2eeb612b)
![image](https://github.com/user-attachments/assets/cf5f80ca-b237-4556-aa2b-bc04fba471e0)

<br />

<p align="center">
copy the “upload” folder into “c:\inetpub\wwwroot”

</p>
</p>
  
![image](https://github.com/user-attachments/assets/0f581053-8b5f-432a-bf22-1b25a3608837)

![image](https://github.com/user-attachments/assets/713ba414-66b7-4a13-b4e5-4dadf9f10d8a)</p>
<br />

<p align="center">
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

</p>
</p>
![image](https://github.com/user-attachments/assets/3350994b-81a1-4b85-acd9-bd0a27016da6)

</p>
<br />

<p align="center">
Reload IIS (Open IIS, Stop and Start the server)

</p>
</p>
  
![image](https://github.com/user-attachments/assets/9de40a17-3b15-4950-9d3a-941307b88176)

![image](https://github.com/user-attachments/assets/af201faa-895a-4d09-9a42-269a498a4a17)

</p>
<br />

<p align="center">
Go to sites -> Default -> osTicket (then click on it)


</p>
</p>
  
![image](https://github.com/user-attachments/assets/bf96f8a1-2c9d-4155-8cc5-67d9b3b8a62c)

</p>
<br />

<p align="center">
On the right, click “Browse *:80”

</p>
</p>

![image](https://github.com/user-attachments/assets/bf96f8a1-2c9d-4155-8cc5-67d9b3b8a62c)

![image](https://github.com/user-attachments/assets/314a5bc3-f84b-4055-b25f-8bcec3331519)
</p>
<br />

<p align="center">
Note that some extensions are not enabled. Go back to IIS, sites -> Default -> osTicket

</p>
</p>
  
![image](https://github.com/user-attachments/assets/a2f623aa-e331-4d66-a5fc-9776d1a508c5)

</p>
<br />

<p align="center">
Double-click PHP Manager

</p>
</p>

![image](https://github.com/user-attachments/assets/87575a1f-69d8-403d-a9f8-b6ebd7aee6d9)

</p>
<br />

<p align="center">
Click “Enable or disable an extension”

</p>
</p>
  
![image](https://github.com/user-attachments/assets/2a858bbe-e4b2-4897-9213-8ba72d38422d)

</p>
<br />

<p align="center">
Enable: php_imap.dll ; Enable: php_intl.dll ; Enable: php_opcache.dll

</p>
</p>
  
![image](https://github.com/user-attachments/assets/406d4b20-1141-42b7-bb49-5a621f9c044a)

</p>
<br />

<p align="center">
Refresh the osTicket site in your browser, observe the changes

</p>
</p>

![image](https://github.com/user-attachments/assets/6ee11063-83d1-49c8-90cd-37152e6621f6)

</p>
<br />

<p align="center">
Rename: ost-config.php. From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php ; To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
</p>
  
![image](https://github.com/user-attachments/assets/291614e6-0c01-4c1e-8fef-635ec061e705)

</p>
<br />

<p align="center">
Assign Permissions: ost-config.php (Right click file and go to properties)

</p>
</p>
  
![image](https://github.com/user-attachments/assets/7354ec22-13b0-46eb-886f-79acc6e327b1)

</p>
<br />

<p align="center">
Then go to Security -> Advanced


</p>
</p>
  
![image](https://github.com/user-attachments/assets/dcb514d2-a351-45bf-bb6f-96fffdc66c6c)

</p>
<br />

<p align="center">
Disable inheritance -> Remove All


</p>
</p>
  
![image](https://github.com/user-attachments/assets/63e308f0-9363-4a35-84b8-7c65d4ef7c0d)

![image](https://github.com/user-attachments/assets/64aad517-4b18-455e-beed-b6de24c2e1e2)

</p>
<br />

<p align="center">
In order to  go from New Permissions -> Everyone -> All, first click on add to add New Permissions.

</p>
</p>

![image](https://github.com/user-attachments/assets/52dbb752-00d8-4214-8ce9-9fd94fd43a16)

</p>
<br />

<p align="center">
Select Principal.

</p>
</p>

![image](https://github.com/user-attachments/assets/c783f6cd-b6be-43bf-90af-3633ce9bd494)

</p>
<br />

<p align="center">
Type everyone, then click check name, then OK.In real life, this is not ideal for security purposes.

</p>
</p>

![image](https://github.com/user-attachments/assets/f28dc13f-b26b-4b5b-aaf5-7759bd61a1c4)

</p>
<br />

<p align="center">
Then click full control, then OK.

</p>
</p>

![image](https://github.com/user-attachments/assets/71c8f55b-0651-42e8-b11b-bf6d279aa16a)
</p>
<br />

<p align="center">
Make sure in the name it should be ‘‪C:\inetpub\wwwroot\osTicket\include\ost-config.php’. Then click Apply, then OK.

</p>
</p>

![image](https://github.com/user-attachments/assets/1f74d383-1edb-4ec9-bd15-16038cb39f9c)

</p>
<br />

<p align="center">
Then click OK in ost-config.php properties.

</p>
</p>

![image](https://github.com/user-attachments/assets/53ca1561-f387-41e9-8412-fedd37bbeec7)

</p>
<br />

<p align="center">
Continue Setting up osTicket in the browser (click Continue)

</p>
</p>

![image](https://github.com/user-attachments/assets/f3a289e9-687f-4735-9899-42fb4140606d)

</p>
<br />

<p align="center">
Name: Helpdesk ; Default email (receives email from customers) ; (The other email should be different)

</p>
</p>

![image](https://github.com/user-attachments/assets/576d0461-1e73-44df-9fd7-17aac02761c4)

</p>
<br />

<p align="center">
Use your admin login info there. (Afterwards move on to the next step, but we are still not done here)

</p>
</p>

![image](https://github.com/user-attachments/assets/83dfb887-b26b-4698-8cd1-eebf11359fcf)

</p>
<br />

<p align="center">
From the “osTicket-Installation-Files” folder, install HeidiSQL. (https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe)
Open Heidi SQL to install. (Yes to everything, check launch, and click finish)

</p>
</p>

![image](https://github.com/user-attachments/assets/4b15c016-4926-4669-978d-9bd8129847e5)

</p>
<br />

<p align="center">
Click Skip

</p>
</p>

![image](https://github.com/user-attachments/assets/84c007e0-7f07-4add-8b2d-95992065ca3e)

</p>
<br />

<p align="center">
Click New

</p>
</p>
  
![image](https://github.com/user-attachments/assets/ba2709c8-3d93-4d54-91f4-ef4d85eecc24)

</p>
<br />

<p align="center">
Create a new session, root/root, then click open

</p>
</p>

![image](https://github.com/user-attachments/assets/d7f1c652-3852-402b-a149-a3ef193bb057)

</p>
<br />

<p align="center">
Connect to the session.

</p>
</p>

![image](https://github.com/user-attachments/assets/929af70d-ec12-41ad-8594-ed3c69814a27)

</p>
<br />

<p align="center">
Create a database called “osTicket”, then click OK (You have to right click Unnamed) (Can refresh this by right clicking after you install in the next step).

</p>
</p>
  
![image](https://github.com/user-attachments/assets/eb2758c2-9d5d-4c6b-b20b-9976cc4c0115)

![image](https://github.com/user-attachments/assets/e8e133d6-385d-488d-88fb-198f54c3156b)
</p>
<br />

<p align="center">
Continue Setting up osTicket in the browser. MySQL Database: osTicket ; MySQL Username: root ; MySQL Password: root ; Click “Install Now!”

</p>
</p>

![image](https://github.com/user-attachments/assets/a0dc436c-172f-44b6-909b-cbd091fbc9a1)

</p>
<br />

<p align="center">
Congratulations, hopefully it is installed with no errors! Browse to your help desk login page: http://localhost/osTicket/scp/login.php

</p>
</p>

![image](https://github.com/user-attachments/assets/a1878562-275f-4244-9d5c-60343b71ec4c)

![image](https://github.com/user-attachments/assets/547b05dd-4535-404a-b025-905829da1e41)

</p>
<br />

<p align="center">
End Users osTicket URL: http://localhost/osTicket/ 


</p>
</p>

![image](https://github.com/user-attachments/assets/afe36545-953a-4547-9470-cf49fa3e220d)

</p>
<br />
