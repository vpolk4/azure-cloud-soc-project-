
## Building a SOC + Honeynet in Azure (Live Traffic)
![Cloud Honeynet / SOC](https://i.imgur.com/ZWxe03e.jpg)

## Introduction 

In this project, I built a mini honeynet in Microsoft Azure and ingested log sources from various resouces into a Log Anayltcis workspace. This is then used by Microsoft Sentinel to build attack maps, trigger alerts, and create incidents. After configuring log collection on the INSECURE environment, I then set security metrics, then observed the environment for 24 hours. After investigating the incidents that Sentinel genereated during that period, security controls were applied to harden the environment. I then measured metrics for another 24 hours. The metrics showed:

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

 ## Architecture Before Hardening And Security Controls 
In the before, all resouces were initially deployed with public exposure to the internet. This was to attract potential attackers and observe their tactics. The VMs had both their NSGs (Network Security Groups) 
and firewalls open, allowing unretricted access. 

 
![Architecture Diagram](https://i.imgur.com/1tLjWY9.png)

## Architecture After Hardening Security Controls 
For the after stage, I implemented a series of harending measures and security controls to improve the environment's overall security. 


![Architecture Diagram](https://i.imgur.com/ch1cAMU.png)


 

 The following table shows the metrics we measured in our insecure environement for 24 hours:

Start Time 2024-07-05 17:04:29
Stop Time 2024-07-06 17:04:29


| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 13300
| Syslog                   | 1078
| SecurityAlert            | 10
| SecurityIncident         | 348
| AzureNetworkAnalytics_CL | 843

## Attack Maps Before Hardening / Security Controls

```All map queries actually returned no results due to no instances of malicious activity for the 24 hour period after hardening.```


![image](https://github.com/vpolk4/azure-cloud-soc-project-/assets/135063837/5ed37dd4-8f4a-43a1-8948-8bc6daf8c11f)










## Metrics After Hardening / Security Controls


The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls:

Start Time 2024-07-07 17:02:29
Stop Time 2024-07-08 17:02:29

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 6,650
| Syslog                   | 26
| SecurityAlert            | 0
| SecurityIncident         | 0
| AzureNetworkAnalytics_CL | 0
















 
