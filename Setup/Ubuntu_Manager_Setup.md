# 🛠 Ubuntu Wazuh Manager Setup – Lab Execution Log

This document is my **hands-on record** of installing and configuring the Wazuh Manager in my SOC Analyst home lab.  
It contains the exact commands, terminal outputs, and proof screenshots from my setup process.

---

## 1️⃣ Environment
- **Ubuntu Server**: 22.04 LTS (VirtualBox VM)
- **Network Mode**: Bridged Adapter
- **VM IP**: `192.168.X.217`

---

## 2️⃣ Commands Run

```bash
# Switch to the root user
sudo su

# Update system
sudo apt update && sudo apt upgrade -y

# Add Wazuh key
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -

# Install Java dependency
apt install default-jdk -y

# Download the Wazuh installation assistant
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh

# Run the all-in-one installer
bash wazuh-install.sh -a

#After installation is complete there is username and password Save the Login Password for login
Proof Screenshot:

---

## 3️⃣  Accessing Dashboard
Open: https://192.168.X.217

Logged in with default credentials shown during installation.
Proof Screenshot:

---

## 4️⃣ Registering Windows Agent
```
sudo /var/ossec/bin/manage_agents
```
Added agent → copied generated authentication key.

Saved key for Windows Agent setup.

Proof Screenshot:

---

✅ Status
Wazuh Manager fully installed

Accessible from host machine

Ready to receive logs from Windows Agent