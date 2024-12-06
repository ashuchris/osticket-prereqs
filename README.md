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

- Azure Virtual Machine
- Internet Information Services (IIS)
- osTicket Installation Files (https://docs.google.com/document/d/1DyjX8LeVU98LjhXO2t2K2F0aHywI2N9GD57T3taO5qo/edit?tab=t.0)
- PHP Manager for IIS
- Rewrite Module
- MySQL
- VC Redist
- Heidi SQL

<h2>Installation Steps</h2>

<p>
The first thing we have to do is set up our virtual machine in Azure. So sign into your Azure portal and create a Windows 10 vm with at least 2 Vcpus.
  After doing that we have to use remote desktop to login into our Windows VM by using our vms public IP address.
</p>
<p>
<img src="https://i.imgur.com/madXwPZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Make sure to download the Os Ticket installation files and extract them to our desktop. You should end up with something like this.
</p>
<p>
<img src="https://i.imgur.com/Fe9rJX3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
We now Install and Enable IIS in Windows WITH CGI. Go to your control panel and locate uninstall a program.
</p>
<p>
<img src="https://i.imgur.com/7hClpMF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
click on turn windows features on or off. Follow this directory to enable and install IIS with CGI.Make sure to check the boxes. World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<p>
<img src="https://i.imgur.com/f1q3yN9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
From the OsTicket Installation Files folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<p>
<img src="https://i.imgur.com/pSoRX37.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
From the OsTicket Installation Files folder, install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<p>
<img src="https://i.imgur.com/rwaEjBI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Create a folder named PHP in your C drive. Extract the PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) which is in the osTicket Installation Files folder into the “C:\PHP” folder that you created.

</p>
<p>
<img src="https://i.imgur.com/jkFDFfT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/3LY26Zl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
From the OsTicket Installation Files folder, install install VC_redist.x86.exe
</p>
<p>
<img src="https://i.imgur.com/pKXFILL.png." height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


<p>
From the OsTicket Installation Files folder, install install l MySQL 5.5.62 (mysql-5.5.62-win32.msi)
</p>
<p>
<img src="https://i.imgur.com/s3xP3pm.png." height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
In the installation wizard choose Typical and install. Leave the launch configuration box checked.
</p>
<p>
<img src="https://i.imgur.com/9jG0R2V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Launch the configuration wizard and check the standard configuration and click next
</p>
<p>
<img src="https://i.imgur.com/d55D5q2.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
For simplicity's sake, the password will be "root" and the username "root" and click next And click on execute.
</p>
<p>
<img src="https://i.imgur.com/kHMUs4g.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Now let's open ISS as an administrator. Go to the search bar type ISS and run it as admin
</p>
<p>
<img src="https://i.imgur.com/eaUDFae.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Now let's register PHP from within IIS. Click on PHP Manager
</p>
<p>
<img src="https://i.imgur.com/NYINfRX.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 Click on "register new PHP version" and follow the path to the php executable file (php-cgi.exe)
</p>
<p>
<img src="https://i.imgur.com/uN5w1ml.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 We restart the ISS server
</p>
<p>
<img src="https://i.imgur.com/JrTfCNF.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 in the Os ticket Installation files folder. unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot” directory and rename the "upload" folder to "osTicket". Then reload ISS again.
</p>
<p>
<img src="https://i.imgur.com/9aUc5ex.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 In ISS to branch out to sites -> Default -> osTicket -On the right, click “Browse *:80” on the right
</p>
<p>
<img src="https://i.imgur.com/jaW6zgW.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 We see that some extensions are not enabled 
</p>
<p>
<img src="https://i.imgur.com/yzJBXzJ.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Double click PHP manager"
</p>
<p>
<img src="https://i.imgur.com/zerVJRx.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 Click "Enable or disable an extension"
</p>
<p>
<img src="https://i.imgur.com/FhvJnXB.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 we have to enable the following extensions : Enable: php_imap.dll, Enable: php_intl.dll , Enable: php_opcache.dll. 
  Then refresh the browser and see if they have been enabled.
</p>
<p>
<img src="https://i.imgur.com/NlNcbSa.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 we now have to rename one of our files. Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the "ost-sampleconfig.php" file to "ost-config.php"
</p>
<p>
<img src="https://i.imgur.com/vGla6Dm.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Twybjv3.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 we now have to assign permissions to the file we just renamed. We do so by right-clicking on ost-config.php and clicking on properties. Click security, click on advance, and click on disable the inheritance and we select remove all inherited permissions from this object
</p>
<p>
<img src="https://i.imgur.com/K7rJvSg.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 Then click on Add. click on select principal, Type "everyone" in the box and click on check names and OK
</p>
<p>
<img src="https://i.imgur.com/Y4r9CYO.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 Then click on Add. click on Select Principal, Type "everyone" in the box, and click on check names and OK. Make the basic permissions full control. Click on Apply and OK
</p>
<p>
<img src="https://i.imgur.com/Y4r9CYO.png" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/rlvZa5D.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 Then we go back to the browser and click on continue to set up our OSTicket. Fill in the field with the appropriate details and leave the database section for now. We have to set up our  database. In our osTicket-Installation-Files folder, install HeidiSQL and launch the setup.
</p>
<p>
<img src="https://i.imgur.com/UMixw7y.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 Click on New. On the right side, we want the username and password to be both "root". Then we click open.
</p>
<p>
<img src="https://i.imgur.com/MbWOaDq.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
  Right-click on unnamed in HeidiSQL on the left and take "create new" then click "database". Name the database "osTicket" without any space in-between. Then go back to the browser and fill in the details for the database make sure the MySQL Database is "osTicket" and the password and user name are "root". Click on Install Now.
  </p>
<p>
<img src="https://i.imgur.com/GuKn8sV.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
  You should see a congratulatory screen like this and some login links. We have just installed OS Ticket.
  </p>
<p>
<img src="https://i.imgur.com/zreBSZg.png" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/broQ56E.png" alt="Disk Sanitization Steps"/>
</p>
<br />

<h1>Congratulations we just installed Os Ticket</h1>
