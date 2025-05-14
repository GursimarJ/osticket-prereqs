<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This is a walkthrough/tutorial that outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. At the end of this walkthrough, we will have a admin/analyst login page and a end users osTicket URL.<br />


<h2>Environments Used</h2>

- Microsoft Azure
- macOS (Host Machine)
- Windows 10 (Virtual Machine)
- Windows App (Remote Desktop)
- Internet Information Services (IIS)

<h2>Technology/Applications/Services </h2>

- osTicket
- Azure Virtual Machines
- MySQL
- HeidiSQL
- PHP Manager for IIS



<h2>Walkthrough</h2>



Go to the azure portal and go to the Virtual Machine to Create a new virtual machine.
  
![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic1.png)
</p>
<br />
<p>
Create a new virtual machine -  Windows 10, 2 vCPUs
  


![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic2.png)
</p>
<br />
<p>
Use Windows App(Remote Desktop) to log in to the new VM we created
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic3.png)
</p>
<br />
<p>
Download the following: osTicket-Installation-Files.zip -> (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- It contains all the necessary files to install osTicket and some of its dependencies
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic4.png)
</p>
<br />
<p>
Extract/Unzip to access the files on our desktop
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic5.png)
</p>
<br />
<p>
Need to Install/Enable IIS in Windows<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Click on Windows start menu -> Control Panel -> Programs -> Turn Windows features on or off -> Check Internet Information services
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic6.png)
</p>
<br />
<p>
Install CGI<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Expand Internet Information Services -> Worldwide Web Services - Application Development Features -> CGI
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic7.png)
  *Computer is technically a Web server after this step.
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic8.png)
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic9.png)
</p>
<br />
<p>
Create the new directory C:\PHP
  
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic10.png)
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic11.png)
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic12.png)
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
- Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic13.png)
</p>
<br />
<p>
Username: root | Password: root

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic14.png)
</p>
<br />
<p>
Open IIS as an Admin
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic15.png)
</p>
<br />
<p>
Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic16.png)
</p>
<br />
<p>
Reload IIS (Open IIS, Stop and Start the server)
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic17.png)
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

</p>


![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic18.png)
</p>
<br />
<p>
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic19.png)
</p>
<br />
<p>
Reload IIS (Open IIS, Stop and Start the server)
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic20.png)
</p>
<br />
<p>
Go to sites -> Default -> osTicket -> On the right, click “Browse *:80”
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic21.png)
</p>
<br />
<p>
Some important extensions are not enabled:<br />
Go back to IIS, sites -> Default -> osTicket -> Double-click PHP Manager<br />
Click “Enable or disable an extension”<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Enable: php_imap.dll<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Enable: php_intl.dll<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Enable: php_opcache.dll<br />

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic22.png)
</p>
<br />
<p>
Refresh the osTicket site in your browser, observe the changes
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic23.png)
</p>
<br />
<p>
Rename: ost-config.php:<br />
-From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php<br />
-To: C:\inetpub\wwwroot\osTicket\include\ost-config.php<br />

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic24.png)
</p>
<br />
<p>
Right click “ost-config.php” -> Properties -> Security -> Advanced -> Disable inheritance -> Remove All
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic25.png)
</p>
<br />
<p>
“Add” New Permissions -> Principal -> Enter the object name to select “Everyone” 
-> Check All

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic26.png)
</p>
<br />
<p>
Continue Setting up osTicket in the browser (click Continue)<br />
- Name Helpdesk<br />
- Default email (receives email from customers)<br />
- Fill out Admin User<br />

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic27.png)
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL.
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic28.png)
</p>
<br />
<p>
 - Open Heidi SQL<br />
 - Create a new session, root/root<br />
 - Connect to the session<br />
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic29.png)
</p>
<br />
<p>
Create a database called “osTicket”
</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic30.png)
</p>
<br />
<p>
Continue Setting up osTicket in the browser<br />
 - MySQL Database: osTicket<br />
 - MySQL Username: root<br />
 - MySQL Password: root<br />
 - Click “Install Now!”<br />

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic31.png)
</p>
<br />
<p>
osTicket is successfully installed

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic32.png)




