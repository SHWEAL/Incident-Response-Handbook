# Incident-Response-Handbook
This repository contains a complete, safe, and controlled simulation of a phishing attack that delivers a mock ransomware payload. The goal of this project is to demonstrate how phishing leads to system compromise and how digital forensics and incident response teams investigate such incidents in a lab environment.

This project was implemented using GoPhish, MailHog, Python (PyInstaller), FTK Imager, and Volatility.

📌 Project Overview

The project demonstrates the full attack chain:

A phishing email is created using GoPhish

MailHog captures the email safely in a local environment

The victim downloads a mock ransomware payload

The payload simulates ransomware behavior without causing real damage

Disk and memory images are acquired for forensic analysis

Indicators of Compromise (IOCs) and persistence mechanisms are identified

The attack phases are mapped using MITRE ATT&CK and the Cyber Kill Chain

This project is purely educational and does not use or distribute real malware.

⚠️ Ethical & Legal Disclaimer

This simulation is for educational and research purposes only.
All testing must be done in an isolated lab environment.
No real ransomware samples are included or executed.
The payload used (ticket.exe) is a harmless mock executable designed to imitate ransomware behavior without encrypting or damaging files.

🧪 Technologies Used

GoPhish — Phishing framework

MailHog — Local SMTP server for safe email delivery

Python 3 + PyInstaller — Building the mock payload

FTK Imager — Disk & memory acquisition

Volatility 3 — Memory analysis

Registry tools — Persistence analysis

MITRE ATT&CK — Technique mapping

🚀 Simulation Steps

Start MailHog (SMTP 1025 / UI 8025)

Start GoPhish (Admin panel on port 3333)

Create a phishing email with a download link to ticket.exe

Host ticket.exe using Python HTTP server

Send the phishing campaign to test targets

Victim downloads and runs the mock payload

Payload displays a fake ransom message and renames demo files

Use FTK Imager to capture disk & memory images

Analyze memory using Volatility (processes, trees, modules)

Identify persistence keys and suspicious artifacts

🔍 Forensic Findings (Examples)

Suspicious processes found in memory:

@WannaCryDecryptor

tasksche.exe

Registry persistence entry:

HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\WanaCrypt0


Evidence collected via:

Disk image

Memory image

Registry hive extraction

Volatility process analysis

🧩 MITRE ATT&CK Mapping
Stage	Technique ID	Description
Initial Access	T1566.001	Phishing email with malicious link
Execution	T1204.002	User executed downloaded payload
Persistence	T1547.001	Registry Run key persistence
Defense Evasion	T1036.005	Masquerading with fake file names
Impact	T1486	Simulated ransomware impact
🛡 Recommendations

Conduct regular phishing-awareness training

Enable SPF, DKIM, and DMARC

Block executable attachments at the email gateway

Use EDR solutions with behavioral detection

Maintain offline backups

Segment networks for damage limitation

Centralize logging through a SIEM

Implement a formal Incident Response Plan

📝 Conclusion

This project successfully demonstrates the lifecycle of a modern cyber incident:

Phishing delivery

Execution of a malicious (mock) payload

Forensic acquisition

Evidence analysis

Incident response

Mapping attacker behavior

It provides hands-on experience for students and professionals learning about phishing, ransomware behavior, digital forensics, and incident response.
