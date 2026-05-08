LLMNR Poisoning Lab Simulation

 ⚠️ Disclaimer
This project is created strictly for educational purposes in an isolated lab environment.


📌 Overview
This project demonstrates an LLMNR Poisoning attack performed in a controlled and isolated lab environment. It showcases how attackers capture credentials and use them for further exploitation.


🧪 Lab Environment

Attacker Machine: Kali Linux
Victim Machine: Windows 10
Domain Controller (Optional): Windows Server


🛠️ Tools Used

Responder → LLMNR/NBT-NS poisoning & hash capture
Wireshark → Network traffic analysis
Hashcat → Password cracking
PsExec → Lateral movement


📡 What is LLMNR?
LLMNR (Link-Local Multicast Name Resolution) is used by Windows systems to resolve hostnames when DNS fails.

⚡ Attack Concept

Victim tries to access a non-existent share (e.g., \\fileserver)
DNS fails → system sends LLMNR request
Attacker responds as the fake server
Victim sends NTLM hash
Attacker captures the hash


🚀 Attack Flow
1️⃣ Reconnaissance

Monitor network traffic
Identify active hosts

2️⃣ Initial Access (LLMNR Poisoning)

Run Responder on attacker machine
Listen for LLMNR/NBT-NS requests
Poison responses to impersonate server

3️⃣ Credential Capture

Victim attempts authentication
NTLMv2 hash is captured

4️⃣ Hash Cracking

Use Hashcat
Convert hash → plaintext password

5️⃣ Valid Credentials

Extract:

Username
Domain
Password



6️⃣ Lateral Movement

Access victim system using credentials
Tool used: PsExec

7️⃣ Execution

Execute commands on target machine
Gain elevated/system-level access

8️⃣ Persistence

Create new accounts or scheduled tasks
Maintain long-term access


📊 Logs & Analysis
All logs attached in this repository are Captured from the lab environment.


