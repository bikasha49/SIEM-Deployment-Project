# 🛡️ Splunk Enterprise SIEM Deployment

| Category | Details |
| :--- | :--- |
| **🛡️ Role** | Security Operations (SOC) Analyst Project |
| **💻 Tech Stack** | ![Splunk](https://img.shields.io/badge/Splunk-Enterprise-000000?style=flat-square&logo=splunk&logoColor=white) ![Kali](https://img.shields.io/badge/Kali-Linux-5C1F87?style=flat-square&logo=kalilinux&logoColor=white) ![Windows](https://img.shields.io/badge/Windows-10-0078D6?style=flat-square&logo=windows&logoColor=white) |
| **🎯 Focus** | Log Ingestion, Windows Event Analysis and Threat Detection |

## 📌 Executive Summary
This project demonstrates the deployment of a fully functional **Security Information and Event Management (SIEM)** architecture. I designed and built a lab environment to simulate a corporate network, focusing on the lifecycle of a security log: from generation on the endpoint, to transmission via forwarders, to indexing and visualization on the SIEM.

Unlike basic installations, this project focuses on the **engineering** side of a SOC: configuring `inputs.conf` for granular data collection, troubleshooting network ingest pipelines, and normalizing data for analysis.

## 🏗️ Architecture & Topology
The environment consists of a centralized Indexer receiving encrypted logs from a Windows endpoint.

* **SIEM Server (Indexer/Search Head):** Kali Linux
* **Target Endpoint:** Windows 10 Enterprise
* **Log Shipper:** Splunk Universal Forwarder (UF)
* **Data Sources Configured:**
    * **Security Log:** Auditing login attempts (`EventCode 4625`) and privilege escalation.
    * **System Log:** Monitoring service changes and OS-level errors.
    * **Application Log:** Tracking software crashes and installation events.

## 📸 Operational Evidence ("The Money Shots")

### 1. The "Single Pane of Glass" (Dashboard)
*A real-time data summary dashboard confirming successful log ingestion from the Windows 10 endpoint (`DESKTOP-4BE3VH6`). This view allows analysts to monitor event velocity and source types.*
![Splunk Dashboard](41%20data%20summary.png)

### 2. Live Telemetry Verification
*Validating the indexing pipeline. Here, I confirmed that raw event logs (`WinEventLog:Security`) are being correctly parsed and time-stamped by the indexer.*
![Log Search](43%20collecting%20a%20logs.png)

### 3. Configuration Management (Infrastructure as Code)
*Configuring the `inputs.conf` stanza on the Universal Forwarder. I defined granular inputs to filter noise and ensure only critical security events are forwarded.*
![Configuration](30%20need%20to%20change%20inputs%20.png)

## 🔧 Technical Implementation Details

### 🔹 Phase 1: Infrastructure Hardening
* Deployed **Splunk Enterprise** on a Linux kernel (Kali).
* Configured persistent boot services (`enable boot-start`) to ensure high availability.
* Established network bridging to allow isolated VMs to communicate securely while maintaining segmentation.

### 🔹 Phase 2: Log Forwarding (The "Plumbing")
* Installed the **Universal Forwarder (UF)** agent on the endpoint.
* Configured `inputs.conf` to capture the three critical Windows log channels:
    1.  `[WinEventLog://Security]` - For detecting authentication attacks.
    2.  `[WinEventLog://System]` - For operational health monitoring.
    3.  `[WinEventLog://Application]` - For application error tracking.
* **Troubleshooting:** Diagnosed a service failure where the Forwarder could not read Security logs. Resolved by escalating service privileges to the `Local System` account.

### 🔹 Phase 3: Detection Logic & Analysis
* Verified data flow using the Splunk Search Processing Language (SPL):
   ```splunk
   index=main host="Windows10-Endpoint" sourcetype="WinEventLog:Security" | stats count by EventCode

## 🧠 Competencies Demonstrated
* **Log Pipeline Management:** Deep understanding of how data moves from *Edge* (Forwarder) to *Index* (Server).
* **Linux CLI Administration:** Managing system services (`systemctl`), modifying file permissions (`chmod`), and handling package installations (`dpkg`).
* **Troubleshooting:** Diagnosing complex network connectivity issues (firewall rules) and resolving endpoint service failures.
* **Windows Event Architecture:** Selecting and filtering the correct log channels (System vs. Security) to ensure effective monitoring without log fatigue.
---

<div align="center">

### 🌐 Let's Connect

<a href="https://www.linkedin.com/in/bikasha-gurung">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn" />
</a>

<br />
<br />

*If you found this project helpful, please give it a Star! ⭐*

</div>
