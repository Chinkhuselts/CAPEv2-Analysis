# WannaCry Malware Analysis using CAPEv2

This project presents a dynamic malware analysis of the WannaCry ransomware using the CAPEv2 sandbox. The malware was executed in a controlled Windows 10 virtual environment to safely observe its behavior and identify key indicators of compromise (IOCs).

## Objective
- Execute the WannaCry sample in a virtualized environment
- Observe and log system behavior
- Extract key behavioral indicators

## Tools Used
- CAPEv2 sandbox (hosted on Ubuntu 22.04)
- Windows 10 Virtual Machine (with CAPE agent)
- CAPEv2 web interface

## Environment Setup
- Host machine: Ubuntu 24.02
- CAPEv2 cloned and configured with Python dependencies
- Windows 10 VM connected via NAT with agent installed

See full instructions in [`setup`](SETUP.md)
## Input Sample
![sample](/report/import-sample.png)
## Analysis Reports
![1](/report/result1.png)
![2](/report/Result2.png)

## IOCs Extracted
See `IOCs/IOC-summary.txt` for:
- Modified registry keys
- File paths created
- Dropped payloads
- Any suspicious processes

If you want more details about installation and progress, check SETUP.md.
No external network traffic capture tools were used (e.g., Wireshark). Behavior was recorded through CAPEv2's built-in mechanisms.

---

If you have any feedback or are a recruiter interested in my skills, feel free to contact me at **husele1000@gmail.com**
