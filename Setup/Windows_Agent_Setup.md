# 🖥 Windows Wazuh Agent Setup – Lab Execution Log

This document records the exact steps I followed to install and configure the **Wazuh Agent** on my Windows 10 machine for integration with the Wazuh Manager.

---

## 1️⃣ Environment
- **Windows 10 Pro** (VM Machine)
- **Manager IP**: `192.168.X.217`
- **Agent IP**: `192.168.X.35`
- **Agent Auth Key**: Generated from Wazuh Manager

---

## 2️⃣ Download & Install Agent
1. Downloaded **Wazuh Agent installer** from the official Wazuh website:  
   [https://wazuh.com/downloads](https://wazuh.com/downloads)
2. Launched installer as Administrator.
3. During setup:
   - Entered **Manager IP**: `192.168.X.217`
   - Entered **Authentication Key** (from Ubuntu Manager)
4. Completed installation.

**Proof Screenshot:**  
![Agent Install Wizard](../proof/agent_install.png)

---

## 3️⃣ Configure File Integrity Monitoring (FIM)
1. Navigated to:
```
C:\Program Files (x86)\ossec-agent\ossec.conf
```

2. Add the following entry inside the Directory block::
```
<directories realtime="yes">Your_Desired_Directory's_path</directories>
```

3. Saved file.

Proof Screenshot:

---

4️⃣ Restart Wazuh Agent Service
Opened Services.msc

Restarted Wazuh Agent service

Proof Screenshot:

---

5️⃣ Verification in Wazuh Dashboard
Navigated to Wazuh Dashboard → Agents

Verified Windows Agent status = Active

Performed test:

Created a file in C:\Wazuh_Test

Deleted the file

Confirmed both events were captured in dashboard logs.

Proof Screenshot:

---

✅ Status
Windows Agent installed and connected to Manager

File Integrity Monitoring configured and verified

Successfully sending logs and events to Wazuh Manager