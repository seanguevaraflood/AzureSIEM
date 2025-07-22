<h1>SIEM In Microsoft Azure Project</h1>

<p>Created a Honeypot using a virtual machine and virtual network. Released it to the public internet and observed the attacks through logs and queried the data with KQL. Created an Attack Map and observed the enriched logs.</p>

<p>This is a visual example of what we are going to execute.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/SIEM%20Project%20Diagram%201.png
)

<p>We then created a resource group for this Homelab.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Resource%20Group%201.png
)

<p>We then created a virtual network.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Virtual%20Network%201%20.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Virtual%20Network%202.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Virtual%20Network%203.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Virtual%20Network%204.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Virtual%20Network%205.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Resource%20Group%202.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Resource%20Group%203.png
)

<p>We then created the honeypot virtual machine to attract hackers.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Virtual%20Machine%201.png
)

<p>We now have a virtual machine honeypot.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Resource%20List.png
)

<p>Now we are going to expose this honeypot to the public internet by adding an inbound rule to allow all traffic on any protocol.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Inbound%20Security%20Rules.png
)

<p>We then RDP into the virtual machine to turn off Windows Firewall to help allow the virtual machine to be attacked.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Windows%20Defender%201.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Windows%20Defender%202.png
)

<p>Now that we have turned off Windows Defender, the virtual machine is a lot more vulnerable to attack.</p>

<p>Let’s ping the VM to make sure we are connected to the public internet.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Ping%20to%20VM.png
)

<p>Now let’s get into logging and create a repository to forward logs into it. We will forward the logs from Event Viewer into a log repository in Microsoft Azure. Let's create a Log Analytics Workstation.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Log%20Analytics%201.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Log%20Analytics%20Workspace.png
)

<p>Now that we have created the Log Analytics Workspace, let’s create the SIEM using Microsoft Sentinel.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Microsoft%20Sentinel%20Search.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Create%20Microsoft%20Sentinel%201.png
)

<p>Great, with Microsoft Sentinel activated, let’s link the Log Analytics Workspace with Microsoft Sentinel.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Microsoft%20Sentinel%20Directory.png
)

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Microsoft%20Sentinel%20To%20Workspace%20.png
)

<p>Let's download the Microsoft Security Event Connector so we can forward the Security Event Viewer on the Virtual Machine to Microsoft Azure.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Windows%20Security%20Events.png
)

<p>Ok let’s wait a bit and see what logs have come in.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Windows%20Secuirty%20Logs.png
)

<p>Let’s analyze these logs using KQL to filter a specific account location attempt.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/KQL%20Logs%201.png
)

<p>Let’s query failed log-in attempts with KQL by using <code>EventID == 4625</code>.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/KQL%20Logs%202.png
)

<p>We can query different EventIDs and timeframes to see a series of logs as per our specifications.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/KQL%20Logs%202.png
)

<p>Let’s make a Watchlist to plot the geolocations of those who are trying to log into the Virtual Machine by using a GeoIP summarized CSV file.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Watchlist%20Wizard%20GeoIP.png
)

<p>Now we can query the CSV file to log the geolocation of those trying to get into the Virtual Machine.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/CSV%20Geolocation.png
)

<p>Let’s fill this out—how we can enrich this query to specify specific IP addresses and Event ID. Let’s get even more information about the attackers.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Geolocation%20KQL.png
)

<p>Finally, let’s get these attackers mapped out based on their geolocation by using a Microsoft Sentinel Workbook.</p>


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Attack%20Map%201.png
)


![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/Attack%20Map%202.png
)

<p>This concludes our Homelab. We created a resource group which we assigned into a subnet. We then created a Virtual Machine and disabled the Virtual Machine’s firewall. We then used a Log Analytics Workspace to forward all security events into the Log Analytics Workspace with Azure Monitor Agent. We then created a Microsoft Sentinel instance and connected that Log Analytics Workspace. Inside Sentinel, we uploaded a watchlist with the geolocation based on IP. We then used KQL to specify all failed login attempts by specifying the EventID. We then used the watchlist based on the logs to map out where the attackers are coming from.</p>

![image alt](https://github.com/seanguevaraflood/AzureSIEM/blob/0f73857ae2c03de16dc3518208e74660010a0f1d/images/SIEM%20Project%20Diagram%202.png
)
