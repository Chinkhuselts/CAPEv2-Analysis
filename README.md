# WannaCry Malware Analysis using CAPEv2

This repository presents a dynamic malware analysis of the **WannaCry ransomware** utilizing the **CAPEv2** automated malware analysis system. The malware was executed within a controlled Windows 10 virtual environment to safely observe its execution chain, system interactions, and to identify key Indicators of Compromise (IOCs).

## 🎯 Objective
* Execute the WannaCry sample in a secure, isolated virtualized environment.
* Dynamically observe and log system behavior, including file system changes and process execution.
* Extract key behavioral indicators and IOCs for threat intelligence.

## 🛠️ Tools Used
* **CAPEv2 Sandbox:** Core analysis engine (hosted on Ubuntu 22.04).
* **Windows 10 Virtual Machine:** Target environment configured with the CAPE agent.
* **CAPEv2 Web Interface:** Used for submitting samples and reviewing analysis reports.

## ⚙️ Environment Setup
* **Host Machine:** Ubuntu 24.02
* CAPEv2 repository cloned and configured with necessary Python dependencies.
* Windows 10 VM connected via NAT, utilizing the CAPE guest agent for instrumentation.

For comprehensive configuration and deployment instructions, please refer to the setup documentation: [SETUP.md](SETUP.md).

## 🔄 Analysis Process
The execution and analysis process was recorded. Click the thumbnail below to watch the demonstration:

[![WannaCry Analysis Video](/report/thumbnail.png)](https://youtu.be/LHIFQqk9zLk)

## 📥 Input Sample
![Sample Import](/report/import-sample.png)

## 📊 Analysis Reports
![Analysis Result 1](/report/result1.png)
![Analysis Result 2](/report/Result2.png)

## 🔍 Extracted Indicators of Compromise (IOCs)
A detailed summary of the findings can be found in `IOCs/IOC-summary.txt`, which includes:
* Modified and created registry keys.
* Specific file paths created by the ransomware.
* Dropped secondary payloads.
* Suspicious spawned processes and execution trees.

> **Note:** No external network traffic capture tools (e.g., Wireshark) were utilized during this specific execution. All behavioral logging and network monitoring were recorded solely through CAPEv2's built-in hooking and logging mechanisms.

---

## 📬 Contact
For feedback, inquiries, or professional opportunities, please reach out via email at **husele1000@gmail.com**.
