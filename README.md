<p align="center">
<img src="https://i.imgur.com/gLK8kv9.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1 align = "center"> Configuring Active Directory in Azure </h1>
This tutorial outlines the execution of Active Directory within Azure Virtual Machines. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

<p>
The first thing that is needed is a resource group on portal.azure.com. 
</p>
<p align="center">
<img src="https://i.imgur.com/uaGQ6cG.png" height="45%" width="45%" />
  
<p>
Once that is done, I am now creating a Domain Controller VM in Windows Server 2022 and naming it DC-1. After allowing sufficient time for the setup, I set the Domain Controller’s NIC IP address to be static. 
</p>
<p align="center">
<img src="https://i.imgur.com/dS6kioQ.png" height="45%" width="45%" />

<p>
 I have used the same Resource Group and Vnet that was created beforehand. To make sure that both VMs are in the same Vnet, I have checked the topology with Network Watcher. Using the previously established Resource Group and Vnet, I ensure both VMs share the same network by verifying the topology using Network Watcher.
</p>
<p align="center">
<img src="https://i.imgur.com/nKHfipe.png" height="45%" width="45%" />

<p>
I logged into Client-1 via Remote Desktop and began a continuous ping DC-1’s private IP address using the command ‘ping -t <ip address>’ 
</p>
<p align="center">
<img src="https://i.imgur.com/ZfN9JYN.png" height="45%" width="45%" />

<p>
I logged into the Domain Controller and activated ICMPv4 within the local Windows Firewall settings.
</p>
<p align="center">
<img src="https://i.imgur.com/hmykDIh.png" height="40%" width="40%" />
<p align="center">
<img src="https://i.imgur.com/OARRAUk.png" height="45%" width="45%" />

<p>
On client-1 I am verifying the ping success
</p>
<p align="center">
<img src="https://i.imgur.com/6F6OlnK.png" height="50%" width="50%" />

<p>
I am installing the Active Directory Domain Services on DC-1
</p>
<p align="center">
<img src="https://i.imgur.com/BTFimVT.png" height="50%" width="50%" />
<p align="center">
<img src="https://i.imgur.com/XXr6htT.png" height="50%" width="50%" />


<p>
Promoting as a Domain Controller: I've launched a new forest with the domain name mydomain.com
</p>
<p align="center">
<img src="https://i.imgur.com/jcHMknq.png" height="50%" width="50%" />

<p>
Restart and then log back into DC-1 as user: mydomain.com\chels31218
</p>
<p align="center">
<img src="https://i.imgur.com/IDypQwI.png" height="40%" width="40%" />
<p align="center">
<img src="https://i.imgur.com/2O5lRAj.png" height="45%" width="45%" />
