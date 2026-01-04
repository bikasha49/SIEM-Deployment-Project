# On Prem Splunk SIEM Deployment

## Project Summary

This project demonstrates how to build a security information and event management environment using Splunk Enterprise on a Linux host.  A Windows endpoint generates logs that are shipped via a Universal Forwarder.  The lab shows how to collect, forward, and analyse security telemetry to support a SOC analyst workflow.  The goal is to learn the engineering side of a SIEM, not just installation and to highlight tangible results.

## Project Architecture
<img src="https://github.com/bikasha49/SIEM-Deployment-Project/blob/3cbf7a8b97697573edf9952015fe0fefab00bde4/images/Splunk-SIEM-architecture-diagram.png" alt="Project Architecture" width="80%">
</p>
The environment consists of a Windows 10 endpoint, a Splunk Universal Forwarder and a Splunk Enterprise server acting as indexer and search head.  Logs flow from the endpoint to the forwarder and then to the server.  The high‑resolution diagram above makes it easy to see the components and log flow at a glance.

## Project Objectives

• Build an on premise SIEM environment with Splunk

• Collect Windows Security, System and Application logs using a Universal Forwarder

• Practice SOC analyst investigation and threat hunting

• Align detections with the MITRE ATT&CK framework

## Results and Outcomes

• Demonstrated end‑to‑end log ingestion from a Windows endpoint into Splunk, verifying that Security, System and Application events arrived within seconds of occurrence.

• Detected multiple categories of suspicious activity, including repeated logon failures, unexpected service installations and new local user creation.

• Mapped each detection to specific MITRE ATT&CK techniques, showing coverage across initial access, persistence and privilege escalation.

• Produced a high‑resolution architecture diagram and documented steps to allow others to replicate the lab.

## Environment Setup

• Deployed Splunk Enterprise on a Kali Linux virtual machine and created an administrator account

• Enabled data receiving on port 9997 and configured the Splunk service to start on boot

• Established network bridging between the Linux and Windows hosts to enable log forwarding while keeping isolation

## Endpoint Configuration

• Installed Splunk Universal Forwarder on Windows 10 using the official installer

• Configured the service to run as the Local System account and pointed it to the Splunk server IP on port 9997

• Edited inputs.conf to enable Security, System and Application logs and set the index to main

• Edited outputs.conf to define the Splunk server as the data receiver

## Tools and Technologies Used

• Splunk Enterprise (Indexer and Search Head)

• Splunk Universal Forwarder

• Windows 10 Enterprise

• Linux (Kali) as the SIEM server

• Splunk Search Processing Language

## Log Sources Collected

• Windows Security event log (authentication success and failure)

• Windows System log (service status and errors)

• Windows Application log (application crashes and installs)

## Threat Detection Performed

• Monitored failed and successful logon attempts to identify brute force behaviour

• Detected service installations and unexpected service starts that may indicate persistence

• Detected new local user account creation and privilege changes on the endpoint

## MITRE ATT&CK Techniques

• Initial Access: Valid accounts (T1078) — Brute force detection covers this technique

• Persistence: Service installation and modification (T1035) — Monitoring new services and start ups

• Privilege Escalation: User account privilege changes (T1068)

• Defense Evasion: Disabling security logging (T1089) — Noted when logs stop

## Threat Hunting Workflow

• Used Splunk dashboards to monitor log volume and event distribution from the endpoint

• Pivoted from high level alerts to raw event logs using host name, user, and event code filters

• Verified timestamps, processes, and user context to distinguish noise from true incidents

• Followed a structured investigation sequence: triage, analysis, containment, lessons learned

## MITRE ATT&CK Alignment

• Mapped each detection query to tactics and techniques for traceability

• Demonstrated coverage of multiple stages of the attack lifecycle

• Used the framework to prioritise additional detection ideas

## Operational Evidence

### 1️⃣ Splunk Dashboard Access
Shows successful access to the Splunk Enterprise dashboard.
![Splunk Dashboard Home](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/splunk_dashboard_home.png)

### 2️⃣ Secure Web Access (HTTPS Enabled)
Confirms SSL/HTTPS is enabled for secure Splunk Web access.
![HTTPS Enabled](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/splunk_https_enabled.png)

### 3️⃣ Indexer Receiving Port Enabled
Shows TCP port 9997 enabled to receive data from Universal Forwarders.
![Receiving Port 9997](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/splunk_receiving_port_9997_enabled.png)

### 4️⃣ Data Ingestion Detected
Confirms Splunk successfully detected incoming log data.
![Data Ingestion Detected](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/splunk_data_ingestion_detected.png)

### 5️⃣ Data Summary View
Displays hosts, sources, and sourcetypes actively indexed.
![Data Summary](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/data_summary.png)

### 6️⃣ Real-Time Search Results
Shows indexed Windows events with timestamps and host context.
![Search Results](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/search_results.png)

### 7️⃣ Log Source Breakdown
Breakdown of Security, System, and Application logs.
![Source Breakdown](https://github.com/bikasha49/SIEM-Deployment-Project/blob/950eeff811def6df75f3089b6a05a43b40f84653/images/source_breakdown.png)


## Security Best Practices Applied

• Masked credentials and IP addresses in documentation

• Used encrypted communication between forwarder and indexer

• Limited inbound and outbound firewall rules to required ports

• Noted differences between lab and production settings and avoided exposing sensitive details

## What I Gained from This Project

• Hands on experience deploying Splunk Enterprise and the Universal Forwarder

• Deep understanding of log pipelines and configuration management

• Practice writing SPL queries for threat detection and threat hunting

• Ability to map detections to the MITRE ATT&CK framework

## Project Value

• Demonstrates readiness for SOC analyst and security engineering roles

• Shows practical ability to build and maintain an on premise SIEM

• Provides documented evidence of detection logic and analysis skills

## Screenshots and Evidence 👉 *[Click here](https://github.com/bikasha49/SIEM-Deployment-Project/tree/main/images)*
### 🌐 Let's Connect

<a href="https://www.linkedin.com/in/bikasha-gurung">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn" />
</a>
