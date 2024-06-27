
 Building a SOC + Honeynet in Azure (Live Traffic)
![Cloud Honeynet / SOC](https://i.imgur.com/ZWxe03e.jpg)

## Introduction 

In this project, I built a mini honeynet in Microsoft Azure and ingested log sources from various resouces into a Log Anayltcis workspace. This is then ussed by Microsoft Sentinel to build attack maps, trigger alerts, and create incidents. After configuring log collection on the INSECURE environment, I then set security metrics, then observed the environment for 24 hours. After investigating the incidents that Sentinel genereated during that period, security controls were applied to harden the environment. I then measured metrics for another 24 hours. The metrics showed:

- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents Created by Sentinel)
- AzureNetworkAnalyticsCL (Malicious flows allowed into our honeynet)



## Technologies, Azure Components, and Regulations Employed 

- Azure Network Security Groups (NSG)
- Azure Virtual Network (VNet)
- Virtual Machines (2 Windows VMs, 1 Linux VM)
- Azure Key Vault for Secure Secrets Management
- Azure Storage Account for Data Storage
- Microsoft Sentinel for Security Information and Event Management (SIEM)
- Microsoft Defender for Cloud to Protect Cloud Resources
- Window Remote Desktop for Remote Access
- Command Line Interface (CLI) for System Management
- PowerShell for Automation and Configuration Management
- Microsoft Cloud Security Benchmark
- Azure CSPM
- NIST SP 800-53 Revision 5 for Security Controls
- NIST 800-61 Revison 2 for Incident Handling Guidance



- 
