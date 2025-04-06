# Comprehensive Splunk SIEM Deployment Project

## Executive Summary
This project demonstrates a full deployment of Splunk as a Security Information and Event Management (SIEM) platform, showcasing the installation, configuration, and use of Splunk Enterprise alongside Universal Forwarders on Windows and Linux endpoints.

The goal was to build a mini-SOC environment: a central Splunk server collecting logs from a Windows 10 workstation and a Linux system. Key security configurations (such as SSL encryption and admin controls) were enabled to harden the SIEM, and essential Splunk apps/add-ons (like Splunk Security Essentials and the Splunk Add-on for Microsoft Windows) were installed to extend functionality. As a result, the Splunk server successfully ingests and indexes Windows event logs (Security, System, Application) and Linux system logs, with end-to-end verification of data flow.

### Splunk Enterprise Installation Setup Step by Step on (Kali Linux)
The deployment began with setting up the Splunk Enterprise server on a Kali Linux machine. After downloading the Splunk Enterprise installer (Debian package) from Splunk’s website, it was installed via the command line.


![Installing Splunk Enterprise on Kali Linux](screenshots/splunk_installation.png)

### Initial Access and Configuration
With Splunk Enterprise running, the web interface became accessible on port 8000.

![Splunk web interface ready for first login](screenshots/splunk_web_interface.png)

### Universal Forwarder Deployment (Windows 10)
The next part of the environment setup was installing the Splunk Universal Forwarder (UF) on a Windows 10 machine to serve as a log source.

![Configuring the Universal Forwarder during installation](screenshots/uf_configuration.png)

## Security Configurations

### Enabling SSL for Splunk Web
Securing the Splunk deployment was a priority. By default, Splunk’s web interface can run on HTTP – in our case it was initially on `http://192.168.79.128:8000`. To follow best practices, we enabled SSL encryption for Splunk Web.

![Enabling HTTPS for the web interface](screenshots/enable_https.png)

### Splunk Security Essentials (SSE) App
Next, we installed Splunk Security Essentials (SSE), a free app from Splunk that provides a library of security use-cases, guides, and pre-built detections.

![Confirmation of Splunk Security Essentials installation](screenshots/sse_installation.png)

### Installing Relevant Add-ons (Windows Logs)
In addition to SSE, we deployed the Splunk Add-on for Microsoft Windows, which is essential for collecting and parsing Windows host logs.

![Installing Splunk Add-on for Microsoft Windows](screenshots/windows_addon_installation.png)

## Data Ingestion

### Configuring Data Inputs on Splunk (Receiver)
On the Splunk Enterprise server, we configured it to receive data from the Universal Forwarders by enabling the listening port 9997 for incoming forwarded data.

![Enabling the listening port 9997](screenshots/enable_listening_port.png)

### Enabling Log Collection on Forwarders
On the data source side, we configured what logs to send. For the Windows 10 forwarder, this meant enabling the monitoring of the Windows Event Logs.

![Windows Event Log inputs enabled](screenshots/windows_event_log_inputs.png)

### Verifying Log Flow from Endpoints
Once the inputs were enabled and forwarders running, we verified that logs were indeed flowing into the Splunk server.

![Verifying log flow from endpoints](screenshots/log_flow_verification.png)

## Monitoring & Management

### Forwarder Management and Status
An important aspect of operating a SIEM is monitoring the health and status of log collectors (forwarders).

![Forwarder Management](screenshots/forwarder_management.png)

### Service Control and Reliability
We also verified the forwarder’s service on the Windows endpoint at the OS level.

![Windows Services showing SplunkForwarder service running](screenshots/windows_services.png)

## Final Summary
Deploying Splunk Enterprise with Universal Forwarders on Windows and Linux provided hands-on experience in building a functional SIEM platform from scratch. The process required knowledge of systems administration, networking, and security configuration. This project demonstrates the ability to set up, secure, and manage a SIEM environment, highlighting practical skills relevant to SOC or cybersecurity analyst roles.

### Lessons Learned
- Importance of planning and configuring inputs.
- Verification of each change to avoid blind spots.
- Value of Splunk add-ons and apps in accelerating deployment.
- End-to-end understanding of Splunk’s architecture and practical implementation.

## Screenshots
- [Installing Splunk Enterprise](screenshots/splunk_installation.png)
- [Splunk web interface ready for first login](screenshots/splunk_web_interface.png)
- [Configuring the Universal Forwarder during installation](screenshots/uf_configuration.png)
- [Enabling HTTPS for the web interface](screenshots/enable_https.png)
- [Confirmation of Splunk Security Essentials installation](screenshots/sse_installation.png)
- [Installing Splunk Add-on for Microsoft Windows](screenshots/windows_addon_installation.png)
- [Enabling the listening port 9997](screenshots/enable_listening_port.png)
- [Windows Event Log inputs enabled](screenshots/windows_event_log_inputs.png)
- [Verifying log flow from endpoints](screenshots/log_flow_verification.png)
- [Forwarder Management](screenshots/forwarder_management.png)
- [Windows Services showing SplunkForwarder service running](screenshots/windows_services.png)
