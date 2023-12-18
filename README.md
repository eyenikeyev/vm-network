<p align="center">
<img src="https://github.com/ColtonTrauCC/vm-network/assets/147654000/2cb238ff-4e46-4a75-8967-7ef5d124ab74" height="15%" width="15%" alt="Microsoft Azure logo"/>
</p>

<h1 align = "center">Virtual Machine Network in Microsoft Azure</h1>
This tutorial outlines how to set up an Virtual Machine Network in Microsoft Azure and doing some exercises observing traffic.

<br />

<h2>Environments and Technologies </h2>

<ul>
<li>Microsoft Azure (Virtual Machines/Compute)</li>
<li>Microsoft Remote Desktop</li>
<li>Windows Command Prompt</li>
<li>Wireshark</li>
<li>Network Protocols</li>
</p>
DNS: Domain Name System
</p>
ICMP: Internet Control Message Protocol
</p>
SSH: Secure Shell
</p>
RDP: Remote Desktop Protocol
</p>
<ul>
<p>
</ul>
</ul>

</br>

<h2>Operating Systems </h2>
<ul>
  <li>Windows 10 (21H2)</li>
  <li>Linux (Ubuntu 20.04)</li>
</ul>

</br>

<h2>List of Prerequisites</h2>
<ol>
  <li>Microsoft Azure Account and Subscription</li>
  <li>Access to Microsoft Remote Desktop Connection. For MacOS users, follow <a href = "https://www.youtube.com/watch?v=0lllpAhgAJs&ab_channel=TheHostingVideos">this video</a> to use Remote Desktop on Mac</li>
</ul>
<li>Notepad (Optional): for typing down log in information for our Virtual Machines</li>
</ol>
</p>
</ol>

<h2>Installation Steps</h2>

<h3>Creating our Resource Group and Virtual Machines</h3>

<p>
  <ul>
</li>
</p>
<b>Resource Group</b>: In the Azure Portal, go to resource groups to create a resource group and name it RG-Lab-01. Take note of the region of the resource group as it'll come in use when setting up the virtual machines. When finished, click on Review + Create.</li>
<p>
<img src="https://i.imgur.com/VhKtvlv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<b>Virtual Machine</b>: Access Azure Portal, go to Virtual Machines to create an azure virtual machine. Select the resource group we've created (RG-Lab-01) and name it VM-1. Make sure the Region is the same as the resource group previously created. To set the Availability Options, set it to No Infrastructure and Security Type to Standard.</i>
</p>
<b>Image</b> (Operating System): set it to Windows 10 Pro, Version 22H2, x64 Gen2</li>
</p>
<b>Size</b>: the general processing power and RAM of the VM, set it to Standard_E2s_V3 which provides 2 virtual cpus and 16 GBs of RAM</li>
<p>
<img src="https://i.imgur.com/AcVLLhH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Set the username and password of your VM for logging in and make sure to check the box for licensing agreements
<p>
Go to the Network tab, notice the Virtual Network created by the Virtual Machine by the Resource Group. It will be made automatically by the Virtual Machine
<p>
<img src="https://i.imgur.com/oa1kwem.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
Click on Review + Create to deploy the virtual machine. Wait approximately five to ten minutes to fully deploy before continuing
</p>
<b>Virtual Machine 2</b>: same process as Virtual Machine 1 except name it VM-2 and set the image to Ubuntu Server 20.04 LTS x64 Gen2. Ubuntu by default has their Administrator account authentication as SSH public key, so we must set it as Password for logging in through Remote Desktop
</p>
<img src="https://i.imgur.com/DJtKqDb.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
</ul>
</p>

<br />

<h3>Logging into a Virtual Machine using Remote Desktop Connection</h3>

<p>
  <ul>
<p>
In Azure Portal go to Virtual Machines, go to Overview, go to Public IP Address section and copy it. Open Remote Desktop Connection and paste it there, then click Connect. Log in using the username and password you set up for VM1 (a pop up may show for verification, click "Yes" if it does)
<p>
<img src="https://i.imgur.com/cMqnoKP.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
You have successfully logged into the Virtual Machine
<p>
<img src="https://i.imgur.com/8liNZe7.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
</p>

<br />

<h2>Observing Traffic in Virtual Machines</h2>
<p>
Open a web browser (Microsoft Edge) in the virtual machine. Search for and install <a href="https://www.wireshark.org/download.html">Wireshark</a>.
<p>
</p>

<br />

<h3>Observing ICMP Traffic</h3>

<p>
Open Wireshark and start capturing packets (blue fin icon). In the filter bar type icmp to filter incoming ICMP packets
<img src="https://i.imgur.com/9f2LFVp.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Go to the Azure Portal on the physical desktop, go to VM2 and note its private ip address
<p>
Open Windows Powershell in VM1 and in the command line enter ping [VM2 Private IP]. Then ICMP packets should display in Wireshark
<p>
<img src="https://i.imgur.com/7GnDrxc.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
