# Creating-Virtual-Machines/Secure Shell
<p></p>
The process of utilizing secure shell (SSH) using virtual machines created in Microsoft Azure.
<p></p>
<p></p>
<img src=https://i.imgur.com/Lt8FHMp.png
<p>
<p></p>
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop


<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Ubuntu 20.04 (Linux)
<h2>Configuration Objectives</h2>

- Create VM1 (Windows 10) via azure portal
- Create VM2 (Ubuntu)
- Test connection from VM1 to VM2
- Secure Shell into VM2
- Terminate connection 

<h2>Configuration Steps</h2>

<p>
<img src=https://i.imgur.com/Rub4QBm.png</p>
<p>
<p></p>
<img src=https://i.imgur.com/yfREsDA.png
<p> 
<p></p>
- Using a current Azure subscription, create a resource group. This can be accomplished by typing "Resource Group" in the Azure portal search bar and pressing "Create" on the resource groups page.
<p></p>
- Create a virtual machine running a Windows 10 operating system. Create a username and password which will be used to sign into the VM via remote desktop.
<p></p>
- All settings can be changed or left default as desired. Take a note of the network used, as VM2 must be assigned to the same virtual network. Press review and create, and create once validation has been passed. 
<p></p>
- Create a second virtual machine running an Ubuntu 20.04 operating system. Repeat the same process as earlier, with the exception being that VM2 must utilize VM1's virtual network. To see, the option for VM2's virtual network. The name for VM1 should be displayed, along with the IP address associated with it. This is the one to use.
<p></p>
- NOTE: VM1's virtual network should automatically be selected for VM2 as long as the same resource group is used for both VMs. If it does not shoow up, I find that canceling VM2 and remaking it will fix this issue.
<p></p>
</p>
<br />

</p>
<p>
<img src=https://i.imgur.com/YtdIRYj.png
</p>
<br />
- Once both VMs have been created, navigate to the virtual machines page via the Azure portal. Select VM1 (Windows 10).
<p>
- Right click and copy the public IP for VM1. This will be necessary to access the VM in remote desktop.
<p>
- Go to your PC's remote desktop program and select add new PC. Enter your VM's public IP. Select it and input the username and password that was created for VM1. Complete initial login steps.
<p>
<p>
<img src=https://i.imgur.com/ndoGVWT.png<p>
</p>
<p>
- Once logged into VM1, navigate to Windows Power Shell via the search bar in the start menu. 
<p></p>
- From powershell, the connection between VMs 1 and 2 can be tested by inputing the command "ping" followed by VM2's private IP address. To find the private IP needed, navigate to VM2's page in the Azure portal from the default browser outside of the VM. Scroll down and the Private IP will be shown.
<p></p>
- In my case the ping command was "ping 10.0.0.5" as shown in the image above. The window should display similar data to the image shown.
<p></p>
</p>
- Once a connection has been verified, input "ssh (VM2username)@(VM2Private IP). Mine was "ssh mikle2@10.0.0.5". A message will display that reads "the authenticity of host can't be established" and it will ask if you would like to continue. Type "yes" in the command line. It will then ask for the login password for VM2 that was created earlier. If successful, VM2's username will be displayed in green. From here, Linux commands will be accepted to accomplish tasks. Secure shell is complete. To log off of VM2 from powershell, simply input the command "exit".
<p></p>
<img src=https://i.imgur.com/0vdDpIo.png
