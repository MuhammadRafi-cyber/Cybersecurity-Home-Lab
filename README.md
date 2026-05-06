# Cybersecurity-Home-Lab
This project involves the creation of a dedicated, isolated home lab environment designed to simulate real-world cyber attacks and defensive monitoring. By integrating Kali Linux as the adversary and Windows 10 as the monitored endpoint, I successfully implemented a SIEM.


**🛡️ Endpoint Security Monitoring Lab: Splunk SIEM & Sysmon Integration**


**📝 Project Overview**

This project involves the creation of a dedicated, isolated home lab environment designed to simulate real-world cyber attacks and defensive monitoring. By integrating Kali Linux as the adversary and Windows 10 as the monitored endpoint, I successfully implemented a SIEM (Security Information and Event Management) pipeline using Splunk Enterprise and Sysmon.

This lab serves as a practical foundation for understanding EDR (Endpoint Detection and Response), log analysis, and incident response within an audited IT infrastructure.

**🏗️ Network Architecture**

The environment is built on a VirtualBox infrastructure using a segmented network to ensure safety and isolation from the host machine.
- Attacker Node: Kali Linux (IP: 192.168.20.11) 
- Target Node: Windows 10 (IP: 192.168.20.10)
- Monitoring Stack: Splunk Enterprise & Sysmon
- Subnet: 192.168.20.0/24

**🛠️ Tools & Technologies**

- Virtualization: Oracle VirtualBox
- Attacker OS: Kali Linux (Nmap, Metasploit)
- Target OS: Windows 10 (Endpoint)
- Log Collection: Microsoft Sysmon (System Monitor)
- SIEM Platform: Splunk Enterprise
- Analysis: SPL (Splunk Processing Language)

**🚀 Implementation Steps**

1. Network Configuration: Established a manual IP scheme for internal network communication to prevent external traffic interference.
   
2. Endpoint Hardening: Configured Windows 10 with Sysmon utilizing the SwiftOnSecurity configuration for granular event logging.
   
3. SIEM Deployment: Installed and configured Splunk Enterprise to ingest Event Logs and Sysmon data via the Universal Forwarder/Manual Add-on methods.
   
4. Simulation: Executed basic reconnaissance and network discovery from Kali Linux to trigger telemetry in the SIEM dashboard.

**🛠️ Technical Challenges & Troubleshooting**

During the deployment, several technical hurdles were encountered and resolved, demonstrating resilience and infrastructure knowledge:

- Splunk App Installation (JSON.parse error): Due to strict network isolation, the internal Splunkbase API was unreachable. I resolved this by performing a manual offline deployment of the .tgz Sysmon Add-on via the Splunk Web UI.
  
- Guest Additions Driver Conflict: Encountered a system hang during the Windows driver installation. This was resolved through a hard reset and service verification, ensuring VirtualBox integration services were correctly registered in the Windows registry.
  
- Network Visibility: Addressed "No-Carrier" interface issues by manually bringing up the virtual adapters via the Linux CLI and verifying cable connectivity in the hypervisor settings.

**📊 Key Learning Outcomes**

- Understanding the flow of telemetry from an endpoint to a centralized SIEM.
- Proficiency in configuring isolated virtual networks for safe security testing.
- Developing a "Detective Control" mindset, aligning with COBIT frameworks for information systems auditing.
- Practical experience in troubleshooting complex virtualization and software integration issues.

**📜 Acknowledgements**

Special thanks to the MyDFIR YouTube community for providing the foundational tutorial for this lab setup.
