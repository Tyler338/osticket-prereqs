# osticket-prereqs<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
<h2>This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<h2><br />

<h2>What is osTicket?<h2>

- osTicket is a widely-used open source support ticket system. It seamlessly integrates inquiries created via email, phone, and web-based forms into a simple easy-to-use multi-user web interface. Manage, organize and archive all your support requests and responses in one place while providing your customers with accountability and responsiveness they deserve.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Subscription
- osTicket installation files


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/azKx6SW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, create a new Resource Group in Microsoft Azure Cloud Service. Name this Resource Group "OSTICKET". Create a virtual machine (VM) on the same page and name it "vmosTicket" or anything you like. Pick a region to host the VM in. Pick Windows 10 in the image section, this will be the operating system your VM will use. For the size section pick one that uses 2 cpu's. Lastly, Click review and create to finialize the Resource group and VM creation.
</p>
<br />

<p>

</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/MLPnstq.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/lAkffSs.png" alt="Disk Sanitization Steps"/>
</p>

In azure go to the VM "vmosticket" and copy the public IP address. Open Remote Desktop, paste the IP address, and connect to your VM. Now that that our VM is connected, let us enable IIS (Internet Information Services ). ISS is a Microsoft web server that runs on Windows operating system and is used to exchange static and dynamic web content with internet users. IIS can be used to host, deploy, and manage web applications using technologies such as ASP.NET and PHP. You'll need to find "CGI" within IIS and enable it.
- Start Menu > Windows Feature > Internet Information Services > World Wide Web Services > Application Development Features > CGI

- Now that we have this installed lets [download](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) the files needed for osTicket and HeidiSQL.
<img src="https://i.imgur.com/FIQFo0g.png" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

- From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
<img src="https://i.imgur.com/0qAZLWE.png" alt="Disk Sanitization Steps"/>

- Create the directory C:\PHP
- From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
- From the Installation Files, download and install VC_redist.x86.exe.
- From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
- Once you have installed MySQL Server you will need to create credentials for the MySQL Server. Write the credentials down as they'll be needed later once we setup HeidiSQL.


<img src="https://i.imgur.com/sX8jxmX.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5OMhW4o.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/dA7bSgp.png" alt="Disk Sanitization Steps"/>
Everything except HeidiSQL (will be installed later) should be installed now and we'll begin to use/configure IIS manager which we need to run osTicket. Within IIS we'll use PHP Manager to register a new version which includes CGI. We installed CGI earlier in IIS.

- Open IIS Manager as an Admin, Register the PHP using the file "php-client" within the PHP folder that's located in C:.

 

<img src="https://i.imgur.com/X0qHOe9.png" alt="Disk Sanitization Steps "/>
<img src="https://i.imgur.com/aBhRiqU.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/n6byJt1.png" alt="Disk Sanitization Steps"/>
Now that our PHP is registered we need to enable some extensions that are currently disabled. In IIS Manager, open PHP Manager, and click "enable or disable an extension". We need to enable three extensions by the name of php_imap.dll, php_intl.dll, php_opcache.dll. Now reload IIS manager and make your way to "Sites > Default > osTickets" and on the right side, click " Browse *:80" to open the osTicket web-interface. 

On this page you can see the requirements needed for osTicket and some of the extensions we enabled. If your page doesn't open or some of the extensions aren't enabled you missed a step along the way. Be sure the folder "osTicket" is spelled exactly like this with the capital T. If it's still not working I suggest restarting the tutorial. 

<img src="https://i.imgur.com/scD9EuC.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/npem9ld.png" alt="Disk Sanitization Steps"/>

Now lets step back and return to c:\inetpub\wwwroot\osticket\include. Once you find it look for the file named "ost-sample-config.php" We will rename it to "ost-config.php". Once that is completed, right click the file, open properties under the secruity tab and click advanced. Now click "Disable Inheritance", then Remove all new permissions and give everyone permissions.

<img src="https://i.imgur.com/Ifh74Wg.png" alt="Disk Sanitization Steps "/>
<img src="https://i.imgur.com/FMCRIhJ.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Imv06P2.png"/>

- Now we'll return to the osTicket webpage so we can finish the installation process. Click continue and you will need to give your help desk a name, an email, and an admin user profile. Put anything you'd like but document all the information because it will be used later once osTicket is installed and running.
- Next we'll need to download and install HeidiSQL which can be found [here](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).
- After installation you need to launch heidiSQL and input your username and password that you created (from MySQL server). Connect to a new session using the same information from MySQL and create a database called "osTicket". Return to the osTicket browser we have open and fill out the rest of the page.

<img src="https://i.imgur.com/TuVbn9p.png" alt="Disk Sanitization Steps "/>
Lastly click "install now" at the bottom of the osTicket browser. You've now succesfully setup your own ticketing system and database!

<img src="https://i.imgur.com/jWufN79.png" alt="Disk Sanitization Steps "/>
<img src="https://i.imgur.com/KC6y3pW.png" alt="Disk Sanitization Steps "/>
This final section for osTicket installation is cleanup to setup for post installation.

- Delete: C:\inetpub\wwwroot\osTicket\setup
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php



