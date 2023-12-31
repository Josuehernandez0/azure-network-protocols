# Network-Security-Groups-NSGs-and-Inspecting-Network-Protocols
<p align="center">
<img src="https://i.imgur.com/OMcqJe2.png"/>
</p>
<p align="center">
<img src="https://i.imgur.com/IJEbSNn.png"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- First create a Resource Group
- Create a Virtual Machine in Windows
- Create a Virtual Machine in Linux
- Remote Desktop Connection into both VM
- Download Wireshark in VM1
- Open Command prompt and perform a endless ping -t from VM1 to VM2
- Create a Network Security Group in Azure for denying the endless ping
- Open Wireshark and monitor protocols (SSH,DNS,RDP, and ICMP)
- Open Powershell and log into VM2 using SSH
- Run Powershell Commands in VM2
- Exit VM1
- Delete Resource Groups in Azure for both VM's


<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/arfiadH.png"/>
</p>
<p>
First go to Microsoft Azure and type Resource Groups in the search bar
</p>
<br />

<p>
<img src="https://i.imgur.com/fPLfxWy.png"/>
</p>
<p>
Next for the Resource Group name type RG-LAB-02 and the region under US West US 3
</p>
<br />

<p>
<img src="https://i.imgur.com/vkTmURS.png"/>
</p>
<p>
Then go to the Review and Create section and let the validation passed
</p>
<br />

<p>
<img src="https://i.imgur.com/GlZ9usl.png"/>
</p>
<p>
Now go back to Resource Groups and you will see it was created
</p>
<br />

<p>
<img src="https://i.imgur.com/3XUSk1Y.png"/>
</p>
<p>
Type Virtual Machines in the search bar
</p>
<br />


<p>
<img src="https://i.imgur.com/6TE4oEG.png"/>
</p>
<p>
Now for the Resource Group click the one we created RG-LAB-02.
</p>
<br />

<p>
<img src="https://i.imgur.com/yzPT6cu.png"/>
</p>
<p>
Next type the VM name VM1, and the region under US West US 3, the Image under Windows 10 Pro, and the size under Standard E2s
</p>
<br />

<p>
<img src="https://i.imgur.com/FjP17Gw.png"/>
</p>
<p>
Next the username will be named labuser and the password can be your own unique password. The Licensing check the box
</p>
<br />

<p>
<img src="https://i.imgur.com/g9wTXn4.png"/>
</p>
<p>
Now go to the Networking tab and make sure the Virtual Network, Subnet, and Public IP all says (new)
</p>
<br />

<p>
<img src="https://i.imgur.com/ZVYz36f.png"/>
</p>
<p>
Now go to the Review and create tab and click the Create tab on the bottom left
</p>
<br />

<p>
<img src="https://i.imgur.com/BjbNgJc.png"/>
</p>
<p>
<img src="https://i.imgur.com/Ox6FroE.png"/>
</p>
<p>
Next let the deployment process load, once its done a green check will emerge near the deployment
</p>
<br />

<p>
<img src="https://i.imgur.com/rUvjWGu.png"/>
</p>
<p>
Next go type Virtual Machine and click VM1
</p>
<br />

<p>
<img src="https://i.imgur.com/wlMJfWd.png"/>
</p>
<p>
Now click create Azure Virtual Machine 
</p>
<br />

<p>
<img src="https://i.imgur.com/QxxMlvq.png"/>
</p>
<p>
Next click the Resource group name under RG-LAB-02, the Vritual Machine Name under VM2 and the region US WEST US 3
</p>
<br />

<p>
<img src="https://i.imgur.com/MSlLYKw.png"/>
</p>
<p>
Now for the Image put Ubuntu Sever Gen2 and the size under Standard E2
</p>
<br />

<p>
<img src="https://i.imgur.com/s7aYCSD.png"/>
</p>
<p>
Next for the authentication type click password, under Username type labuser and the password tpye the password
</p>
<br />

<p>
<img src="https://i.imgur.com/LxLbIma.png"/>
</p>
<p>
Now go to the networking tab and make sure virtual network, subent, and public IP all says (new)
</p>
<br />

<p>
<img src="https://i.imgur.com/ZVYz36f.png"/>
</p>
<p>
Next go to the Review and create tab and click create at the bottom left
</p>
<br />

<p>
<img src="https://i.imgur.com/74Eb00A.png"/>
</p>
<p>
<img src="https://i.imgur.com/74Eb00A.png"/>
</p>
<p>
Now the deployment process will begin. Then once it's done a green check will appear
</p>
<br />


<p>
<img src="https://i.imgur.com/ZZ3BWcB.png"/>
</p>
<p>
Next you can upload all the info in a notepad file
</p>
<br />

<p>
<img src="https://i.imgur.com/ubc6Uvd.png"/>
</p>
<p>
Next type Virtual Machine in the search bar
</p>
<br />

<p>
<img src="https://i.imgur.com/IUz7pkb.png"/>
</p>
<p>
<img src="https://i.imgur.com/pr6KRhh.png"/>
</p>
<p>
Next you will see the VM has been created click VM1 and copy the public IP address 
</p>
<br />

<p>
<img src="https://i.imgur.com/QJk8zIO.png"/>
</p>
<p>
Next type Remote Desktop Connection in the search bar
</p>
<br />

<p>
<img src="https://i.imgur.com/2tYkXUl.png"/>
</p>
<p>
Next type the public IP of VM1 in the computer seciton and click the connect buttton
</p>
<br />


<p>
<img src="https://i.imgur.com/x6KFSKS.png"/>
</p>
<p>
Next type the username as labsuer and the password as the password you created, then click the blue ok button
</p>
<br />

<p>
<img src="https://i.imgur.com/wiOnifE.png"/>
</p>
<p>
Then click the yes button 
</p>
<br />

<p>
<img src="https://i.imgur.com/KuxOylj.png"/>
</p>
<p>
Then click no for all of the following in the image above
</p>
<br />

<p>
<img src="https://i.imgur.com/NIJj3qn.png"/>
</p>
<p>
Then once the networking tab loads click the yes button 
</p>
<br />

<p>
<img src="https://i.imgur.com/kFWfFBb.png"/>
</p>
<p>
Next load Microsoft Excel and click start without yuor data 
</p>
<br />

<p>
<img src="https://i.imgur.com/MogctZ2.png"/>
</p>
<p>
Next click continue without this data
</p>
<br />

<p>
<img src="https://i.imgur.com/QWRb2PS.png"/>
</p>
<p>
Now click confirm and continue 
</p>
<br />

<p>
<img src="https://i.imgur.com/tKTR15Q.png"/>
</p>
<p>
Next click confirm and start browsing
</p>
<br />

<p>
<img src="https://i.imgur.com/9eTzf56.png"/>
</p>
<p>
Now type download wireshark in the search bar 
</p>
<br />

<p>
<img src="https://i.imgur.com/SKIeyMb.png"/>
</p>
<p>
Now click go to download 
</p>
<br />

<p>
<img src="https://i.imgur.com/yeofYAf.png"/>
</p>
<p>
Now click windows x64 installer 
</p>
<br />

<p>
<img src="https://i.imgur.com/KAdfnBf.png"/>
</p>
<p>
Once the process is done click the file to open in or go to file explorer and open the file in the downloads folder
</p>
<br />

<p>
<img src="https://i.imgur.com/gZvtIWZ.png"/>
</p>
<p>
Next go to file explorer and double click Wireshark to load the software
</p>
<br />

<p>
<img src="https://i.imgur.com/RniQhRO.png"/>
</p>
<p>
Now click next
</p>
<br />

<p>
<img src="https://i.imgur.com/DdpBbsG.png"/>
</p>
<p>
Now click next 
</p>
<br />

<p>
<img src="https://i.imgur.com/v4K0BRZ.png"/>
</p>
<p>
Now finally click Install
</p>
<br />

<p>
<img src="https://i.imgur.com/OdFJnJg.png"/>
</p>
<p>
The installation progess will start
</p>
<br />

<p>
<img src="https://i.imgur.com/znQbOdM.png"/>
</p>
<p>
Once the process is done click finish 
</p>
<br />

<p>
<img src="https://i.imgur.com/I9wwRiv.png"/>
</p>
<p>
Next type Wireshark in the search bar on the VM, then double click to open the software
</p>
<br />

<p>
<img src="https://i.imgur.com/oyxh2oc.png"/>
</p>
<p>
Next click the Ethernet on Wireshark
</p>
<br />

<p>
<img src="https://i.imgur.com/OnBKj6A.png"/>
</p>
<p>
Now go back to Miscrosoft Azure and click VM2, copy the  IP or the Private IP address 
</p>
<br />

<p>
<img src="https://i.imgur.com/PRSaS5f.png"/>
</p>
<p>
Now open Windows Powershell and type ping (then type the private IP address) Example >>[ping 10.0.0.4] 
</p>
<br />

<p>
<img src="https://i.imgur.com/dv2JdZW.png"/>
</p>
<p>
You can see that 4 packets where sent and received
</p>
<br />

<p>
<img src="https://i.imgur.com/WhYkE68.png"/>
</p>
<p>
Now we can ping a website to see the same results, ping www.google.com
</p>
<br />

<p>
<img src="https://i.imgur.com/feKYkuI.png"/>
</p>
<p>
Next we can do a endless ping by typing ping (then type the private IP address) -t Example >>[ping 10.0.0.4 -t] 
</p>
<br />

<p>
<img src="https://i.imgur.com/2QZOqaf.png"/>
</p>
<p>
Now go to Microsoft Azure and type Network Security Groups 
</p>
<br />

<p>
<img src="https://i.imgur.com/Ivma8gt.png"/>
</p>
<p>
Next click VM2 and then click +Add 
</p>
<br />

<p>
<img src="https://i.imgur.com/vPjoJCV.png"/>
</p>
<p>
Now source can be under any, Protocol you need to click ICMP and the action will be deny, because we are going to deny the endless ping to stop. The priority needs to be lower than all the others for this example I put 200 and the name will be DENYICMPPINGFROMANYWHERE
</p>
<br />

<p>
<img src="https://i.imgur.com/3DfGet9.png"/>
</p>
<p>
Now if we go back to VM1 we can see the ping stop when can now click Ctrl + C to go back to the home on commandline
</p>
<br />

<p>
<img src="https://i.imgur.com/jndlg9r.png"/>
</p>
<p>
Next type ssh in the search bar in Wireshark to see ssh traffic (SSH Stands for Secure Shell)
</p>
<br />

<p>
<img src="https://i.imgur.com/VKHBXNU.png"/>
</p>
<p>
Next type dns in the search bar in Wireshark to see dns traffic (DNS stands for Domain Name Systems)
</p>
<br />

<p>
<img src="https://i.imgur.com/Ri3Edk8.png"/>
</p>
<p>
Next type rdp in the search bar in Wireshark to see rdp traffic (RDP stands for Romote Desktop Protocol)
</p>
<br />

<p>
<img src="https://i.imgur.com/CLXgz4s.png"/>
</p>
<p>
Next each of these protocols have port numbers type tcp.port==22 this port is for ssh Secure Shell
</p>
<br />

<p>
<img src="https://i.imgur.com/UjSwq26.png"/>
</p>
<p>
Next type udp.port==53 this port is for dns Domain Name System
</p>
<br />

<p>
<img src="https://i.imgur.com/sJ2oM87.png"/>
</p>
<p>
Next type tcp.port==3389 this port is for rdp Romote Desktop Protocol
</p>
<br />

<p>
<img src="https://i.imgur.com/RicUPcN.png"/>
</p>
<p>
Now go back to Microsoft Azure and copy the Public IP address or the Private IP address of VM2 
</p>
<br />

<p>
<img src="https://i.imgur.com/IN4TPGh.png"/>
</p>
<p>
Now go back to VM1 and type ssh labuser@ Public IP Address or Private IP Address. So this is using ssh to take into VM2 through VM1. ssh then the name of the VM which was labuser, then type the private or public IP address. Next type yes to allow the connection. Then type in your password the password wont show on the screen just have faith you are typing it correctly then press ENTER
</p>
<br />

<p>
<img src="https://i.imgur.com/r2DNs7z.png"/>
</p>
<p>
You will know it worked if you see a green name under labuser@VM2. Next type pwd (Print Working Directory) to show the directory 
</p>
<br />

<p>
<img src="https://i.imgur.com/tJiLGSm.png"/>
</p>
<p>
Now type id to show all the identification in VM2
</p>
<br />

<p>
<img src="https://i.imgur.com/FwN8lOP.png"/>
</p>
<p>
Now type ip to see all the list of ip commands 
</p>
<br />

<p>
<img src="https://i.imgur.com/EWzVHjo.png"/>
</p>
<p>
Now to create a txt file we can type touch hi.txt this will create a hi txt file 
</p>
<br />

<p>
<img src="https://i.imgur.com/l2Y6xt9.png"/>
</p>
<p>
Now to see the txt file we just created type ls -lasth
</p>
<br />

<p>
<img src="https://i.imgur.com/c2cygOJ.png"/>
</p>
<p>
Now we can also create multiple files at once by typing touch hi my name is. Anything after touch will be its own file created. Then type ls -lasth to see the files
</p>
<br />

<p>
<img src="https://i.imgur.com/hhTgZsr.png"/>
</p>
<p>
Now type uname -a this shows a string with all the os info running on it
</p>
<br />

<p>
<img src="https://i.imgur.com/zQHn3e8.png"/>
</p>
<p>
Now to exit out of VM2 type exit 
</p>
<br />

<p>
<img src="https://i.imgur.com/y2uOHcM.png"/>
</p>
<p>
Next out of VM2 in the command line type nslookup this shows the IP or the DNS
</p>
<br />

<p>
<img src="https://i.imgur.com/qbQTdnm.png"/>
</p>
<p>
Next type ipconfig in the command line this shows the current TCP/ IP also machine IP
</p>
<br />

<p>
<img src="https://i.imgur.com/AM124cK.png"/>
</p>
<p>
Now go back to Microsoft Azure and go to the Resource Groups we created. Click RG-LAB-02 and retype it in the delete section, then click the red delete button
</p>
<br />

<p>
<img src="https://i.imgur.com/ukE7wtT.png"/>
</p>
<p>
Now go to the NetworkWatcherRG and delete that one as well
</p>
<br />
