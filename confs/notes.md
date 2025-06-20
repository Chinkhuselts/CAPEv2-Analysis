# Configuration Files Overview

This folder holds configuration files used during the WannaCry malware analysis with CAPEv2. These overrides tailor default behavior to ensure reliable and safe execution.

---

## 🧩 Files

### `auxiliary.conf`  
Controls additional analysis modules (e.g., network sniffing, snapshots).  
You might enable or disable modules like `sniffer`, `mitm`, or `replay` :contentReference[oaicite:1]{index=1}.

### `cuckoo.conf`  
Main configuration: defines general behavior, result server settings, database, and machinery type.  
Key settings include `[cuckoo] machinery`, `[resultserver] ip/port`, and `[database] connection` :contentReference[oaicite:2]{index=2}.

### `reporting.conf`  
Manages report formats (JSON, HTML, PDF, etc.).  
Used to enable or disable output formats after analysis :contentReference[oaicite:3]{index=3}.

### `virtualbox.conf`  
Specifies VirtualBox VM settings: mode (`gui`, `headless`), VBoxManage path, VM labels, IP addresses, snapshots, and network interfaces :contentReference[oaicite:4]{index=4}.

### `web.conf`  
Configures the CAPEv2 web interface: UI behavior, authentication, rate limits, and API settings :contentReference[oaicite:5]{index=5}.

---

## 📌 Notes

- These files override defaults under `conf/`, so your changes are preserved through updates :contentReference[oaicite:6]{index=6}.
- Use environment variables (e.g., `%(ENV:VAR)s`) to manage secrets, keys, and endpoints :contentReference[oaicite:7]{index=7}.
- Confirm IPs, ports, and interfaces are correct for your environment before running malware.

