
#<h1>Basic Home SOC Lab in Azure</h1>

<h2>Description</h2>
This project involves creating a basic home Security Operations Center (SOC) in the cloud, using a free Azure subscription. The goal is to deploy a honeypot virtual machine intentionally exposed to the public internet to observe real-time cyber-attacks. By forwarding security logs from the honeypot to a centralized repository and integrating with a Security Information and Event Management (SIEM) system, the project demonstrates how attackers interact with exposed systems and how security teams can monitor and analyze these threats using KQL.
<br />



<h2>Tools and Technologies Used</h2>

<b>Microsoft Azure Cloud Platform:</b>  
<b>Used to create and manage the virtual infrastructure including the virtual machine, virtual network, and security groups.</b>

<b>Azure Free Subscription:</b>  
<b>Used for cost-effective access to cloud services with free credits.</b>

<b>Virtual Machine (Windows 10 Image):</b>  
<b>Acts as the honeypot, deliberately opened to public internet traffic to attract real attacks.</b>

<b>Virtual Network and Subnet:</b>  
<b>Provides network segmentation and connectivity within Azure, similar to a home router but in the cloud.</b>

<b>Network Security Group (NSG):</b>  
<b>Functions as a cloud firewall controlling inbound and outbound traffic, configured to allow all inbound traffic to expose the VM.</b>

<b>Windows Firewall (inside VM):</b>  
<b>Disabled to increase the VM’s vulnerability and attract more attacks from the internet.</b>

<b>Azure Log Analytics Workspace:</b>  
<b>A centralized log repository where security logs from the VM are forwarded for aggregation and analysis.</b>

<b>Azure Sentinel:</b>  
<b>Microsoft’s cloud-native Security Information and Event Management (SIEM) system used to aggregate, analyze, and visualize security events collected from Azure resources.</b>

<b>Azure Monitor Agent:</b>  
<b>Installed as an extension on the VM, responsible for forwarding security event logs to the Log Analytics workspace.</b>

<b>Kusto Query Language (KQL):</b>  
<b>The query language used to filter, analyze, and visualize event logs inside Log Analytics and Sentinel.</b>

<b>Watch List in Sentinel:</b>  
<b>A large spreadsheet containing IP-to-geolocation mappings uploaded into Sentinel to enrich logs with geographic information about attacker IP addresses.</b>



<h2>Project Activities performed & Images of its walk-through:</h2>

- <b>Created a Free Azure Subscription:</b> Signed up using a personal email and credit card.

- <b>Logged into Azure Portal:</b> Accessed and managed resources via portal.azure.com.

- <b>Created a Resource Group:</b> Organized cloud resources in a logical container to manage the project infrastructure.

- <b>Created a Virtual Network:</b> Set up a cloud network environment similar to a home router, hosting the virtual machine and subnet.

- <b>Deployed a Virtual Machine (Honeypot):</b>  
  - Used Windows 10 image for the VM.<br>  
  - Selected a VM size balancing cost and performance.<br>  
  - Assigned the VM to the virtual network.<br>  
  - Named the VM inconspicuously to avoid revealing its honeypot nature.

- <b>Configured Network Security Group (NSG):</b>  
  - Deleted default inbound rules.<br>  
  - Added a rule allowing all inbound traffic to expose the VM publicly and attract attackers.

- <b>Disabled Windows Firewall on VM:</b> Logged in via Remote Desktop and turned off the internal firewall to maximize vulnerability.

- <b>Accessed the Virtual Machine:</b> Connected using Remote Desktop Protocol (RDP) with the VM’s public IP; Mac users installed Microsoft Remote Desktop app.

- <b>Generated Failed Login Attempts:</b> Performed invalid login attempts to produce security audit failure logs.

- <b>Viewed Local Logs:</b> Used Windows Event Viewer to examine security logs, focusing on event ID 4625 (failed logons).

- <b>Created a Log Analytics Workspace:</b> Established a central repository in Azure to collect forwarded logs from the VM.

- <b>Set Up Azure Sentinel:</b> Connected Sentinel (Azure’s SIEM) to the Log Analytics workspace for advanced querying and visualization of security events.

- <b>Installed Azure Monitor Agent on VM:</b> Deployed the agent extension to forward VM security logs to the Log Analytics workspace.

- <b>Performed Log Analysis and Visualization:</b>  
  - Used Kusto Query Language (KQL) to filter failed login attempts.<br>  
  - Uploaded a watch list spreadsheet mapping IP ranges to geographic locations.<br>  
  - Created a Sentinel workbook to visualize attacker locations on a dynamic map.
 

  <p align="center">
Creating a Virtual Network: <br/>
<img src="https://imgur.com/a/oyoDJ45" height="80%" width="80%" alt="Virtual Network"/>
<br />
<br />




 
