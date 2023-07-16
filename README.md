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
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>In Microsoft Azure, create a Windows 10 Virtual Machine within a Resource Group.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/b2cbbafc-530e-48a2-83a0-2d1dacbc166a" height="80%" width="80%" alt="VM Creation"/></p>
<p>The more CPUs and memory the better. Use any username and password.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/093be17e-1be6-46b1-8b0c-6a430d1cb644" height="80%" width="80%" alt="VM Creation"/></p>

<p>Once your VM has been created, copy its public IP address.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/45a9d6b4-a286-4e6c-b74d-e5695568e7d7" height="80%" width="80%" alt="VM Public IP"/></p>
<p>In Remote Desktop Connection, enter your VM's public IP and log in using the username and password you chosen while creating your VM. Connect even if you get a certificate error.</p>
<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/fcf5cc21-45f5-422e-9012-6259b0e7595d" height="80%" width="80%" alt="VM Public IP"/></p>

<p>
Once you connect to your VM, accept your desired privacy settings if prompted and then enable the following through Windows Features:
<br>Internet Information Services->Web Management Tools->IIS Management Console
<br>Internet Information Services->World Wide Web Services->Application Development Features->CGI
<br>Internet Information Services->World Wide Web Services->Common HTTP Features
</p>

<p><img src="https://github.com/VTeas2000/osticket-prereqs/assets/60052902/2462a7f1-bad3-4f84-813c-e621bb4dd8d4" height="80%" width="80%" alt="Windows Features"/></p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
