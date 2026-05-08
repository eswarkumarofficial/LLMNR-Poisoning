#

## 📌 Overview
This project demonstrates an **LLMNR Poisoning attack** performed in a **controlled and isolated lab environment**.  
It showcases how attackers capture credentials and use them for further exploitation.

---

## ⚠️ Disclaimer
This project is created strictly for **educational purposes** in an **isolated lab environment**.  

---

## 🧪 Lab Environment
- **Attacker Machine:** Kali Linux  
- **Victim Machine:** Windows 10  
- **Domain Controller (Optional):** Windows Server  

---

## 🛠️ Tools Used
- **Responder** → LLMNR/NBT-NS poisoning & hash capture  
- **Wireshark** → Network traffic analysis  
- **Hashcat** → Password cracking  
- **PsExec** → Lateral movement  

---

## 📡 What is LLMNR?
LLMNR (Link-Local Multicast Name Resolution) is used by Windows systems to resolve hostnames when DNS fails.

---

## ⚡ Attack Concept
1. Victim tries to access a non-existent share (e.g., `\\fileserver`)  
2. DNS fails → system sends LLMNR request  
3. Attacker responds as a fake server  
4. Victim sends NTLM hash  
5. Attacker captures the hash and crack
6. Now attacker uses captured credentials for further exploitation

---

## 📊 Logs & Analysis
All logs included in this repository are captured from the lab environment  


