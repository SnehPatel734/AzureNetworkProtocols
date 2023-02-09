<p align="center">
<img src="https://i.imgur.com/vfTt8Tp.png" height="45%" width="45%" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Creating Resource Groups
- Spinning Up Virtual Machines
- Connecting Virtual Machines On The Same Network
- Monitor/Send Traffic Between VM's

<h2>Actions and Observations</h2>
<p>
First, we need to create a resource group which is a container that holds Azure resources. For our purposes we are going to be creating two virtual machines and adding them into this resource group.
</p>

<p>
<img src="https://i.imgur.com/t3HwTEo.png" height="80%" width="80%" alt="Resource Group"/>
</p>
<p>
Next we will create 2 virtual machines one running Windows 10 and the other running Ubuntu 20.04 LTS. To create a VM in Azure we search for "virtual machine" in the search bar at the top. Create an "Azure virtual machine" selecting the resource group we made earlier. You can name it however you like, and select the Windows 10 Pro thats free tier eligible for our purposes. Also make sure you remember the availability zone and set an appropriate username/password for this VM; this will come in handy later.
</p>
<br />

<p>
<img src="https://i.imgur.com/RLym8dW.png" height="80%" width="80%" alt="VM1"/>
</p>

<p>
 We don't have to worry about any other setting except Network for now let it auto-create a new Virtual Network, Subnet and IP.
</p>
<br />

<p>
<img src="https://i.imgur.com/GQz1yuF.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
