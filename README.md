# Active-Directory
This lab focuses on setting up Active Directory by configuring Server Manager and deploying a Domain Controller. It includes steps to create and manage users, groups, and policies. Additionally, it covers connecting a Windows PC to the domain for centralized management.

<h2>ENVIROMENTS AND TECHNOLOGY USED</h2>
<br>- Microsoft Azure (Virtual Machine )</br><br>- Microsoft Remote Desktop </br><br>- Active Directory Domain Services </br>
<h2>Operating System Used</h2>
<br>- Windows Server 2022 (Domain Controller)</br><br>- Windows 10 </br>

<h2>Virtual Machine Set up</h2>
<br>1. Create Azure account (free subscription) </br>
<br>2. Find and click Virtual machine in search bar </br>
<br>3. create new VM </br> 
<br>4. Name Your VM whatever you like. Select the region that best fits your geolocation. Create Username and Password that you won't forget. Name Resource group (AD-windows-Vm)  select (windows 22) </br>
<br>5. Name Virtual network (VNet) ( AD-Vnet) </br>
<br>6. click "review + create" </br> 
<br><img src="https://imgur.com/vpOPVca.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/VE0HgIU.png height="40%" width="40%" alt="Disk Sanitization Steps"/>
</br>
<h2>Microsoft Remote Desktop</h2>
<br>Depending on what operating system you are using, Downloading Micrososft Remote Desktop app is for Mac users to be able to remote into windows Virtual machine</br>
<br>1. Go to the app store and search for " Microsoft Remote Desktop</br>
<br>2. Add the Windows VM public IP address </br>
<br><img src="https://imgur.com/xqrdWZ2.png"  height="40%" width="40%" alt="Disk Sanitization Steps"/>
</br>

<h2>Configuring Server Manager</h2>
<br>Server Manager is going to open by default, as you log in</br>
<br>1. Click on "tool", then select "Add roles and Features</br>
<br>2. Installation type select "Role-based or feature-based installation. then next</br>
<br>3. Server Roles , select " AD Services, Remote Access, DNS server" , then next</br>
<br>4. Features ,ensure "group Policy management" is selected. then next</br>
<br>5. Keep clicking Next till you are able to just press install</br>
<br>6. Once everything is installed we should click on "Promote this server to a domain controller"</br>
<br>7. then click "Add a new forest", my domain name is "Youngsb24.local" . its imparitive to add ".com" or ".local" at the end</b>
<br>. After you install after passing the prerequisites. You will forced to reboot the server so it can install Active directory tool. Then re log in.</br>
<br><img src="https://imgur.com/BDKWKz9.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/SAdAVOG.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</br>
<br>Verify if the Active Directory tool has been installed properly. Click the dropped down for "Windows Administrative Tools" to confirm</br>
<br><img src="https://imgur.com/FbKferg.png"  height="50%" width="50%" alt="Disk Sanitization Steps"/>
</br>
