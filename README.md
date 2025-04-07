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

## Skilled in capturing and presenting step-by-step technical workflows with visuals
## Step 1
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/bc8e634c9eafe21f92e9744cf6f915283c6cdd39/1%20.png) 
## Step 2
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/286351972c50b9e2880c811e43feb0956af47b31/2.png)
## Step 3
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/529dff5a0790c90985aa458fa51a536ef1b81c26/3%20done%20install%20.png)
## Step 4
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/4%20start.png)
## Step 5
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/5%20localhost%20.png)
## Step 6
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/6%20splunk%20ready%20to%20login%20in%20localhost.png)
## Step 7
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/7%20splunk%20home%20page.png)
## Step 8
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/8%20SSL%20encrypted.png)
## Step 9
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/9%20restarting%20.png)
## Step 10
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/10%20restart.png)
## Step 11
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/11%20self%20sign%20certificate.png)
## Step 12
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/12%20isntalling%20security%20essentials%20.png)
## Step 13
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/13%20getting%20data%20forwarding%20and%20receiving.png)
## Step 14
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/14%20re%20ceiving%20portf%209997.png)
## Step 15
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/15%20installing%20splunkforwarder%20in%20windows10.png)
## Step 16
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/16%20select%20local%20system.png)
## Step 17
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/17%20deafult%20%26%20next.png)
## Step 18
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/18%20administrator%20username%20%26%20password.png)
## Step 19
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/19%20splunk%20deployement%20server%20ip%20and%20deafult%20port.png)
## Step 20
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/20%20receiving%20indexer%20ip%20and%20deafult%20tcp%20port.png)
## Step 21
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/21%20done%20instalation%20SplunkUniversalForwarder.png)
## Step 22
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/22%20cheking%20Services%20.png)
## Step 23
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/22%20cheking%20Services%20.png)
## Step 24
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/24%20restarting%20SplunkForwarder.png)
## Step 25
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/25%20dowloading%20Splunk%20Add-On%20Microsoft%20Windows.png)
## Step 26
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/26%20extracted%20Splunk-add_on%20.png)
## Step 27
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/27%20deployement%20server%20outputs.png)
## Step 28
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/28%20deployement%20client.png)
## Step 29
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/29%20pest%20the%20Splunk-TA_Windows.png)
## Step 30
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/30%20need%20to%20change%20inputs%20.png)
## Step 31
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/31%20change%20the%20value%20of%20input%20and%20save%20on%20local%20folder.png)
## Step 32
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/32%20restart%20the%20services%20again.png)
## Step 33
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/33%20download%20splunkforwarder%20in%20kali%20linux.png)
## Step 34
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/34%20splunk%20forwarder%20is%20done%20instalation.png)
## Step 35
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/35%20receiving%20data%20port%20tcp%20deafult%20port%20.png)
## Step 36
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/36%20receiving%20data%20tcp%20port%20is%20add%20it.png)
## Step 37
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/37%20add%20data%20from%20splunk%20server.png)
## Step 38
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/38%20splunk%20forwarder%20click.png)
## Step 39
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/39%20data%20receiving%20from%20endpoint.png)
## Step 40
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/40%20hostname%20is%20match.png)
## Step 41
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/41%20data%20summary.png)
## Step 42
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/42%20receiving%20data%20from%20endpoint.png)
## Step 43
### ![image_alt](https://github.com/bikasha49/SIEM-Deployment-Project/blob/b9c74f019bb2ae266600dbce2d721a60b562dbde/43%20collecting%20a%20logs.png)








