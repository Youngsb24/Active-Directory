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
<br>7. Create new VM for the client server, using Windows 10 and different naming conventions</br>
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
<br><img src="https://imgur.com/1UKoBYX.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/dgg45bw.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/hixRtzA.png"  height="70%" width="70%" alt="Disk Sanitization Steps"/>
</br>
<br>Verify if the Active Directory tool has been installed properly. Click the dropped down for "Windows Administrative Tools" to confirm</br>
<br><img src="https://imgur.com/JOPPLkF.png"  height="20%" width="30%" alt="Disk Sanitization Steps"/>
</br>
<br>Select "Active Directory Users and Computers" </br>
<br><img src="https://imgur.com/D80IktI.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>


<h2>Connecting PC to a Domain</h2>
Connecting a PC to an Active Directory (AD) domain allows centralized management, security, and authentication. It enables administrators to enforce policies, manage user access, and streamline IT operations. This setup enhances security and simplifies user and device management within an organization.

<h3>Steps for Domain Controller Server</h3>
<br>1. Search for the cmd (command line) --> run "ipconfig /all" to gather the IP4 information and defualt gateway information</br>
<br>2. Search for the Control Plane --> click "View Network Status and Task" --> click "change dapter" --> right click "ethernet" go to "properties" (insert your info from the cmd line)</br>
<br>Configure the server to have a static IP address, reason is becuase we aren't using router or switch for the DHCP. Also allows our client Server to easily connect to the Domain controller.</br>
<br><img src="https://imgur.com/XdkRf3F.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>
<img src="https://imgur.com/7kuTx41.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br></br>
<h3>Steps for Client Server</h3>
<br>1. Search for "Add or remove programs"</br>
<br>2. select "Optional features" </br>
<br>3. Select "Add features" </br>
<br>4. Select " RSAT AD certificate services tools" "RSAT DHCP server tools" "RSAT AD DS lightweight directory" "RSAT DNS server tools" "RSAT group management tools" "RSAT Remote Desktop" "RSAT server manager" </br>
<br>5. install </br>
<br><img src="https://imgur.com/jt53wKp.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/Pu2xl2n.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/jkOeMRu.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/4ojrQ9X.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>
<h3>Steps</h3>
<br>Lastly configure Client server IP address to be static, and conncecting the client PC to the domain controller</br>
<br>1. Search for the cmd (command line) --> run "ipconfig /all" to gather the IP4 information and defualt gateway information</br>
<br>2. Search for the Control Plane --> click "View Network Status and Task" --> click "change dapter" --> right click "ethernet" go to "properties" (insert your info from the cmd line)</br>
<br>3. Add the DC (domain controller) IP address in the "preferred DNS Server" with the gateway IP address to follow.</br>
<br><img src=https://imgur.com/CZ3TUrq.png"  height="50%" width="50%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/kBIhbyU.png"  height="30%" width="30%" alt="Disk Sanitization Steps"/>
</br>
<br>4. Go to "file explorer" --> right click "This PC" --> click "Properties" --> click "Advance System Settings" --> click "Computer Name" --> click "change" --> click "Member of" add the Domain name you created. follow the rest of the prompt. Lastly go back to Domain Controller and Open " AD users and Computers" check the computer OU (Organizational Unit) to confirm the PC has been successfully connected (last image)</br>
<br><img src="https://imgur.com/twiCLX7.png"  height="50%" width="50%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/K5Nc8iB.png"  height="50%" width="50%" alt="Disk Sanitization Steps"/>
</br>
<br><img src="https://imgur.com/5PZMkgB.png"  height="50%" width="50%" alt="Disk Sanitization Steps"/>
</br>




