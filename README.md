## RDP Brute Force SOC Investigation
# 🔍Project Overview
```
This project is a SOC (Security Operations Center) investigation of a Windows RDP brute force attack using Splunk SIEM logs. The analysis identifies failed authentication attempts, extracts key forensic indicators, and maps the attack to the MITRE ATT&CK framework.
```
## Screenshot of Dashboard
<img width="1351" height="767" alt="Dashboard for rdp" src="https://github.com/user-attachments/assets/a1fbd3b4-151c-4557-a13e-2cf40768bb3d" />



## 🎯Objective
```
Analyze Windows Security logs (Event ID 4625)
Identify brute force attack patterns
Extract attacker and victim details
Determine attack behavior and timeline
Map findings to MITRE ATT&CK framework
Produce SOC-style incident report
```
## 🛠️Tools Used
```
Splunk SIEM
Windows Security Event Logs
Regex (rex) for field extraction
IP Geolocation (iplocation)
MITRE ATT&CK Framework
```
## 📂Dataset Information
```
Source: BTLO Brute Force Challenge logs
Log Type: Windows Authentication Logs
Event ID Used: 4625 (Logon Failure)
Format: CSV ingested into Splunk
```
## 🔎Investigation Process
```
Step 1: Identify Failed Logins

Filtered authentication failures using Windows Event ID 4625.

Step 2: Extract Key Fields

Extracted:

Username
Source IP
Source Port
Failure Reason
Step 3: Analyze Attack Pattern
Repeated login attempts
Single attacking IP address
Rapid sequential requests
Changing source ports (automation behavior)
Step 4: Threat Confirmation

Confirmed a brute force attack targeting the Windows Administrator account.
```
## 📊Key Findings
```
Field	Value
Total Failed Attempts	3,129+
Targeted User	administrator
Event ID	4625
Source IP	113.161.192.227
Failure Reason	Unknown username or bad password
Source Ports	49735 – 50077
Attack Type	RDP Brute Force
```
## 🌍Geolocation (Threat Intelligence)
```
Source IP: 113.161.192.227
Country: Vietnam (approx.)
Type: External attacker network
```
## 🧠MITRE ATT&CK Mapping
```
Technique ID	Name	Description
T1110	Brute Force	Repeated password guessing attempts
T1078	Valid Accounts (Attempted)	Targeting legitimate system account (administrator)
```
## 📌Conclusion
```
This incident is a confirmed brute force attack against a Windows host. The attack was automated, external, and targeted privileged credentials. Immediate mitigation would include IP blocking, account lockout policies, and monitoring for similar patterns.
```
## 📁Project Structure
```
RDP-Bruteforce-SOC-Investigation/
│
├── README.md
├── incident-report.pdf
├── logs-analysis.txt
├── mitre-mapping.md
│
└── screenshots/
    ├── event-id-4625.png
    ├── failed-logins.png
    ├── splunk-dashboard.png
```
## 🧠Skills Demonstrated
```
SIEM log analysis (Splunk)
Windows Event log investigation
Brute force attack detection
Regex-based field extraction
Threat intelligence (IP analysis)
MITRE ATT&CK mapping
SOC-style reporting
```
# 🏆Outcome
```
This project demonstrates real-world SOC analyst capabilities in detecting and analyzing brute force attacks using SIEM tools and security logs.

