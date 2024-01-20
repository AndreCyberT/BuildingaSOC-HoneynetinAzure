# BuildingaSOC-HoneynetinAzure

<h2>Description</h2>
In this project,I build a mini HoenyNet in Azure and ingest log sources from a multitude of resources into a Log Analytics workspace,which is then usec by Microsfot sentinel to build attack maps,trigger alerts,and create incidents.I measured some security metrics in the insecure enviroment for 24 hours, apply some security controls to harden the enviroment,measured metrics for another 24 hours,then show the results below.

<h2>Languages and Utilities</h2>

- <b>PowerShell (Automation and Configuration Management)</b>
- <b>Azure Network Security Group (NSG) </b>
- <b>Microsoft Defender (Cloud to protect Cloud Resources)</b>
- <b>Microsoft sentinel (Security Information and Event Management SIEM)</b>
- <b>Azure Key Vault (Secure Secrets Management)</b>
- <b>Azure Storage Account (Data Storage) </b>
- <b>Window Remote Desktop (Remote Access) </b>
- <b>Command Line Interface (System Management) </b>
- <b>NIST SP 800-53 Revision 4 (Security Controls) </b>
- <b>NIST SP 800-53 Revision 2 (Incident Handling Guidance) </b>

 <h2>Enviroments Used </h2>


- <b>2x Windows 10 Pro</b> (21H2)
- <b>Linux Server</b>
- <b>Log Analytics Workspace (Kusto Query Lanuage KQL Queries)</b>
- <b>Azure Virtual Network (VNet)</b>

 <h2>Course of Action</h2>
  
-Establishing the honeynet: To start, I created the vulnerable environment with the Virtual Machines. This was done by disabling the firewall inside of the VM as well as allowing all ports and traffic to be received by the Network Security Group (NSG).

-Tracking and examination: The Azure infrastructure was meticulously configured to seamlessly ingest log sources from a multitude of resources into a dedicated log analytics workspace. Leveraging the advanced capabilities of Microsoft Sentinel, sophisticated attack maps were meticulously constructed, meticulously triggering highly precise alerts and meticulously generating comprehensive incidents, all meticulously derived from the meticulously collected and meticulously analyzed data.

-Tracking and evaluating security metrics: I monitored the unsecured environment for a full day, noting important security measurements during that time. This served as a starting point for comparison once I applied security improvements.

-Addressing and resolving security incidents: Following the resolution of incidents and identification of vulnerabilities, I proceeded to fortify the environment by implementing security best practices and incorporating Azure-specific recommendations.

-Analysis after implementing remediation measures: An additional 24-hour period was dedicated to the meticulous re-observation of the environment, facilitating a comprehensive evaluation of the security metrics. The resulting data was then meticulously juxtaposed with the initial baseline, enabling a rigorous comparative analysis.

<h2>Metrics that will be displayed</h2>

- <b>SecurityEvent (Windows Event Logs)</b>
- <b>Syslog (Linux Event Logs)</b>
- <b>SecurityAlert (Log Analytics Alerts Triggered)</b>
- <b>SecurityIncident (Incidents created by Sentinel)</b>
- <b>AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)</b>

<h2> Design Before Hardening/Security Controls </h2>
 
 In the "BEFORE" phase, it was observed that all resources were initially provisioned with direct internet exposure. The Virtual Machines were configured with open Network Security Groups and permissive built-in firewalls, while other resources were deployed with publicly accessible endpoints, thereby rendering the usage of Private Endpoints unnecessary: <br/>
 <img width="767" alt="BEFORE measurement phase, it was observed that all resources were initially provisioned with direct internet exposure" src="https://i.imgur.com/jOEQdTU.gif">

 <h2> Design After Hardening/Security Controls </h2>

 In the "AFTER" stage, the Network Security Groups underwent fortification measures whereby all traffic, with the exception of my administrative workstation, was comprehensively blocked. Additionally, other resources were fortified by leveraging their built-in firewalls alongside the implementation of Private Endpoint functionality: <br/>
  <img width="768" alt="BEFORE measurement phase, it was observed that all resources were initially provisioned with direct internet exposure" src="https://i.imgur.com/tRm4lyo.png">


<h2>Program walk-through:</h2>

<p align="center">
The visual below provides an overview of the assault endeavors targeted at a publicly accessible Microsoft SQL server throughout a span of 24 hours. The plotted data points on the map delineate the precise origins of these attacks or attempted logins.: <br/>
<img width="766" alt="Installing Domain" src="https://i.imgur.com/Uk94HeI.png">

<p align="center">
The visual attack map clearly illustrates numerous syslog authentication failures faced by the Linux server I set up. It highlights unauthorized attempts to gain access from external sources outside the local network. This strongly emphasizes the importance of reinforcing Linux servers with strong authentication protocols and carefully monitoring system logs to identify and prevent potential intrusions. <br/>
<img width="775" alt="creating users for power shell" src="https://i.imgur.com/CIZvLkQ.png">

<p align="center">
The displayed attack map captures a variety of failures in RDP (Remote Desktop Protocol) and SMB (Server Message Block), vividly showcasing the persistent efforts of potential attackers to exploit these particular protocols. The visual representation emphasizes the crucial need to strengthen remote access and file-sharing services as a way to protect against unauthorized entry and mitigate potential cyber threats. <br/>
<img width="774" alt="Running users" src="https://i.imgur.com/0xyd96w.png">

<p align="center">
The depicted attack map compellingly exhibits the consequences arising from the decision to leave the Network Security Group (NSG) unrestricted, allowing unrestricted entry of malicious network traffic. This visualization strongly underscores the importance of implementing robust security protocols, including the enforcement of strict NSG rules, to prevent unauthorized access and mitigate the inherent risks associated with potential threats. <br/>
<img width="774" alt="Running users" src="https://i.imgur.com/gyC1HTU.png">

<h2> Benchmarks Before Hardening / Security Controls </h2>

The following table shows the metrics we measured in our insecure environment for 24 hours:
- <b>Start Time: 2024-11-12T16:16:40</b>
- <b>Stop Time: 2024-11-13T16:16:40</b>
<img width="361" alt="Metrics" src="https://github.com/AndreCyberT/BuildingaSOC-HoneynetinAzure/assets/143320920/0c225cf8-5e17-448d-ab12-408fbef528a9">

<h2> Attack Maps After Hardening / Security Controls </h2>

Note: All map queries actually returned no results due to no instances of malicious activity for the 24-hour period after hardening.

<h2> Metrics After Hardening / Security Controls </h2>

- <b>Start Time: 2024-11-13T18:20:40</b>
- <b>Stop Time: 2024-11-14T18:20:40</b>
<img width="357" alt="Metric 2" src="https://github.com/AndreCyberT/BuildingaSOC-HoneynetinAzure/assets/143320920/8148ef78-49d3-4708-ab1d-4fc06795654c">

<h2> Change after Securing Environment </h2>





