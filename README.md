<h1>Microsoft Azure: Azure Sentinel (SIEM & SOAR) Project</h1>
<img src="MicrosoftAzureProject copy.jpeg" height="80%" width="80%" alt="diagram"/>
<h2>Description</h2>
In this lab, I implemented Azure Sentinel as a SIEM & SOAR solution, integrated with a live honeypot VM. This allowed for monitoring of global RDP Brute Force attacks. I employed a custom PowerShell script to extract attacker geolocation data and plotted it on the Azure Sentinel Map for enhanced visual insights.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Azure</b>
- <b>Remote Desktop Connection</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Create a VM that is discoverable to all traffic: <br/>
<img src="VM.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Change security group inbound rules to make the VM very discoverable:  <br/>
<img src="https://imgur.com/cj8s8vV.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Create a Log Analytics Workspace to log the inbound traffic to the VM: <br/>
<img src="Log analytics.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Connect the Log Analytics Workspace to the VM:  <br/>
<img src="68747470733a2f2f696d6775722e636f6d2f637663326157672e706e67.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Run the VM and connect to it via Remote Desktop Connection:  <br/>
<img src="Connecting to VM.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Turn off Windows Firewall within the RDC VM:  <br/>
<img src="RDP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Test ping from personal computer to VM:  <br/>
<img src="VM connectivity .png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Get an API Key if you dont already have one (ipgeolocation.io):  <br/>
<img src="API key.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run custom script with your API Key on Windows PowerShell ISE to get Geo Data from attackers :  <br/>
<img src="custom script.png" height="80%" width="80%" alt="Cyber Attack Event Management"/>
<br />
<br />
Save script as log file and it'll create a txt file with all the failed login attempts Geo Data :  <br/>
<img src="log file.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a custom log thats linked to the txt file with all the failed login attempts Geo Data:  <br/>
<img src="Custom log Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Using the SQL Query in logs, observe the data security audit logs:  <br/>
<img src="Security event logs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Using the SQL Query in logs, observe the data from the custom log:  <br/>
<img src="query custom logs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Extract the fields from raw custom logs:  <br/>
<img src="raw custom logs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Check custom fields to confirm before testing:  <br/>
<img src="custom fields.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Test new custom fields which were extracted to see if they collect the data:  <br/>
<img src="https://imgur.com/rjCRuf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create Microsoft Sentinel:  <br/>
<img src="MS sentinel.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Within Microsoft Sentinel, setup a map in workbooks using longitude and latitude:  <br/>
<img src="workbook map.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use the following SQL Query to isolate which data to be shown, and the following map settings to display on world map:  <br/>
<img src="SQL Query for map.png" height="80%" width="80%" alt="workbook setup"/>
<img src="https://imgur.com/TAeiN3Q.png" height="80%" width="80%" alt="workbook setup"/>
<img src="https://imgur.com/F7WlgYG.png" height="80%" width="80%" alt="workbook setup"/>
<br />
<br />
After a couple hours the VM will be found by the cyber attackers of the world. Now you can observe Geo Data from where your VM is being breached!:  <br/>
<img src="breached image.png" height="80%" width="80%" alt="Cyber Attack Event Management"/>
<br />
<br />
This Concludes This Microsoft Azure SIEM Project!
NOTE: You can toggle map setting to display other custom fields  <br/>
<br />
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
