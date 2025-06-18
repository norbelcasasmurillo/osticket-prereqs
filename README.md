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
Log into Microsoft Azure and head to the virtual machines tab. Click on the + Create Button and press create Azure Virtual Machine. 
</p>
<p>
  
![image](https://github.com/user-attachments/assets/4e3113d6-34f8-4519-8a62-96628c99628a)

</p>
<br />

<p>
- **Create a new resource group:** `osTicket`  
- **Virtual machine name:** `osticket-vm`  
- **Select a region:** East US 2   
</p>
<p>
  
![image](https://github.com/user-attachments/assets/4e3113d6-34f8-4519-8a62-96628c99628a)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/784982af-08b7-4293-8ac3-5d4b2e539076)

</p>
<p>
Next, while creating an Azure Virtual Machine. Choose Windows 10 pro for the operating system, and for size 4 vCPUs.
</p>
<br />

<p>


![image](https://github.com/user-attachments/assets/7c7310a4-8951-43d6-bc34-5c3c53c75824)

</p>
<p>
Then fill out using these exact login infomration. Username: labuser ; Password: osTicketPassword1! Also check the box at the bottom for the licensing. Finally, click on teh "Review + Create" button.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/ca3be361-e5d2-4267-af35-250b372ecd92)

</p>
<p>
Next click on the Create button. 
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/78f10f82-3804-4e54-a4f0-dce5d489d532)

</p>
<p>
Log into the VM with Remote Desktop. Use the previous login information.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/666cb2c7-6b46-4537-8d19-f568e360d448)

</p>
<p>
Within the VM (osticket-vm), download the osTicket-Installation-Files.zip (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)
  
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/98c2327d-6051-4bd0-8d7b-93f5e6f2bb30)

</p>
<p>
Unzip it onto your desktop.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/7a91ff19-d545-4fad-949c-44278474726e)

![image](https://github.com/user-attachments/assets/4b99edb6-f940-48fc-9a60-641e88ab1356)


</p>
<p>
The folder should be called “osTicket-Installation-Files”. We will use the files in this folder to install osTicket and some of the dependencies.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/cb6dddea-bd34-4c7a-b911-6adfc86108bb)

![image](https://github.com/user-attachments/assets/a5d44b3d-f4c2-471e-bc59-5c6c6db73e09)


</p>
<p>
In order to Install / Enable IIS in Windows WITH CGI, first go to the Control Panel from the start menu and click on it. Then click on Program [Uninstall Program]

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/38fa1db6-74ed-4df1-89b4-4d95ea5ccfe4)

![image](https://github.com/user-attachments/assets/0223b314-55d6-4c61-9fb7-97f71e6d13c5)


</p>
<p>
From there, click on "Turn Window Features On or Off"
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/56d5b9aa-0b44-42bf-9224-bee886db9245)

</p>
<p>
Check Internet Information Services box.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/92a8adff-14ec-455d-8ab6-4cb8329cc648)


</p>
<p>
Expand that folder, then expand World Web Web Services folder, then expand Application Development Features, then click CGI. Then click OK. 
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/5a98852f-e257-4fb1-b62c-4b57195e2b16)

</p>
<p>
Type 127.0.0.1 in the address bar in a browser in the windows-vm, then press enter.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/795cbf2a-dd00-499e-9e57-15a5bc020de4)

![image](https://github.com/user-attachments/assets/7793ed53-82c4-433e-b9f3-065287627293)


</p>
<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) [Say yes to everything and install it]

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/ffb0730b-c87e-4353-b583-0ebfa872be77)

</p>
<p>
In order to create the directory C:\PHP, first open a new file explorer folder.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/103851e8-aac8-440e-a471-84a8abcc3c80)

</p>
<p>
Go to the C drive

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/59acfef1-6fd5-4ecb-a8a9-fe2786dd3699)

</p>
<p>
Create a new folder there, and name it PHP.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/2320ee01-811e-4e9c-baec-c4c836fe0d2f)

![image](https://github.com/user-attachments/assets/7b6026cd-e318-45af-8357-411239c780b7)

![image](https://github.com/user-attachments/assets/6727870e-83b3-4362-a793-98b83785a47c)



</p>
<p>
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/dcee8065-d87f-44e9-8bdd-67a107c88cc8)

</p>
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/5de5b997-6148-48db-af07-1fdcb1f3e26a)


</p>
<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/124914b6-692f-43e1-8ee2-12d16990a271)

</p>
<p>
Choose Typical Setup.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/5aadf256-4fab-42a7-b37c-1a2c1eaa5ea9)

</p>
<p>
Launch Configuration Wizard (after install). 
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/7919c076-b489-4669-97d8-0e4793ad8915)

</p>
<p>
Choose Standard Configuration. Follow by putting this login information in the setup: Username: root ; Password: root.


</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/dfcb1271-621b-4d84-b5ba-d5669e0fe255)


</p>
<p>
Save login information on the desktop with notepad.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/9a954baf-347f-4265-918d-418407b19052)

</p>
<p>
Open IIS as an Admin

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/1ecb9172-3512-4c30-afae-e7d13a6c5982)

</p>
<p>
In order to register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe), first open PHP Manager

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/28414cdb-21ba-4d41-a486-cea931fea6cf)

</p>
<p>
Select Register New PHP version.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/22f7c401-d98d-4cc3-a0b6-ac9f329edf42)

</p>
<p>
Click the three dots to browse through it.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/e67b3c9f-8c2e-4b58-8669-eb9c7dacc90d)

</p>
<p>
Go to C drive and into PHP folder. Then select php-cgi.exe. Then click OK.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/a5639752-4a87-4914-ae07-db15a65fe4b9)

</p>
<p>
in order to reload IIS (Open IIS, Stop and Start the server), click under the Connections left sidebar, where it says osticket-vm …

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/3a341204-0f54-4de4-a0ed-cede37dfc4b3)

</p>
<p>
Then Under on the Right handed sidebar that says Action, click on stop. 

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/2e1150e3-8d3f-4a2a-ae0b-7d02d162394b)

</p>
<p>
Then click start.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/f2dc74e3-718e-4ae2-a851-e00b2eeb612b)

![image](https://github.com/user-attachments/assets/cf5f80ca-b237-4556-aa2b-bc04fba471e0)


</p>
<p>
Then, in order to install osTicket v1.15.8, first from the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” (extract in the given place)

<br />

<p>

![image](https://github.com/user-attachments/assets/0f581053-8b5f-432a-bf22-1b25a3608837)

![image](https://github.com/user-attachments/assets/713ba414-66b7-4a13-b4e5-4dadf9f10d8a)


</p>
<p>
copy the “upload” folder into “c:\inetpub\wwwroot”
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/3350994b-81a1-4b85-acd9-bd0a27016da6)

</p>
<p>
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/9de40a17-3b15-4950-9d3a-941307b88176)

![image](https://github.com/user-attachments/assets/af201faa-895a-4d09-9a42-269a498a4a17)


</p>
<p>
Reload IIS (Open IIS, Stop and Start the server)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/bf96f8a1-2c9d-4155-8cc5-67d9b3b8a62c)


</p>
<p>
Go to sites -> Default -> osTicket (then click on it)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/bf96f8a1-2c9d-4155-8cc5-67d9b3b8a62c)

![image](https://github.com/user-attachments/assets/314a5bc3-f84b-4055-b25f-8bcec3331519)

</p>
<p>
On the right, click “Browse *:80”

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/a2f623aa-e331-4d66-a5fc-9776d1a508c5)

</p>
<p>
Note that some extensions are not enabled. Go back to IIS, sites -> Default -> osTicket

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/87575a1f-69d8-403d-a9f8-b6ebd7aee6d9)

</p>
<p>
Double-click PHP Manager

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/2a858bbe-e4b2-4897-9213-8ba72d38422d)

</p>
<p>
Click “Enable or disable an extension”

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/406d4b20-1141-42b7-bb49-5a621f9c044a)

</p>
<p>
Enable: php_imap.dll ; Enable: php_intl.dll ; Enable: php_opcache.dll

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/6ee11063-83d1-49c8-90cd-37152e6621f6)

</p>
<p>
Refresh the osTicket site in your browser, observe the changes

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/291614e6-0c01-4c1e-8fef-635ec061e705)

</p>
<p>
Rename: ost-config.php. From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php ; To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/7354ec22-13b0-46eb-886f-79acc6e327b1)

</p>
<p>
Assign Permissions: ost-config.php (Right click file and go to properties)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/dcb514d2-a351-45bf-bb6f-96fffdc66c6c)

</p>
<p>
Then go to Security -> Advanced

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/63e308f0-9363-4a35-84b8-7c65d4ef7c0d)

![image](https://github.com/user-attachments/assets/64aad517-4b18-455e-beed-b6de24c2e1e2)


</p>
<p>
Disable inheritance -> Remove All

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/52dbb752-00d8-4214-8ce9-9fd94fd43a16)

</p>
<p>
In order to  go from New Permissions -> Everyone -> All, first click on add to add New Permissions.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/c783f6cd-b6be-43bf-90af-3633ce9bd494)

</p>
<p>
Select Principal.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/f28dc13f-b26b-4b5b-aaf5-7759bd61a1c4)

</p>
<p>
Type everyone, then click check name, then OK.In real life, this is not ideal for security purposes.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/71c8f55b-0651-42e8-b11b-bf6d279aa16a)

</p>
<p>
Then click full control, then OK.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/1f74d383-1edb-4ec9-bd15-16038cb39f9c)

</p>
<p>
Make sure in the name it should be ‘‪C:\inetpub\wwwroot\osTicket\include\ost-config.php’. Then click Apply, then OK.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/53ca1561-f387-41e9-8412-fedd37bbeec7)

</p>
<p>
Then click OK in ost-config.php properties.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/f3a289e9-687f-4735-9899-42fb4140606d)

</p>
<p>
Continue Setting up osTicket in the browser (click Continue)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/576d0461-1e73-44df-9fd7-17aac02761c4)

</p>
<p>
Name: Helpdesk ; Default email (receives email from customers) ; (The other email should be different)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/83dfb887-b26b-4698-8cd1-eebf11359fcf)

</p>
<p>
Use your admin login info there. (Afterwards move on to the next step, but we are still not done here)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/4b15c016-4926-4669-978d-9bd8129847e5)



</p>
<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL. (https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe)
Open Heidi SQL to install. (Yes to everything, check launch, and click finish)

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/84c007e0-7f07-4add-8b2d-95992065ca3e)

</p>
<p>
Click Skip

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/ba2709c8-3d93-4d54-91f4-ef4d85eecc24)

</p>
<p>
Click New

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/d7f1c652-3852-402b-a149-a3ef193bb057)

</p>
<p>
Create a new session, root/root, then click open

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/929af70d-ec12-41ad-8594-ed3c69814a27)

</p>
<p>
Connect to the session.

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/eb2758c2-9d5d-4c6b-b20b-9976cc4c0115)

![image](https://github.com/user-attachments/assets/e8e133d6-385d-488d-88fb-198f54c3156b)


</p>
<p>
Create a database called “osTicket”, then click OK (You have to right click Unnamed) (Can refresh this by right clicking after you install in the next step).

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/a0dc436c-172f-44b6-909b-cbd091fbc9a1)

</p>
<p>
Continue Setting up osTicket in the browser. MySQL Database: osTicket ; MySQL Username: root ; MySQL Password: root ; Click “Install Now!”

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/a1878562-275f-4244-9d5c-60343b71ec4c)

![image](https://github.com/user-attachments/assets/547b05dd-4535-404a-b025-905829da1e41)


</p>
<p>
Congratulations, hopefully it is installed with no errors! Browse to your help desk login page: http://localhost/osTicket/scp/login.php

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/afe36545-953a-4547-9470-cf49fa3e220d)

</p>
<p>
End Users osTicket URL: http://localhost/osTicket/ 

</p>
<br />
