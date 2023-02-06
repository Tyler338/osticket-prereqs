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

- Microsoft Azure Subscription
- osTicket installation files


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/azKx6SW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, create a new Resource Group in Microsoft Azure Cloud Service. Name this Resource Group "OSTICKET". Create a virtual machine (VM) on the same page and name it "vmosTicket" or anything you like. Pick a region to host the VM in and remember the location. This is important because the two VM's we'll be creating for this project need to use the same region. Pick Windows 10 in the image section. This will be the operating system your VM will use. For the size section pick one that uses 2 cpu's. Lastly, Click review and create to finialize the Resource group and VM creation.
</p>
<br />

<p>
<img src="https://i.imgur.com/cpFMYM1.png" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, create a second VM inside the already excisting Resource Group "OSTICKET". Name this VM "vmosTicket2" and pick the same region as used when creating the first VM. Choose windows 10 as the operating system and use at least 2 cpu's for the size. Click review and create to finalize the VM creation.
</p>
<br />

<p>
<img src="https://i.imgur.com/MLPnstq.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/lAkffSs.png" alt="Disk Sanitization Steps"/>
</p>
<p>
Now that this is installed lets [download](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) the installations files needed for osTicket and HeidiSQL.
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
- Once you have installed MySQL Server you will need to create credentials for the MySQL Server. 


<img src="https://i.imgur.com/sX8jxmX.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5OMhW4o.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/dA7bSgp.png" alt="Disk Sanitization Steps"/>
Open IIS Manager as an Admin, Register the PHP using the PHP folder

