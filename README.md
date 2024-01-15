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

 <h2>Course of Action</h2>
  
-Establishing the honeynet: To start, I created the vulnerable environment with the Virtual Machines. This was done by disabling the firewall inside of the VM as well as allowing all ports and traffic to be received by the Network Security Group (NSG).

-Tracking and examination: The Azure infrastructure was meticulously configured to seamlessly ingest log sources from a multitude of resources into a dedicated log analytics workspace. Leveraging the advanced capabilities of Microsoft Sentinel, sophisticated attack maps were meticulously constructed, meticulously triggering highly precise alerts and meticulously generating comprehensive incidents, all meticulously derived from the meticulously collected and meticulously analyzed data.

-Tracking and evaluating security metrics: I monitored the unsecured environment for a full day, noting important security measurements during that time. This served as a starting point for comparison once I applied security improvements.

-Addressing and resolving security incidents: Following the resolution of incidents and identification of vulnerabilities, I proceeded to fortify the environment by implementing security best practices and incorporating Azure-specific recommendations.

-Analysis after implementing remediation measures: An additional 24-hour period was dedicated to the meticulous re-observation of the environment, facilitating a comprehensive evaluation of the security metrics. The resulting data was then meticulously juxtaposed with the initial baseline, enabling a rigorous comparative analysis.

<h2>Enviroments Used </h2>

- <b>2x Windows 10 Pro</b> (21H2)
- <b>Linux Server</b>
- <b>Log Analytics Workspace (Kusto Query Lanuage KQL Queries) </b>
- <b>Azure Virtual Network (VNet) </b>

<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img width="766" alt="Installing Domain" src="https://github.com/AndreCyberT/ActiveDirectorylab/assets/143320920/11877ddb-62d3-4809-ba17-1140893afe19">

<p align="center">
Creating users with Powershell <br/>
<img width="775" alt="creating users for power shell" src="https://github.com/AndreCyberT/ActiveDirectorylab/assets/143320920/801047e0-1ae3-426a-9f4c-e6f65c1f14bf">

<p align="center">
Running Users <br/>
<img width="774" alt="Running users" src="https://github.com/AndreCyberT/ActiveDirectorylab/assets/143320920/a1cc5472-fabe-4a4a-89c1-852f66cb2963">
