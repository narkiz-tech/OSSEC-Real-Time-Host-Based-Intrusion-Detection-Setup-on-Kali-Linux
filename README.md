# OSSEC-Real-Time-Host-Based-Intrusion-Detection-Setup-on-Kali-Linux
This project demonstrates the full setup and testing of **OSSEC (Open Source Security Event Correlator)** on a Kali Linux virtual machine. It includes installation, configuration, real-time log monitoring, alert generation, and testing active responses.

---

## 🔧 Environment

- **Operating System:** Kali Linux (Virtual Machine)
- **Tool:** [OSSEC HIDS](https://www.ossec.net/)
- **Tested in:** Oracle VirtualBox
- **Terminal Prompt:** `(narkis㉿kali)-[~]`

---

## 📦 Project Structure

| Folder/File                   | Description                                      |
|-------------------------------|--------------------------------------------------|
| `/etc/ossec.conf`             | OSSEC main configuration file 
| `/var/ossec/rules/`           | Custom and active rule files  
| `screenshots/`                | Terminal session images  
| `logs/`                       | Captured alerts and sample logs
| `README.md`                   | Project documentation and steps summary          

---

## 🛠️ Installation Steps

```bash
sudo apt update
sudo apt install curl gcc make libevent-dev zlib1g-dev libpcre2-dev libssl-dev -y
curl -O https://github.com/ossec/ossec-hids/archive/3.7.0.tar.gz
tar -xvzf 3.7.0.tar.gz
cd ossec-hids-3.7.0
sudo ./install.sh
