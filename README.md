**LLMNR Poisoning Lab Simulation**

Educational LLMNR Poisoning lab simulation conducted in an isolated environment, with attached logs and analysis to demonstrate credential capture, attack flow, and SOC detection techniques.


**Lab Environment Setup:** The attack is performed in an isolated lab with the following machines

Attacker Machine: Kali Linux
Victim Machine: Windows 10
Domain Controller (optional): Windows Server


**Tools Used**
Responder → Captures hashes via LLMNR/NBT-NS poisoning
Wireshark → Packet capture and traffic analysis
Hashcat → Password cracking
PsExec → Lateral movement


LLMNR is a protocol used by Windows systems to resolve hostnames when DNS fails.

**Attack Concept:**
Victim tries to access a non-existing share (e.g., \\fileserver)
DNS fails → system sends LLMNR broadcast
Attacker responds pretending to be the server
Victim sends NTLM hash → attacker captures it


**Attack Flow -**
1️⃣ Reconnaissance
Monitor network traffic

2️⃣ Initial Access (LLMNR Poisoning)
Run Responder on attacker machine
Listen for LLMNR/NBT-NS requests
Poison responses to impersonate server

3️⃣ Credential Capture
Victim attempts authentication
NTLMv2 hash is captured by Responder

4️⃣ Hash Cracking
Use tools like Hashcat
Convert captured hash into plaintext password

5️⃣ Valid Credentials
Extract: Username, Domain, Password

6️⃣ Lateral Movement
Use cracked credentials to access victim system
Tools:PsExec

7️⃣ Execution
Execute commands on victim machine
Gain SYSTEM-level access

8️⃣ Persistence
Create new accounts or scheduled tasks to maintain access for future sessions


