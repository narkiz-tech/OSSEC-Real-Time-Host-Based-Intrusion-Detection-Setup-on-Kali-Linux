# 🛡️ OSSEC Real-Time Host-Based Intrusion Detection (HIDS) Lab

**Setup, Monitoring, Alerting & Active Response on Kali Linux**

---

## 📌 Overview

This project demonstrates the **complete setup, configuration, and testing of OSSEC (Open Source Security Event Correlator)** as a **Host-Based Intrusion Detection System (HIDS)** in a controlled lab environment.

The lab focuses on **real-time log monitoring, security alert generation, and active response**, simulating how a **Security Operations Center (SOC)** analyst would detect and investigate suspicious activity on a Linux host.

The purpose of this project is to showcase:

* Hands-on defensive security skills
* Log analysis and alert validation
* Understanding of host-based threat detection
* SOC-style investigation and response thinking

> ⚠️ **Disclaimer:**
> This project was conducted strictly in an isolated virtual lab environment for educational and defensive security purposes only.

---

## 🔧 Lab Environment

* **Operating System:** Kali Linux (Virtual Machine)
* **Security Tool:** OSSEC HIDS
* **Virtualisation:** Oracle VirtualBox
* **Terminal Prompt Used:**

  ```bash
  (narkis㉿kali)-[~]
  ```

---

## 🎯 Project Objectives

* Install and configure **OSSEC HIDS** from source
* Monitor Linux system and authentication logs in real time
* Detect suspicious activity such as authentication failures and privilege abuse
* Generate and analyse OSSEC security alerts
* Test **active response** capabilities
* Simulate SOC-style alert investigation and validation

---

## 📂 Project Structure

```text
OSSEC-Real-Time-HIDS/
│
├── README.md                 # Project documentation
├── logs/                     # Sample OSSEC alerts and system logs
├── screenshots/              # Terminal output and alert screenshots
│
├── config/
│   └── ossec.conf            # OSSEC main configuration file
│
├── rules/
│   └── local_rules.xml       # Custom OSSEC rules
│
└── notes/
    └── investigation-notes.md
```

---

## 🛠️ Installation & Setup

### 1️⃣ System Preparation

The system was first updated and required dependencies installed:

```bash
sudo apt update
sudo apt install curl gcc make libevent-dev zlib1g-dev libpcre2-dev libssl-dev -y
```

---

### 2️⃣ OSSEC Installation

OSSEC was installed directly from the official source package:

```bash
curl -O https://github.com/ossec/ossec-hids/archive/3.7.0.tar.gz
tar -xvzf 3.7.0.tar.gz
cd ossec-hids-3.7.0
sudo ./install.sh
```

During installation:

* Local (standalone) OSSEC installation was selected
* Default directories were used
* System integrity checking and rootkit detection were enabled

---

### 3️⃣ Verifying Installation

After installation, OSSEC services were verified:

```bash
sudo /var/ossec/bin/ossec-control start
sudo /var/ossec/bin/ossec-control status
```

Successful service startup confirmed OSSEC was actively monitoring the host.

---

## 🔍 Log Monitoring & Detection

OSSEC continuously monitors multiple log sources, including:

* `/var/log/auth.log`
* `/var/log/syslog`
* System command execution logs

### Example monitored events:

* Failed SSH login attempts
* Successful logins after repeated failures
* Privilege escalation using `sudo`
* Suspicious system activity

---

## 🚨 Alert Generation & Analysis

### Simulated Attack Scenarios

The following scenarios were manually triggered to test OSSEC detection:

### 🔹 Scenario 1: SSH Brute Force Attempt

* Multiple failed SSH login attempts were generated
* OSSEC detected repeated authentication failures
* Alert severity increased after threshold exceeded

### 🔹 Scenario 2: Suspicious Privilege Escalation

* Unauthorized `sudo` command execution simulated
* OSSEC generated alerts for abnormal privilege use

---

### Sample Alert Output

Alerts were generated in OSSEC logs and reviewed for:

* Timestamp accuracy
* Source user/IP
* Rule ID and severity level

Sample alert logs are stored in the `logs/` directory.

---

## ⚙️ Active Response Testing

OSSEC active response functionality was enabled to demonstrate automated defensive actions.

### Tested response actions:

* Temporary IP blocking after repeated authentication failures
* Alert escalation for high-risk events

This demonstrates how OSSEC can be used not only for detection, but also for **basic automated containment**.

---

## 🧠 Investigation Approach (SOC Perspective)

For each alert, the following investigation steps were applied:

1. Review OSSEC alert details (rule ID, level, source)
2. Correlate alert with raw system logs
3. Validate whether activity was benign or malicious
4. Document findings and response actions
5. Recommend mitigation strategies

This mirrors a **Tier 1 SOC analyst workflow**.

---

## 📘 What I Learned

* How host-based intrusion detection works at the OS level
* How to configure and validate OSSEC rules
* How security alerts are generated and escalated
* Importance of log correlation and context
* How active response can reduce attack impact
* How SOC analysts triage and investigate host alerts

---

## 📸 Screenshots & Evidence

Screenshots demonstrating:

* OSSEC installation
* Alert generation
* Log correlation
* Active response testing

are included in the `screenshots/` directory.

---

## 🔐 Security Relevance

This project demonstrates **real-world defensive security fundamentals**, including:

* Host monitoring
* Log analysis
* Intrusion detection
* Alert triage
* Incident response thinking

These skills are directly relevant to **Junior SOC Analyst**, **Cybersecurity Graduate**, and **Security Operations** roles.

---

## 🚀 Future Improvements

* Forward OSSEC alerts to a SIEM (Splunk / ELK)
* Expand custom detection rules
* Map alerts to **MITRE ATT&CK** techniques
* Simulate additional attack scenarios

---

### ✅ Why this project matters

This repository shows **practical security monitoring**, not just theory.
It demonstrates how security tools are deployed, tested, and analysed in a SOC-style environment.



