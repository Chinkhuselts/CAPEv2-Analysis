# CAPEv2 Sandbox Setup (Ubuntu Host + Windows VM)

This guide outlines how I set up the CAPEv2 malware analysis environment on Ubuntu 22.04 using a Windows 10 virtual machine for sandbox execution.

---

## Host System

- **OS**: Ubuntu 22.04 LTS
- **Hypervisor**: Virtualbox
---

## Installing CAPEv2

### 1. Clone the CAPEv2 Repository

```bash
git clone https://github.com/kevoreilly/CAPEv2.git
cd CAPEv2
```
## 2. Run Installation Script

CAPEv2 includes a semi-automated setup script, which located in installer directory.
```
sudo ./install.sh
```
Follow the prompts and ensure all dependencies are installed.
Tip: If install.sh fails, install missing packages manually (e.g., MongoDB, PostgreSQL, tshark).

## Setting Up the Windows 10 VM
1. Create and Configure the VM
```
    Install a clean copy of Windows 10 (x86).
```
 Disable Windows Defender, Firewall, and auto-updates. If cuckoo doesn't correctly analyze sample, just delete Windows Defender.  
    Set VM to use Host-only networking.

2. Install Agent on Windows VM

    Inside the VM, download the CAPE agent:
    Found in CAPEv2/agent/ on the host.

    Copy it to the VM (via shared folder or ISO).
    Run the agent and set it to auto-start (use Task Scheduler). Also, you can manually activate agent.py.

## Test the Setup

Start CAPEv2 on the host:
```
sudo python3 cuckoo.py
```
Insert your sample:
python3 /opt/CAPEv2/utils/submit.py <sample>
    You can also add your Sample by web interface, submti section.
    Access the CAPEv2 web interface:
```
python3 manage.py runserver (you check -h for other options)
http://localhost:8000/
```
 Upload a benign executable to test your VM connectivity and analysis workflow.

## Storage Tips

Assign a shared folder for log exports (optional).

Take a snapshot of the VM before running malware.

## Debug Tips
    
   It was difficult to integrate it with Ubuntu 24.02. To debug:

   1. Check journalctl -xe for error logs of process
   2. Sometimes, Report cannot be displayed by CAPEv2 web interface. So use process.py for debug (-d), regenerate report (-r) to create report.
   3. Mongodb integration is crucial.
   4. Always check .conf files
   5. Please check config directory for integration of CAPEv2 

NEVER connect the VM to the internet while analyzing real malware.

