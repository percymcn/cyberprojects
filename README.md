# cyberprojects
#                     Building a SOC + Honeynet in Azure (Live Traffic)
![image](https://github.com/percymcn/cyberprojects/assets/162523236/74f50eb0-b092-4254-84fd-2907c5fa6d39)

Introduction
In this project, I build a mini honeynet in Azure and ingest log sources from various resources into a Log Analytics workspace, which is then used by Microsoft Sentinel to build attack maps, trigger alerts, and create incidents. I measured some security metrics in the insecure environment for 24 hours, apply some security controls to harden the environment, measure metrics for another 24 hours, then show the results below. The metrics we will show are:

SecurityEvent (Windows Event Logs)
Syslog (Linux Event Logs)
SecurityAlert (Log Analytics Alerts Triggered)
SecurityIncident (Incidents created by Sentinel)
AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)
Architecture Before Hardening / Security Controls o harden the environment, measure metrics for another 24 hours, then show the results below. 

The metrics we will show are:
SecurityEvent (Windows Event Logs)
Syslog (Linux Event Logs)
SecurityAlert (Log Analytics Alerts Triggered)
SecurityIncident (Incidents created by Sentinel)
AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)


# Architecture Before Hardening / Security Controls

![image](https://github.com/percymcn/cyberprojects/assets/162523236/74badd06-2a41-4e86-8702-340e34030a33)
# Architecture After Hardening / Security Controls

![image](https://github.com/percymcn/cyberprojects/assets/162523236/100b7d78-1cea-4f37-a3b9-68348566cea9)


The architecture of the mini honeynet in Azure consists of the following components:

Virtual Network (VNet)
Network Security Group (NSG)
Virtual Machines (2 windows, 1 linux)
Log Analytics Workspace
Azure Key Vault
Azure Storage Account
Microsoft Sentinel
For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

For the "AFTER" metrics, Network Security Groups were hardened by blocking ALL traffic with the exception of my admin workstation, and all other resources were protected by their built-in firewalls as well as Private Endpoint
