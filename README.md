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
  <ul>
  <li>DNS - Domain Name System
  <li>ICMP - Internet Control Message Protocol
  <li>SSH - Secure Shell
  <li>RDP - Remote Desktop Protocol
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
<b>Virtual Machine</b>: Access Azure Portal, go to Virtual Machines to create an azure virtual machine. Select the resource group we've created (RG-Lab-01) and name it VM-1. Make sure the Region is the same as the resource group previously created. To set the Availability Options, set it to No Infrastructure and Security Type to Standard.
<li>
</p>
<b>Image</b> (Operating System): set it to Windows 10 Pro, Version 22H2, x64 Gen2
<li>
</p>
<b>Size</b>: the general processing power and RAM of the VM, set it to Standard_E2s_V3 which provides 2 virtual cpus and 16 GBs of RAM
<p>
<img src="https://i.imgur.com/AcVLLhH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Set the username and password of your VM for loggin in and make sure to check the box for licensing agreements
