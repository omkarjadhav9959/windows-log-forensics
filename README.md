# windows-log-forensics
Windows Log Forensics is the process of collecting, analyzing, and interpreting Windows event logs to investigate security incidents, detect malicious behavior, and reconstruct attacker activities. It plays a vital role in Incident Response, SOC operations, Threat Hunting, and Malware Analysis.
# Steps to Follow Windows Log Forensics 
@This repository contains:

Windows log types

Important Event IDs

Attack detection examples

Sample queries (Splunk, KQL)

Real-world forensic scenarios

#📂 Types of Windows Logs

1️⃣ Security Logs

Used for tracking authentication, authorization, and account changes.

Event ID	Description
4624	Successful logon
4625	Failed logon
4672	Special privileges assigned
4720	User account created
4726	User account deleted
1102	Security log cleared

📌 Use Cases

Brute-force detection

Unauthorized access

Insider threat investigation

Privilege escalation detection

2️⃣ System Logs

Used for monitoring OS and hardware-level events.

📌 Examples

Unexpected shutdowns

Driver crashes

Service failures

Boot issues

📌 Use Cases

Rootkit detection

Kernel-level attack investigation

Persistence analysis

3️⃣ Application Logs

Used for tracking application behavior.

📌 Examples

Application crashes

Service failures

Unexpected behavior

📌 Use Cases

Malware-infected app analysis

Exploit behavior tracking

Backdoor identification

4️⃣ PowerShell Logs

Used for tracking script-based attacks.

📌 Important Logs

Script Block Logging

Module Logging

PowerShell Operational Logs

📌 Use Cases

Fileless malware detection

Encoded command execution

Living-off-the-Land (LOLBins) abuse

5️⃣ Windows Defender Logs

Used for tracking malware detection and remediation.

📌 Use Cases

Threat identification

Quarantine actions

Real-time protection events

🔍 Common Attack Detection Examples
Example 1: Brute Force Detection

Indicators

Multiple Event ID 4625 (failed logins)

Followed by Event ID 4624 (success)

📌 Splunk Query

index=windows EventCode=4625
| stats count by Account_Name, Source_Network_Address
| where count > 5

Example 2: Privilege Escalation

Indicators

Event ID 4672 (Admin privileges assigned)

Event ID 4728 (User added to admin group)

Example 3: Persistence via Services

Indicators

Event ID 7045 (New service installed)

Example 4: Log Tampering

Indicators

Event ID 1102 (Security log cleared)

🧰 Tools for Windows Log Forensics
Native Tools

Event Viewer

wevtutil

PowerShell

SIEM

Splunk

Microsoft Sentinel

Elastic Stack

DFIR Tools

Autopsy

FTK

Velociraptor

KAPE

🧠 SOC & Incident Response Value

Windows log forensics helps in:

Incident reconstruction

Threat actor tracking

Timeline building

Malware behavior analysis

Legal evidence collection

If you want, I can:

✅ Create a full GitHub repo structure
✅ Add Splunk + KQL queries
✅ Add real attack labs
✅ Add Windows Event ID cheat sheet
✅ Add SOC playbooks

Tell me what you want, and I’ll build it for you 🔥
