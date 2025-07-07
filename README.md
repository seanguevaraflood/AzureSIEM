<h1>Honeypot Homelab</h1>

<p>Created a Honeypot using a virtual machine and virtual network. Released it to the public internet and observed the attacks through logs and queried the data with KQL. Created an Attack Map and observed the enriched logs.</p>

<p>This is a visual example of what we are going to execute.</p>

<p>We then created a resource group for this Homelab.</p>

<p>We then created a virtual network.</p>

<p>We then created the honeypot virtual machine to attract hackers.</p>

<p>We now have a virtual machine honeypot.</p>

<p>Now we are going to expose this honeypot to the public internet by adding an inbound rule to allow all traffic on any protocol.</p>

<p>We then RDP into the virtual machine to turn off Windows Firewall to help allow the virtual machine to be attacked.</p>

<p>Now that we have turned off Windows Defender, the virtual machine is a lot more vulnerable to attack.</p>

<p>Let’s ping the VM to make sure we are connected to the public internet.</p>

<p>Now let’s get into logging and create a repository to forward logs into it. We will forward the logs from Event Viewer into a log repository in Microsoft Azure. Let's create a Log Analytics Workstation.</p>

<p>Now that we have created the Log Analytics Workspace, let’s create the SIEM using Microsoft Sentinel.</p>

<p>Great, with Microsoft Sentinel activated, let’s link the Log Analytics Workspace with Microsoft Sentinel.</p>

<p>Let's download the Microsoft Security Event Connector so we can forward the Security Event Viewer on the Virtual Machine to Microsoft Azure.</p>

<p>Ok let’s wait a bit and see what logs have come in.</p>

<p>Let’s analyze these logs using KQL to filter a specific account location attempt.</p>

<p>Let’s query failed log-in attempts with KQL by using <code>EventID == 4625</code>.</p>

<p>We can query different EventIDs and timeframes to see a series of logs as per our specifications.</p>

<p>Let’s make a Watchlist to plot the geolocations of those who are trying to log into the Virtual Machine by using a GeoIP summarized CSV file.</p>

<p>Now we can query the CSV file to log the geolocation of those trying to get into the Virtual Machine.</p>

<p>Let’s fill this out—how we can enrich this query to specify specific IP addresses and Event ID. Let’s get even more information about the attackers.</p>

<p>Finally, let’s get these attackers mapped out based on their geolocation by using a Microsoft Sentinel Workbook.</p>

<p>This concludes our Homelab. We created a resource group which we assigned into a subnet. We then created a Virtual Machine and disabled the Virtual Machine’s firewall. We then used a Log Analytics Workspace to forward all security events into the Log Analytics Workspace with Azure Monitor Agent. We then created a Microsoft Sentinel instance and connected that Log Analytics Workspace. Inside Sentinel, we uploaded a watchlist with the geolocation based on IP. We then used KQL to specify all failed login attempts by specifying the EventID. We then used the watchlist based on the logs to map out where the attackers are coming from.</p>
