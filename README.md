<h1>Microsoft SQL Logs Forwarding via WinCollect Agent</h1>

<h2>Description</h2>
This project provides a solution to forward Microsoft SQL Server logs via IBM QRadar's WinCollect Agent for monitoring and security analysis. The provided SQL script and WinCollect configuration allow seamless forwarding of SQL logs to your SIEM solution.
<br />


<h2>Requirements</h2>

- <b>Microsoft SQL Server 2016 or newer</b> 
- <b>IBM QRadar</b>
- <b>WinCollect Installer</b>
- <b>WinCollect Standalone patch Installer</b>
- <b>Admin access to SQL Server and Windows environment</b>
- <b>.NET Framework 3.5 Features </b>

<h2>Step-by-step instructions:</h2>

<p align="Left">
<h3>Microsoft SQL Server preparation for communication with QRadar<br/></h3>
Creating a Microsoft SQL Server auditing object
<br/>1.	 Log in to your Microsoft SQL Server Management Studio
<br/>2.	From the navigation menu, select Security > Audits
<br/>3.	Right-click Audits and select New Audit.
<img src="https://i.imgur.com/hwQTAfO.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br/>4.	In the Audit name field, type a name for the new audit file
<br/>5.	From the Audit destination list, select File
<br/>6.	From the File path field, type the directory path for your Microsoft SQL Server audit file
<img src="https://i.imgur.com/jH0czYJ.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />7.	Click OK.
<br />8.	Right-click your audit object and select Enable Audit
<img src="https://i.imgur.com/CZjkpeP.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />

<h3>Creating a Microsoft SQL Server audit specification<br/></h3>
Create an audit specification to define the level of auditing events that are written to an audit file. You can create an audit specification at the server level or at the database level. Depending on your requirements, you might require both a server and database audit specification.
<br />
<br />1.	From the Microsoft SQL Server Management Studio navigation menu, select one of the following options: 
  Security > Server Audit Specifications
<br />2.	Right-click Server Audit Specifications, and then select New Server Audit Specifications
<img src="https://i.imgur.com/MDnDxqB.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />3.	In the Name field, type a name for the new audit file
<br />4.	From the Audit list, select the audit object that you created
<img src="https://i.imgur.com/xj0DQ6I.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />5.	In the Actions pane, add actions and objects to the server audit
<img src="https://i.imgur.com/aVwLl3n.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
Note: Choose audit action type base on your requirements. The chosen objects on the screenshot are just examples
<br />6.	Click Ok
<br />7.	Right-click your server audit specification and click Enable Server Audit Specication.

<h3>Creating a Microsoft SQL Server database view</h3>
1.	From the Microsoft SQL Server Management Studio toolbar, click New Query
<br />2.	Type the following Transact-SQL statement:
<img src="https://i.imgur.com/HP9DE4K.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
3.	From the Standard toolbar, click Execute



<br />
<h3>Install QRadar Wincollect Agent</h3>
Note:Before you begin make sure .NET Framework 3.5 Features was installed
<br />1. Launch the installer of wincollect agent
<br />2. Click next
<br /><img src="https://i.imgur.com/7tDEgch.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />3.	Accept the license agreement and click Next
<br /><img src="https://i.imgur.com/1shSHx3.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />4.	Click **Next**
<br /><img src="https://i.imgur.com/b4P7Zxm.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />5.	Click **Next**
<br /><img src="https://i.imgur.com/XHeaVjb.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />6.	Select **Stand Alone** and click **Next**.
<br /><img src="https://i.imgur.com/a15NP4L.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />7.	Click **Next**
<br /><img src="https://i.imgur.com/80F53pO.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />8.	Click **Next**
<br /><img src="https://i.imgur.com/HELAJCM.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />9.	Click **Next**
<br /><img src="https://i.imgur.com/VZv3tsa.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />10.	Click **Install**
<br /><img src="https://i.imgur.com/DL0uPNq.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />11.	Click **Finish**
<br /><img src="https://i.imgur.com/QMNkjyU.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />


<br />
<h3>Install Wincollect standalone patch</h3>
<br />1. Launch the installer of wincollect standalone patch
<br />2. Click **Next**
<br /><img src="https://i.imgur.com/6Lvbjhb.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />
<br />3.	Accept the license agreement and click **Next**
<br /><img src="https://i.imgur.com/oB4ZlOr.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />4. Click Next
<br /><img src="https://i.imgur.com/iW0o9a6.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />5. Click Next
<br /><img src="https://i.imgur.com/rOuWz6i.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />6. Click Install
<br /><img src="https://i.imgur.com/4NiWmdH.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />7. Click Finish
<br /><img src="https://i.imgur.com/f8hTviZ.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />

<h3>Configure Wincollect Agent to forward the Logs</h3>
1. Launch the Wincollect Configuration Console
<br />2.	Click drop-down arrow under Destinations and right-click to Syslog TCP.
<br />3.	Click Add New Destination
<br /><img src="https://i.imgur.com/x4ikCxa.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />4.	Enter a Destination Name and click Ok
<br /><img src="https://i.imgur.com/OY1KtQV.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />5.	Go to created destination name and enter the Hostname/IP.
<br /><img src="https://i.imgur.com/Nyx9l3O.png" height="60%" width="60%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />6.	Click Deploy Changes, wait for the message “Changes have been successfully deployed” and click Ok.
<br /><img src="https://i.imgur.com/jgTnDJc.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />7.	Click drop-down arrow under Devices and right-click to Microsoft SQL Server
<br />8.	Click Add New Device
<br /><img src="https://i.imgur.com/MFlKLcZ.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />9.	Enter a Device Name and click Ok.
<br /><img src="https://i.imgur.com/4b00BpT.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />10. Go the created Device Name under Microsoft SQL Server. 
<br />11.	Enter the Device Address (Device IP Address).
<br />12.	Enter the right path for your root directory.
<br /><img src="https://i.imgur.com/HVepHDa.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
Note:Please check the website below to find the appropriate path for your Operating System.
<br />https://www.ibm.com/docs/en/qradar-common?topic=agents-microsoft-sql-log-source

<br />
<br />13.	Use Notification-based (local) as your File Monitor Type
<br /><img src="https://i.imgur.com/WNDW4hR.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />14.	Click the Add for the destination and choose the right device. 
<br /><img src="https://i.imgur.com/SkrKYmL.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>
<br />15.	Click Deploy Changes, wait for the message “Changes have been successfully deployed” and click Ok.
<br /><img src="https://i.imgur.com/CrcB7cM.png" height="40%" width="40%" alt="Microsoft SQL Logs Forwarding via WinCollect Agent"/>







<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
