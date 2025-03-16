<p align="center">
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

1. Azure Virtual Machine – Used to host the OsTicket system.

2. osTicket Installation Files – Necessary files for setting up the ticketing system.

3. HeidiSQL – A database management tool for MySQL to configure and manage the database.

<h2>Installation Steps</h2>


<p>
First I Downloaded the osTicket Installation files, then I opened the Zip folder and extracted the installation files to the Desktop of the VM.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
Next I needed to Install / Enable IIS (Internet Information Services) in windows with CGI, to do so i opened the control panel, on the side panel i selected "Turn Windows features on or off", in the popup window i selected Internet Information Services to turn it on and also expanded it to show the option for world wide web services, after expanding WWW services i was able to turn on CGI 
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
then I installed the PHP manager from the osTicket Instalation files downloaded earlier. Just hit, Next, Agree, Next... then it will install, also from the same folder i installed the rewrite module
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
Next I created the directory PHP on the C: Drive
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
Then I unzipped/Extracted the (php-7.3.8-nts-Win32-VC15-x86.zip) folder into the newly created PHP folder on the C: Drive
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
From the "osTicket-Installation-Files" folder, I installed both "VC_redist.x86.exe" and "MySQL-5.5.62-win32" , When installing MySQL I chose to use the Typical settings. Once Completed, Make sure to check the box next to "Launch the MySQL Instance Configuration Wizard".
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Next the MySQL Instance Configuration Wizard pops up, Select Next, then be sure to select "Standard Configuration" and select next.  Hit next again, Now it will ask for the root password. I chose to go with 'root" as the password for root access.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Next task was to open IIS(Internet Information Sevices) as admin. once it was opened, I double clicked on PHP manager, then i selected to Register new PHP version, I then selected the php-cgi.exe file from the C: Drive.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Now it is time to acually intall osTicket. First i extracted the OsTicket-v1.15.8 folder and copied the upload folder into "c:\inetpub\wwwroot" and then i Renamed the upload folder to "osTicket"
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Back in IIS(Internet Information Sevices), in left panel expand Sites, expand Default Web Site, Select osTicket, then on the right hand side under manage folder Select "Browse *:80(http)". Doing so opened osTicket in the web browser.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
I did note that some extensions are not enabled, so back in IIS -> Double click PHP Manager, then i selected "enable or disable extensions", I enabled: php_imap.dll, php_intl.dll, and php_opcache.dll. afterdoing so i reloaded the osTicket browser window.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
In the osTicket folder rename file "ost-sampleconfig.php" to "ost-config.php". then right click the file and select properties -> navigate to the Security tab and select advanced -> Select Disable inheritance -> and select "Remove all inherited permissions..."
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Now i am adding the permissions needed... -> Select a principal -> Type in Everyone (not good to do in real life situation, only for lab purposes). Also give Full Control...
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Now I head back to the browser to input my HelpDesk info...
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Before i could move forward i needed to go back to the folder with the OsTicket Installation files and install "HeidiSQL", once it finished installing and opened, i selected new to create new database for the ticketing system to use.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
With the datbase setup now, i finished connecting the ticketing system to the database in the browser... I filled in the information for: MySQL Database, MySQL Username, and MySQL Password and then I clicked on Install now
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
osTicket has Successfully been installed, on the Left side is the Ticketing System where tickets can be placed, and on the right is the Agent login screen. 
 
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
