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
First, we need to create a resource group which is a container that holds Azure resources. For our purposes we are going to be creating two Virtual Machines and adding them into this resource group.
</p>
<br />
<p>
<img src="https://i.imgur.com/t3HwTEo.png" height="80%" width="80%" alt="Resource Group"/>
</p>
<br />
<p>
Next we will create 2 virtual machines one running Windows 10 and the other running Ubuntu 20.04 LTS. To create a VM in Azure we search for "virtual machine" in the search bar at the top. Create an "Azure virtual machine" selecting the resource group we made earlier. You can name it however you like, and select the Windows 10 Pro thats free tier eligible for our purposes. Also make sure you remember the availability zone and set an appropriate username/password for this VM; this will come in handy later.
</p>
<br />
<p>
<img src="https://i.imgur.com/RLym8dW.png" height="80%" width="80%" alt="VM1"/>
</p>
<br />
<p>
We don't have to worry about any other setting except Network for now let it auto-create a new Virtual Network, Subnet and IP. Now just create and review to finilize and create the VM.
</p>
<br />
<p>
<img src="https://i.imgur.com/GQz1yuF.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
Now lets create the Ubuntu VM following the same steps making sure the VM is in the same resource group and availability zone. As well as the same Virtual Netowrk and Subnet. You can go back to the resource group page and you will see inside our created resource group, there is a VM running as well as a newly created resource group.
</p>
<br />
<p>
<img src="https://i.imgur.com/4COApF3.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
If you did everything correctly, your network should look like this.
</p>
<br />
<p>
<img src="https://i.imgur.com/wTgnwjk.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
Now we RDP (Remote Desktop Protocol) into the Windows VM, and start the important part of this Lab, network communication between the two VM's.
</p>
<br />
<p>
Using Remote Desktop Connection that is built into Windows, you can take the public IP of your Windows VM and connect using the username and password you created.
</p>
<br />
<p>
<img src="https://i.imgur.com/G5S3g3Y.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
Also now we can check if our Ubuntu VM is running via SSH from our Windows VM as well as monitoring the SSH traffic on Wireshark.
</p>
<br />
<p>
<img src="https://i.imgur.com/MTiSPRI.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
Now we can moniter ICMP (Internet Control Message Protocol) traffic sent from our Windows VM to the Ubuntu VM. All we need is to filter ICMP in Wireshark and send a ping to our Ubuntu VM's private IP.
</p>
<br />
<p>
<img src="https://i.imgur.com/4j0J4Tk.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
Let's say we dont want any ICMP traffic sent to our Ubuntu VM, well we can configure the Netowrk Rule for that specific VM to block all ICMP traffic basically setting up a firewall for network security.
</p>
<br />
<p>
<img src="https://i.imgur.com/m09HVfC.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
Now sending any packages over to our Ubuntu VM will fail. Lets try pinging one more time.
</p>
<br />
<p>
<img src="https://i.imgur.com/jET9RMs.png" height="80%" width="80%" alt="VM1-Network"/>
</p>
<br />
<p>
As you can see no reply form out Ubuntu machine. This was a simple demonstration on how to set up virtual machines on the same network and setting security rules to either allow or deny communication between two machines on the same network in Microsoft Azure.
</p>
<br />

