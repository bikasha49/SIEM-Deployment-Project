# Comprehensive Splunk Enterprise Deployment and Configuration for SOC Analysts: Endpoint Log Monitoring

## Project Summary
This project demonstrates a professional and detailed approach to deploying Splunk within a virtualized environment for cybersecurity operations center (SOC) analyst activities. The process involved setting up Splunk Server in VMware Workstation Pro using Kali Linux, deploying a Windows 10 endpoint machine, and configuring Splunk Universal Forwarder and essential Add-ons on the endpoint to send critical logs (system, security, and application logs) back to the Splunk server for centralized monitoring and analysis.

## Detailed Step-by-Step Implementation

### Installation and Setup
1. Install VMware Workstation Pro on the host machine.
2. Create a new virtual machine and install Kali Linux.
3. Install VMware Tools on Kali Linux.
4. Verify network connectivity and settings (Bridge/NAT mode).

### Splunk Server Configuration (Kali Linux)
5. Download the latest Splunk Enterprise for Linux.
6. Install Splunk Enterprise using terminal commands:
   ```bash
   sudo dpkg -i splunk-*.deb
   ```
   [Installing Splunk Enterprise on Kali Linux](screenshots/splunk_installation.png)
7. Start Splunk Server and set it to auto-start:
   ```bash
   sudo /opt/splunk/bin/splunk start --accept-license
   ```
8. Enable boot-start configuration:
   ```bash
   sudo /opt/splunk/bin/splunk enable boot-start
   ```
9. Access Splunk web interface [http://localhost:8000](http://localhost:8000) and set administrative credentials.

### Endpoint Machine Deployment (Windows 10)
10. Deploy Windows 10 as a second VM in VMware Workstation Pro.
11. Install VMware Tools on Windows 10.
12. Check network connectivity and configurations ensuring endpoint-server communication.

### Splunk Universal Forwarder Installation (Windows 10)
13. Download Splunk Universal Forwarder for Windows.
14. Execute installer and complete the installation process.
15. Specify the deployment server (Kali Linux Splunk server IP and Port).
16. Select and enable Windows Event Logs (System, Security, Application).

### Splunk Add-Ons Installation
17. Download essential Add-ons (e.g., Windows App for Splunk).
18. Extract and place Add-ons into Splunk Universal Forwarder's appropriate directory.
19. Restart Splunk Universal Forwarder to apply the Add-ons.

### Splunk Server Configuration for Data Reception
20. Define receiving port on Splunk server (default: 9997).
21. Confirm receiver settings under Settings > Forwarding and Receiving.
22. Ensure firewall rules allow traffic from endpoint to server.

### Endpoint Configuration for Data Forwarding
23. Edit `outputs.conf` on Windows endpoint to define Splunk server IP and receiving port.
24. Edit `inputs.conf` to specify the logs to forward (System, Security, Application logs).
25. Restart Splunk Universal Forwarder to activate configurations.

### Verification and Testing
26. Perform a connectivity test (ping and network checks).
27. Verify Splunk server receiving data using Splunk search (`index=*`).
28. Confirm logs appear from Windows endpoint in Splunk.

### Splunk Indexes and Source Types Configuration
29. Create dedicated indexes (`windows_logs`, `security_logs`, etc.) on the Splunk server.
30. Set proper source types (`WinEventLog:Security`, `WinEventLog:System`, `WinEventLog:Application`).
31. Configure retention and indexing settings for optimal performance.

### Field Extraction and Parsing Configuration
32. Configure `props.conf` and `transforms.conf` for effective data parsing.
33. Validate field extractions via Splunk's search query.

### Alerts and Reporting Configuration
34. Set custom alerts for critical security events.
35. Define thresholds and notification actions (email alerts, dashboards).
36. Test alerts by generating specific events on the endpoint.

### Dashboard Creation and Visualization
37. Develop dashboards for real-time monitoring.
38. Configure visual panels for easy interpretation of log data.
39. Customize dashboard layout for SOC analyst convenience.

### Final Testing and Validation
40. Simulate various security events and system activities on the endpoint.
41. Confirm event log capture and correct indexing.
42. Document the final Splunk configuration and take relevant screenshots.
43. Compile and review all documentation and screenshots into a structured project report.

## Conclusion
This document's successful deployment and configuration enable SOC analysts to perform effective monitoring, swift incident response, and comprehensive security analysis utilizing Splunk's robust capabilities.

## Hands-On Experience of Screenshots following steps
- [Installing Splunk Enterprise](screenshots/splunk_installation.png)
## Step1
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/bc8e634c9eafe21f92e9744cf6f915283c6cdd39/1%20.png) 
## Step2
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/286351972c50b9e2880c811e43feb0956af47b31/2.png)
