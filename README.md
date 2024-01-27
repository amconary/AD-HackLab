<h1>Active Directory Home Lab Setup</h1>

 <h2>Description</h2>
Project consists of setting up a purposefully vunerable Windows Active Directory Home Lab environment that can be used for penetration testing techniques.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Active Directory</b> 
- <b>Group Policy</b>

<h2>Environments Used </h2>

- <b>Windows server 2022 and Windows 10 Enterprise eval editions</b>

<h2>Project walk-through:</h2>

<p align="center">
Lab Setup
<br />
<br />
Download all eval ISO files needed from Microsoft for server 2022 and Win 10 Enterprise.
Setup the virtual server in your VM manager of choice.
Add roles and features - choose Active Directory Domain Services.
Start a new forest to create your domain name ( example: myadlab.local).
Click ‘Next’ until the pre-requisites, then install. Once finished your new server will reboot and be joined to the domain you created: <br/>
<img src="https://i.imgur.com/8qHwltg.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
Next add another feature and role - AD Certificate Services (needed for testing attacks).
After the install is complete configure the CA setup - leave all settings default to completion
<br />
<br />
Go through the VM setup process again and build out 2 win 10 VM’s with the domain join option:  <br/>
<img src="https://i.imgur.com/0SdCMFj.png" height="80%" width="80%" alt="Hack Lab"/>
<br />
<br />
Next connect to the DC Server, login and open Active Directory Users and Computers.
Create some domain and user accounts that we can use for testing:  <br/>
<img src="https://i.imgur.com/P3G3kBg.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
<br />
Next open Group Policy Management and create a new policy under our domain.
Create a policy to disable Windows Defender under Computer > Policies > Admin Templates > Windows components > Microsoft Defender and in the right pane click the option for ‘Turn off Microsoft Defender’ and set it to Enabled. We need Microsoft Defender disabled in order to test some hacking techniques:  <br/>
<img src="https://i.imgur.com/CZpwazN.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
<br />
Log into your 2 user win 10 VMs and join them to your domain. You should now see them added under AD Users and Computers in the Computers OU:  <br/>
<img src="https://i.imgur.com/x0A4oOa.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
<br />
On the 2 win 10 VMs open local users and groups, enable the local administrator account, and add then we are going to add domain user1 to the local admins group. Repeat the steps on the 2nd VM with domain user2 and user1 both added to the local admins group:  <br/>
<img src="https://i.imgur.com/JE2G6bk.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
<br />
On the DC Server open server manager, click on File Services and we are going to create a share.
Click Shares, then tasks in the center pane, select SMB Quick and leave all options default. Name the folder whatever you would like:  <br/>
<img src="https://i.imgur.com/u7vykVC.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
<br />
On your win 10 machine 2 add the network shared folder you created on the DC:  <br/>
<img src="https://i.imgur.com/PEh1yyc.png" height="60%" width="60%" alt="Hack Lab"/>
<br />
<br />
Lab Setup is now Complete!  <br/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
