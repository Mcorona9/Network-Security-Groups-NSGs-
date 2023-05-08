
<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/upyqEZc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As the first step we are going to create two virtual machines, one running Microsoft and the other Linux.
</p>
<br />



<p>
<img src="https://i.imgur.com/WIqmHHm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After successfully creating the the two VM's we can utilize the Network watcher topology to observe the VM's connected to the same virtual network and the whole enviroment over all. 
</p>
<br />

<p>
<img src="https://i.imgur.com/2VKzwU3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the third step we are going be remote connecting into the VM1 and from within we will be installing Wireshark(Network Protocal Analyzer) for the purpose of viewing network traffic between the two virtual machines.
</p>
<br />

<p>
<img src="https://i.imgur.com/2RtuDIk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image above reperesents Wireshark already installed into the VM1 and we could already see activity withing itself. 
</p>
<br />

<p>
<img src="https://i.imgur.com/5WrdQTY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we will go ahead and copy the private ip adress from VM2 in oder to ping it from within VM1 utilizing Powershell. The image above shows the traffic from the two virtual machines after pinging the VM. We can see two different IP address interacting with one another.
</p>
<br />

<p>
<img src="https://i.imgur.com/q6bIGkq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On this section we initialized the forever ping by inputing the private ip adress from VM2 and using commadn - t and the purpose for this is because now we will be changing some settings in the VM2's firewall to essentially not allow any more traffic from imcp whih is the protocol that ping uses in we will not block the incoming traffic.
</p>
<br />

<p>
<img src="https://i.imgur.com/pt0dQSA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After making some changes to the firewalls settings in VM2 we can already see the none stop ping from VM1 comming to a stop as it is now being blocked off.
</p>
<br />

<p>
<img src="https://i.imgur.com/2dmPV0d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we will longing to vm2 from vm1 using SSH command in powershell.
</p>
<br />

