# SOC Level 1 — Learning Notes & Progress

This folder contains my hands-on lab notes, incident triage workflows, SIEM queries, and investigation walkthroughs for the **SOC Level 1 (Security Operations Center)** path on TryHackMe.

Being a good defender requires understanding both attack behaviors and how they appear in logs. In this path, I'm focusing on:
* **Blue Team & SOC Fundamentals:** Understanding analyst tiers, alert triage, shift handoffs, and standard ticketing workflows.
* **Core Tooling:** Getting comfortable querying and building alerts in SIEMs (Splunk, Elastic) and understanding EDR and SOAR platforms.
* **Defense Frameworks:** Applying the Cyber Kill Chain, Unified Kill Chain, MITRE ATT&CK, and Pyramid of Pain to real alerts.
* **Phishing & Email Analysis:** Header analysis, extracting malicious links/attachments, and defanging indicators.
* **Network & Endpoint Monitoring:** PCAP analysis in Wireshark/NetworkMiner, Snort IDS rules, and Windows/Linux event logs.
* **Threat Intel & Malware Basics:** Using VirusTotal, Hybrid Analysis, and threat intel feeds to attribute IOCs.
* **Capstone Challenges:** Full incident investigations where I connect multiple alerts to reconstruct the full intrusion timeline.

---

## My Progress Tracker

### 1. [Blue Team Introduction](./01-Blue-Team-Introduction/README.md)
* [ ] [Junior Security Analyst Intro](./01-Blue-Team-Introduction/Junior-Security-Analyst-Intro/README.md)
* [ ] [SOC Role in Blue Team](./01-Blue-Team-Introduction/SOC-Role-in-Blue-Team/README.md)
* [ ] [Humans as Attack Vectors](./01-Blue-Team-Introduction/Humans-as-Attack-Vectors/README.md)
* [ ] [Systems as Attack Vectors](./01-Blue-Team-Introduction/Systems-as-Attack-Vectors/README.md)

### 2. [SOC Team Internals](./02-SOC-Team-Internals/README.md)
* [ ] [SOC L1 Alert Triage](./02-SOC-Team-Internals/SOC-L1-Alert-Triage/README.md)
* [ ] [SOC L1 Alert Reporting](./02-SOC-Team-Internals/SOC-L1-Alert-Reporting/README.md)
* [ ] [SOC Workbooks and Lookups](./02-SOC-Team-Internals/SOC-Workbooks-and-Lookups/README.md)
* [ ] [SOC Metrics and Objectives](./02-SOC-Team-Internals/SOC-Metrics-and-Objectives/README.md)
* [ ] [SOC Simulator Introduction to Phishing](./02-SOC-Team-Internals/SOC-Simulator-Introduction-to-Phishing/README.md)

### 3. [Core SOC Solutions](./03-Core-SOC-Solutions/README.md)
* [ ] [Introduction to EDR](./03-Core-SOC-Solutions/Introduction-to-EDR/README.md)
* [ ] [Introduction to SIEM](./03-Core-SOC-Solutions/Introduction-to-SIEM/README.md)
* [ ] [Splunk Basics](./03-Core-SOC-Solutions/Splunk-Basics/README.md)
* [ ] [Elastic Stack Basics](./03-Core-SOC-Solutions/Elastic-Stack-Basics/README.md)
* [ ] [Introduction to SOAR](./03-Core-SOC-Solutions/Introduction-to-SOAR/README.md)

### 4. [Cyber Defence Frameworks](./04-Cyber-Defence-Frameworks/README.md)
* [ ] [Pyramid of Pain](./04-Cyber-Defence-Frameworks/Pyramid-of-Pain/README.md)
* [ ] [Cyber Kill Chain](./04-Cyber-Defence-Frameworks/Cyber-Kill-Chain/README.md)
* [ ] [Unified Kill Chain](./04-Cyber-Defence-Frameworks/Unified-Kill-Chain/README.md)
* [ ] [MITRE](./04-Cyber-Defence-Frameworks/MITRE/README.md)
* [ ] [Summit](./04-Cyber-Defence-Frameworks/Summit/README.md)
* [ ] [Eviction](./04-Cyber-Defence-Frameworks/Eviction/README.md)

### 5. [Phishing Analysis](./05-Phishing-Analysis/README.md)
* [ ] [Phishing Analysis Fundamentals](./05-Phishing-Analysis/Phishing-Analysis-Fundamentals/README.md)
* [ ] [Phishing Emails in Action](./05-Phishing-Analysis/Phishing-Emails-in-Action/README.md)
* [ ] [Phishing Analysis Tools](./05-Phishing-Analysis/Phishing-Analysis-Tools/README.md)
* [ ] [Phishing Prevention](./05-Phishing-Analysis/Phishing-Prevention/README.md)
* [ ] [The Greenholt Phish](./05-Phishing-Analysis/The-Greenholt-Phish/README.md)
* [ ] [Snapped Phish ing Line](./05-Phishing-Analysis/Snapped-Phish-ing-Line/README.md)
* [ ] [SOC Simulator Phishing Unfolding](./05-Phishing-Analysis/SOC-Simulator-Phishing-Unfolding/README.md)

### 6. [Network Traffic Analysis](./06-Network-Traffic-Analysis/README.md)
* [ ] [Network Traffic Basics](./06-Network-Traffic-Analysis/Network-Traffic-Basics/README.md)
* [ ] [Wireshark Basics](./06-Network-Traffic-Analysis/Wireshark-Basics/README.md)
* [ ] [Packet Operations](./06-Network-Traffic-Analysis/Packet-Operations/README.md)
* [ ] [Traffic Analysis](./06-Network-Traffic-Analysis/Traffic-Analysis/README.md)
* [ ] [NetworkMiner](./06-Network-Traffic-Analysis/NetworkMiner/README.md)

### 7. [Network Security Monitoring](./07-Network-Security-Monitoring/README.md)
* [ ] [Network Security Essentials](./07-Network-Security-Monitoring/Network-Security-Essentials/README.md)
* [ ] [Network Discovery Detection](./07-Network-Security-Monitoring/Network-Discovery-Detection/README.md)
* [ ] [Data Exfiltration Detection](./07-Network-Security-Monitoring/Data-Exfiltration-Detection/README.md)
* [ ] [Man in the Middle Detection](./07-Network-Security-Monitoring/Man-in-the-Middle-Detection/README.md)
* [ ] [IDS Fundamentals](./07-Network-Security-Monitoring/IDS-Fundamentals/README.md)
* [ ] [Snort](./07-Network-Security-Monitoring/Snort/README.md)

### 8. [Web Security Monitoring](./08-Web-Security-Monitoring/README.md)
* [ ] [Web Security Essentials](./08-Web-Security-Monitoring/Web-Security-Essentials/README.md)
* [ ] [Detecting Web Attacks](./08-Web-Security-Monitoring/Detecting-Web-Attacks/README.md)
* [ ] [Detecting Web Shells](./08-Web-Security-Monitoring/Detecting-Web-Shells/README.md)
* [ ] [Detecting Web DDoS](./08-Web-Security-Monitoring/Detecting-Web-DDoS/README.md)
* [ ] [SOC Simulator Upload and Conquer](./08-Web-Security-Monitoring/SOC-Simulator-Upload-and-Conquer/README.md)

### 9. [Windows Security Monitoring](./09-Windows-Security-Monitoring/README.md)
* [ ] [Windows Logging for SOC](./09-Windows-Security-Monitoring/Windows-Logging-for-SOC/README.md)
* [ ] [Windows Threat Detection 1](./09-Windows-Security-Monitoring/Windows-Threat-Detection-1/README.md)
* [ ] [Windows Threat Detection 2](./09-Windows-Security-Monitoring/Windows-Threat-Detection-2/README.md)
* [ ] [Windows Threat Detection 3](./09-Windows-Security-Monitoring/Windows-Threat-Detection-3/README.md)

### 10. [Linux Security Monitoring](./10-Linux-Security-Monitoring/README.md)
* [ ] [Linux Logging for SOC](./10-Linux-Security-Monitoring/Linux-Logging-for-SOC/README.md)
* [ ] [Linux Threat Detection 1](./10-Linux-Security-Monitoring/Linux-Threat-Detection-1/README.md)
* [ ] [Linux Threat Detection 2](./10-Linux-Security-Monitoring/Linux-Threat-Detection-2/README.md)
* [ ] [Linux Threat Detection 3](./10-Linux-Security-Monitoring/Linux-Threat-Detection-3/README.md)
* [ ] [SOC Simulator BlackCat](./10-Linux-Security-Monitoring/SOC-Simulator-BlackCat/README.md)

### 11. [Malware Concepts for SOC](./11-Malware-Concepts-for-SOC/README.md)
* [ ] [Malware Classification](./11-Malware-Concepts-for-SOC/Malware-Classification/README.md)
* [ ] [Intro to Malware Analysis](./11-Malware-Concepts-for-SOC/Intro-to-Malware-Analysis/README.md)
* [ ] [Living Off the Land Attacks](./11-Malware-Concepts-for-SOC/Living-Off-the-Land-Attacks/README.md)
* [ ] [Shadow Trace](./11-Malware-Concepts-for-SOC/Shadow-Trace/README.md)

### 12. [Threat Analysis Tools](./12-Threat-Analysis-Tools/README.md)
* [ ] [Intro to Cyber Threat Intel](./12-Threat-Analysis-Tools/Intro-to-Cyber-Threat-Intel/README.md)
* [ ] [File and Hash Threat Intel](./12-Threat-Analysis-Tools/File-and-Hash-Threat-Intel/README.md)
* [ ] [IP and Domain Threat Intel](./12-Threat-Analysis-Tools/IP-and-Domain-Threat-Intel/README.md)
* [ ] [Invite Only](./12-Threat-Analysis-Tools/Invite-Only/README.md)

### 13. [SIEM Triage for SOC](./13-SIEM-Triage-for-SOC/README.md)
* [ ] [Log Analysis with SIEM](./13-SIEM-Triage-for-SOC/Log-Analysis-with-SIEM/README.md)
* [ ] [Alert Triage With Splunk](./13-SIEM-Triage-for-SOC/Alert-Triage-With-Splunk/README.md)
* [ ] [Alert Triage With Elastic](./13-SIEM-Triage-for-SOC/Alert-Triage-With-Elastic/README.md)
* [ ] [ItsyBitsy](./13-SIEM-Triage-for-SOC/ItsyBitsy/README.md)
* [ ] [Benign](./13-SIEM-Triage-for-SOC/Benign/README.md)

### 14. [SOC Level 1 Capstone Challenges](./14-SOC-Level-1-Capstone-Challenges/README.md)
* [ ] [Tempest](./14-SOC-Level-1-Capstone-Challenges/Tempest/README.md)
* [ ] [Boogeyman 1](./14-SOC-Level-1-Capstone-Challenges/Boogeyman-1/README.md)
* [ ] [Boogeyman 2](./14-SOC-Level-1-Capstone-Challenges/Boogeyman-2/README.md)
* [ ] [Boogeyman 3](./14-SOC-Level-1-Capstone-Challenges/Boogeyman-3/README.md)
* [ ] [SOC Simulator Hidden Hooks](./14-SOC-Level-1-Capstone-Challenges/SOC-Simulator-Hidden-Hooks/README.md)
* [ ] [SOC Simulator Open Door](./14-SOC-Level-1-Capstone-Challenges/SOC-Simulator-Open-Door/README.md)

---

[Back to main portfolio](../README.md)
