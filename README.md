<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>SSH Connection from VM to VM</h1>
In this tutorial, we will practice SSH connection within Azure Virtual Machines connecting from a Windows VM to a Linux VM, and monitor SSH traffic with Wireshark. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- SSH Network Protocol
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 Pro
- Ubuntu Server 22.04

<h2>Actions and Observations</h2>

Open Remote Desktop connection and connect to your Windows VM (refer to [Monitoring Traffic in Azure VMs - Observe ICMP Traffic](https://github.com/JackieG8803/Monitoring-Traffic-in-Azure-VMs---Observe-ICMP-Traffic)) 

Run WireShark and filter display to only view SSH traffic:

![Screenshot 2024-09-13 165259](https://github.com/user-attachments/assets/47c231eb-ddf5-4740-9843-85ea682465f3)

Open PowerShell and run the command 'ssh (username)@(public ip address)'
In my case, it is 'ssh labuser@10.0.0.5', then hit Enter. 

PowerShell will prompt you to enter the password securely.

Next, you should see the following:

![Screenshot 2024-09-13 165440](https://github.com/user-attachments/assets/2a1c2770-aa62-4c83-b210-8a30e3eee580)
![Screenshot 2024-09-13 165514](https://github.com/user-attachments/assets/a2d68d2a-e7f7-44e8-a47a-49d0433b63ad)

We have now successfully connected to our Linux VM via SSH. 

We can verify our connection with the command 'hostname' indicating we are acting in the Linux VM under PowerShell.

![Screenshot 2024-09-13 165922](https://github.com/user-attachments/assets/f01a3868-b1a7-4ca9-83ed-0598158ff324)

We can also verify the connection in WireShark, under the Transmission Control Protocol dropdown to see the network activity operating in Port 22 (SSH).

![Screenshot 2024-09-13 170030](https://github.com/user-attachments/assets/57134e2a-0590-48e6-b92e-991fc8df97f6)

Lastly, don't forget to close the SSH connection: type 'exit' in PowerShell to drop connection.

![Screenshot 2024-09-13 170404](https://github.com/user-attachments/assets/58439545-a1d9-4d54-aeae-a2615f7df371)

