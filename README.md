<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and guides you through installing the osTicket help desk system on a Windows virtual machine.<br />

<h4>Sidenotes:</h4>

- The screenshots shown below are from Windows 10 (what I used for my personal computer and VM)
- Your personal computer can use any operating system

<h2>Video Demonstration</h2>

- ### [YouTube: Ticketing System Tutorial Part 1: osTicket - Prerequisites and Installation](https://www.youtube.com/watch?v=MwSmFoCdFtw&t=437s)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Windows 10 Pro (VM)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- All Items: [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) 
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


<h3 align="center"> Installing PHP Manager </h3>


<p align="center">
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) [Say yes to everything and install it]

</p>
</p>
  
![image](https://github.com/user-attachments/assets/4d11768e-02e5-4586-88eb-394a4e2a8103)


</p>
<br />


<h3 align="center"> Installing Rewrite Manager </h3>


<p align="center">
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
</p>
  
![image](https://github.com/user-attachments/assets/31899bec-7e95-4a71-b273-f2d222e5af20)


</p>
<br />


<h3 align="center"> Create directory called C:\PHP </h3>


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


<h3 align="center"> Download VC_redist </h3>


<p align="center">
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

</p>
</p>

![image](https://github.com/user-attachments/assets/42b89cd5-5fa9-4112-88e0-6a8f854b42a9)

</p>
<br />


<h3 align="center"> Download MySQL </h3>


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
Choose Standard Configuration, then next. Then choose "Install As Window Service" (leave the default setting for this alone), then click next. Follow by putting this login information in the setup: new root password: root ; confirm: root. Then click next, then execute. 

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


<h3 align="center"> Configurations in IIS </h3>


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

![image](https://github.com/user-attachments/assets/b55a5522-f4ea-4809-856c-b7d50d0a4c21)

</p>
<br />

<p align="center">
Select Register New PHP version.


</p>
</p>

![image](https://github.com/user-attachments/assets/24a46b1a-dffa-4d11-9fe7-8c6122f8cb55)


</p>
<br />

<p align="center">
Click the three dots to browse through it.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/142a1d47-20b5-40d9-8930-be8a5480be73)

</p>
<br />

<p align="center">
Go to C drive and into PHP folder. Then select php-cgi.exe, then click open. Then click OK.

</p>
</p>
  
![image](https://github.com/user-attachments/assets/0e2096cf-c2e3-4df2-929c-dd8fa9777cdf)

</p>
<br />

<p align="center">
in order to reload IIS (Open IIS, Stop and Start the server),look under the Connections left sidebar, where it says osticket-vm (osTicket-vm\labuser) and double click it.

</p>
</p>

![image](https://github.com/user-attachments/assets/4cfd3f23-0415-4f73-9625-12053e9acb6b)

</p>
<br />

<p align="center">
Then Under on the Right handed sidebar that says Action, click on stop. 


</p>
</p>
  
![image](https://github.com/user-attachments/assets/c9b84a5e-9a05-4b31-ac41-c467d2d026de)

</p>
<br />

<p align="center">
Then click start.


</p>
</p>

![image](https://github.com/user-attachments/assets/7f1e590e-7671-4c95-8949-5062bfc4eeeb)

</p>
<br />


<h3 align="center"> Install OsTicket </h3>


<p align="center">
Then, in order to install osTicket v1.15.8, first from the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” (extract in the given place)


</p>
</p>
  
![image](https://github.com/user-attachments/assets/ecf82832-c4ca-4206-8810-01d61b86c787)


<br />

<p align="center">
copy the “upload” folder into “c:\inetpub\wwwroot”

</p>
</p>
  
![image](https://github.com/user-attachments/assets/8a5a4382-a699-4227-95c7-1bb86de04922)

</p>
<br />

<p align="center">
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

</p>
</p>

![image](https://github.com/user-attachments/assets/ae6bc5a7-b78f-4802-b12d-dfa63305463e)

</p>
<br />


<h3 align="center"> Reload IIS </h3>


<p align="center">
Reload IIS (Open IIS, Stop and Start the server)

</p>
</p>
  
![image](https://github.com/user-attachments/assets/c9b84a5e-9a05-4b31-ac41-c467d2d026de)

![image](https://github.com/user-attachments/assets/7f1e590e-7671-4c95-8949-5062bfc4eeeb)

</p>
<br />


<h3 align="center"> OsTicket configurations </h3>


<p align="center">
Go to sites -> Default -> osTicket (then click on it)


</p>
</p>
  
![image](https://github.com/user-attachments/assets/99d5ce6c-4bc1-427a-b5f8-21e0f7ae88bb)

</p>
<br />

<p align="center">
On the right, click “Browse *:80”

</p>
</p>

![image](https://github.com/user-attachments/assets/53b71f9f-ed7f-44f4-ae6f-66f762ffc32a)

</p>
<br />

<p align="center">
Note that some extensions are not enabled. Go back to IIS, sites -> Default -> osTicket

</p>
</p>
  
![image](https://github.com/user-attachments/assets/be2b850a-4b02-40fc-8f58-4a86baaefa83)

</p>
<br />

<p align="center">
Double-click PHP Manager

</p>
</p>

![Screenshot (4)](https://github.com/user-attachments/assets/34ab5753-f80e-44c3-af89-db26879ea8d1)

</p>
<br />

<p align="center">
Click “Enable or disable an extension”

</p>
</p>
  
![image](https://github.com/user-attachments/assets/29b3c696-6126-4f4d-b92d-868a3a1979fc)

</p>
<br />

<p align="center">
Enable: php_imap.dll ; Enable: php_intl.dll ; Enable: php_opcache.dll

</p>
</p>
  
![image](https://github.com/user-attachments/assets/7fc79525-73d6-4432-8c1e-947d11f05153)

</p>
<br />

<p align="center">
Refresh the osTicket site in your browser, observe the changes

</p>
</p>

![image](https://github.com/user-attachments/assets/b3dff0d5-94f8-41dd-8dde-3ee96b70dfa1)

</p>
<br />

<p align="center">
Rename: ost-config.php. From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php ; To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
</p>
  
![image](https://github.com/user-attachments/assets/6f557a64-a590-44bd-ab55-0cb37b4d1724)

</p>
<br />

<p align="center">
Assign Permissions: ost-config.php (Right click file and go to properties)

</p>
</p>
  
![image](https://github.com/user-attachments/assets/1c41ddf3-414d-4510-a70b-518bdff67d64)

</p>
<br />

<p align="center">
Then go to Security -> Advanced


</p>
</p>
  
![image](https://github.com/user-attachments/assets/998bb06f-8976-42c1-85a4-606a883f1dff)

</p>
<br />

<p align="center">
Disable inheritance -> Remove All


</p>
</p>
  
![image](https://github.com/user-attachments/assets/c5e2fff5-29b5-4497-b078-fdc7645d096c)


</p>
<br />

<p align="center">
In order to  go from New Permissions -> Everyone -> All, first click on add to add New Permissions.

</p>
</p>

![image](https://github.com/user-attachments/assets/55ace340-e835-44d5-8518-2d14cf1ec801)

</p>
<br />

<p align="center">
Select Principal.

</p>
</p>

![image](https://github.com/user-attachments/assets/5bc7c101-addb-4693-a50b-1157679cfb08)

</p>
<br />

<p align="center">
Type everyone, then click check name, then OK. In real life, this is not ideal for security purposes.

</p>
</p>

![image](https://github.com/user-attachments/assets/23d08dc7-57f0-472f-a517-00686f93ac27)

</p>
<br />

<p align="center">
Then click full control, then OK.

</p>
</p>

![image](https://github.com/user-attachments/assets/1c64771a-5a43-4f0e-850f-fde974222f25)
</p>
<br />

<p align="center">
Make sure in the name it should be ‘‪C:\inetpub\wwwroot\osTicket\include\ost-config.php’. Then click Apply, then OK.

</p>
</p>

![image](https://github.com/user-attachments/assets/95a4d20b-f3a3-44f5-b6c3-0a0f713b6784)

</p>
<br />

<p align="center">
Then click OK in ost-config.php properties.

</p>
</p>

![image](https://github.com/user-attachments/assets/a1dd0444-00b0-4ef6-9e20-d9f822a77994)

</p>
<br />


<h3 align="center"> Final OsTicket configurations </h3>


<p align="center">
Continue Setting up osTicket in the browser (click Continue)

</p>
</p>

![image](https://github.com/user-attachments/assets/933d94f9-882b-4577-848a-bf28415bcd87)

</p>
<br />

<p align="center">
- **Name:** Helpdesk 
- **Default email (receives email from customers):** any
- **(The other email should be different)**

</p>
</p>

![image](https://github.com/user-attachments/assets/37504d74-6da5-4004-9fd2-3569ad4aaf47)

</p>
<br />

<p align="center">
Use your admin login info there. (Afterwards move on to the next step, but we are still not done here)

</p>
</p>

![image](https://github.com/user-attachments/assets/2ab688c9-4112-4fbd-85aa-f4f00748ccc9)

</p>
<br />


<h3 align="center"> Install HeidiSQL </h3>


<p align="center">
From the “osTicket-Installation-Files” folder, install HeidiSQL. (https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe)
Open Heidi SQL to install. (Yes to everything, check launch, and click finish)

</p>
</p>

![image](https://github.com/user-attachments/assets/67d15816-59cb-4d49-80ba-ac71a55f2559)

</p>
<br />

<p align="center">
Click Skip

</p>
</p>

![image](https://github.com/user-attachments/assets/5e6405a7-4e21-42fe-8a45-0b5610e73244)

</p>
<br />

<p align="center">
Click New

</p>
</p>
  
![image](https://github.com/user-attachments/assets/3331094e-75a9-4514-8aad-d442d9cda178)

</p>
<br />

<p align="center">
In order to create a new session, type root for username and password, then click open to connect to the session. 

</p>
</p>

![image](https://github.com/user-attachments/assets/5a83d2e6-f2d3-4741-953f-34a37988ad69)


<p align="center">
Create a database called “osTicket”, then click OK (You have to right click Unnamed) (Can refresh this by right clicking after you install in the next step).

</p>
</p>
  
![image](https://github.com/user-attachments/assets/83d26142-54db-41f2-9406-4cb6c7c25ebc)

</p>
<br />


<h3 align="center"> Continue Setting Up osTicket in Browser </h3>


<p align="center">
Continue Setting up osTicket in the browser. MySQL Database: osTicket ; MySQL Username: root ; MySQL Password: root ; Click “Install Now!”

</p>
</p>

![image](https://github.com/user-attachments/assets/effc9097-ddb3-4c46-8df7-eb302f47e73d)

</p>
<br />

<p align="center">
Congratulations, hopefully it is installed with no errors! Browse to your help desk login page: http://localhost/osTicket/scp/login.php

</p>
</p>

![image](https://github.com/user-attachments/assets/5c20d76c-d6be-473c-af2d-58d14a670537)

![image](https://github.com/user-attachments/assets/7358f64e-a032-4722-8b6d-bffc9662c314)


</p>
<br />

<p align="center">
End Users osTicket URL: http://localhost/osTicket/ 


</p>
</p>

![image](https://github.com/user-attachments/assets/61689245-e39e-48e2-a73f-a12dc9787316)

</p>
<br />

<h3 align="center">Conclusion</h3>

<p align="center">
Great job! You've successfully set up osTicket on your Windows virtual machine. To avoid unnecessary charges, be sure to shut down the VM in Azure when you're not using it. Well done on completing this project!
</p>
