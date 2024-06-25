 Building a SOC + Honeynet in Azure (Live Traffic)
![Cloud Honeynet / SOC](https://i.imgur.com/ZWxe03e.jpg)

## Introduction 

In this project, I built a mini honeynet in Microsoft Azure and ingested log sources from various resouces into a Log Anayltcis workspace. This is then ussed by Microsoft Sentinel to build attack maps, trigger alerts, and create incidents. After configuring log collection on the INSECURE environment, I then set security metrics, then observed the environment for 24 hours. After investigating the incidents that Sentinel genereated during that period, security controls were applied to harden the environment. I then measured metrics for another 24 hours. The metrics showed:

- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents Created by Sentinel)
- AzureNetworkAnalyticsCL (Malicious flows allowed into our honeynet)

## Architecture Before Hardenining / Security Controls 
