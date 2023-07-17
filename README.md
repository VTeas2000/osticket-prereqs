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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure subscription
- [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Installation Steps</h2>

<p>In Microsoft Azure, create a Windows 10 Virtual Machine within a Resource Group.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/b2cbbafc-530e-48a2-83a0-2d1dacbc166a" height="80%" width="80%" alt="VM Creation"/></p>
<p>The more CPUs and memory the better. Use any username and password.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/093be17e-1be6-46b1-8b0c-6a430d1cb644" height="80%" width="80%" alt="VM Creation"/></p>

<p>Once your VM has been created, copy its public IP address.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/45a9d6b4-a286-4e6c-b74d-e5695568e7d7" height="80%" width="80%" alt="VM Public IP"/></p>
<p>In Remote Desktop Connection, enter your VM's public IP and log in using the username and password you chose while creating your VM. Connect even if you get a certificate error.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/fcf5cc21-45f5-422e-9012-6259b0e7595d" height="80%" width="80%" alt="VM Public IP"/></p>

<p>
Once you connect to your VM, accept your desired privacy settings if prompted and then enable the following through <b>Windows Features</b>:
<br>Internet Information Services->Web Management Tools->IIS Management Console
<br>Internet Information Services->World Wide Web Services->Application Development Features->CGI
<br>Internet Information Services->World Wide Web Services->Common HTTP Features
</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/2462a7f1-bad3-4f84-813c-e621bb4dd8d4" height="80%" width="80%" alt="Windows Features"/></p>

<p>The next step is to access the <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>.</p>
<p>First, download and install <b>PHPManagerForIIS_V1.5.0.msi</b> and <b>rewrite_amd64_en-US.msi</b></p>
<p>Then, download <b>php-7.3.8-nts-Win32-VC15-x86.zip</b> and unzip its contents into a new directory <b>C:\PHP</b></p>
<p>Download and install <b>VC_redist.x86.exe</b> and <b>mysql-5.5.62-win32.msi</b></p>
<p>When installing MySQL 5.5.62:</p>
<p>Typical Setup->Launch Configuration Wizard (after install)->Standard Configuration->Install As Windows Service->Create Root Password</p>

<p>Next, run IIS as an administrator.</p>
<p>Open the PHP manager.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/076c0447-4b98-4d15-9f1f-dc0e37d5989e" height="80%" width="80%" alt="IIS"/></p>
<p>Register a new PHP version.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/169da122-e23b-45ba-a6e3-44661f0fca44" height="80%" width="80%" alt="New PHP"/></p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/42c788d7-fd96-4dff-a25c-37002523f891" height="80%" width="80%" alt="New PHP"/></p>
<p>To the right of the main IIS menu, either Restart or Stop and Start the server.</p>

<p>
Next, download <b>osticket-v1.15.8.zip</b> from the <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>.
<br>Extract and copy "upload" folder to C:\inetpub\wwwroot
<br>Within C:\inetpub\wwwroot, rename "upload" to "osTicket"
</p>

<p>Close IIS and run it as an adminstrator again. On the left side, go to Sites->Default Web Site->osTicket. On the right side, click "Browse *:80 (http)"</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/952faf93-ab5c-460b-93c6-3991c4e8240f" height="80%" width="80%" alt="IIS"/></p>

<p>
Not all of the extensions will be enabled. In IIS, Sites->Default Web Site->osTicket, open the PHP Manager.
<br>Click "Enable or disable an extension"
<br>Enable <b>php_imap.dll</b>
<br>Enable <b>php_intl.dll</b>
<br>Enable <b>php_opcache.dll</b>
<br>Refresh the osTicket site in your browser and observe the changes.
</p>

<p>
Go to C:\inetpub\wwwroot\osTicket\include\ and rename <b>ost-sampleconfig.php</b> to <b>ost-config.php</b>
<br>Right-click <b>ost-config.php</b>, go to Properties->Security->Advanced->Disable inheritance->Remove all
<br>Add->Select a principal->Everyone->Full control
</p>

<p>
In the browser, click "Continue" to set up osTicket.
<br>Fill out the System Settings and Admin User with your own values.
</p>

<p>
Download and install HeidiSQL from the <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a>.
<br>Launch HeidiSQL. Create a new session, and input your username (root) and password that you created for MySQL. Click "Open". Create a database called "osTicket"
</p>

<p>
Back in the browser, set the following for Database Settings:
<br>MySQL Database: osTicket
<br>MySQL Username: root
<br>MySQL Password: <your password>
Click "Install Now"
</p>

<p>
Delete: C:\inetpub\wwwroot\osTicket\setup
<br>For C:\inetpub\wwwroot\osTicket\include\ost-config.php, set permissions to "Read & execute" and "Read" only.
</p>

<p>You can log in using the admin user credentials you created at <a href="http://localhost/osTicket/scp/login.php"></p>
