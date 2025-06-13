<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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

- Observe ICMP Traffic
- Configure Firewalls
- Observe SSH Traffic
- Observe DNS Traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In order to get started we need to log into Azure and create our resource group and Virtual machine. We want to create a linux VM and a Windows VM. Make sure that the VM and resource group are in the same group. After this we can log into the Windows VM and open up edge then type up Wireshark and download it. Once it is downloaded we want to start packet capture and we want ICMP traffic only. Now we can grab the IP adress of the Linux Vm we just created in Azure and we will try to ping it from our Windows VM. We should now be able to observe traffic in wireshark in the current VM and in Powershell we can ping the Linux VM from our windows VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When we open up the security group in our Ubuntu VM we disable inbound ICMP traffic. Now when we go back into wireshark and ping we can see that we dont get a response back.
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we are going to look at all of the different kinds of traffic you can see going back and forth in systems. First we'll start with SSH traffic, in wireshark we want to start a capture but only filter for SSH traffic. We will use our Ubuntu VM IP address into powershell and can type different commands like ping and we can observe the traffic spam. For DHCP traffic filter only for DHCP traffic then we put in a new IP from the command line and we are going to run powershell as an admin and type ip config/ renew and we can observe the DHCP traffic in wireshark. DNS traffic only filter for that traffic. we can grab disneys IP address from nslookup and we can see the DNS from wireshark. It may be privated but it still shows the IP as disney. Then for RDP traffic, theres going to be non-stop traffic because its receiving constant information from the other VM we have, instead of it just doing it by us giving it a command. 
</p>
<br />
