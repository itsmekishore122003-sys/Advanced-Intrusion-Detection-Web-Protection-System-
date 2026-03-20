SentinelShield – Beginner Step-by-Step Guide

1. Introduction (What are we doing?)
In this project, you will act like a security tester (ethical hacker).
- Use a vulnerable website to test attacks
- Perform attacks like SQL Injection, XSS, Command Injection, Brute Force
- Collect logs from the server
- Analyze them to detect attacks

Think of it like this:
- Kali Linux = Attacker machine
- DVWA (on Metasploitable) = Victim website
- Splunk = Security monitoring tool

2. Why do we need these tools?
- DVWA: A purposely insecure website for safe hacking practice
- Kali Linux: Contains attacker tools
- Hydra: Tries many passwords automatically
- Apache Logs: Records every request to the website
- Splunk: Converts logs into graphs to detect suspicious activity

3. Installation (Simple Version)
- Install VirtualBox
- Install Kali Linux VM
- Install Metasploitable 2 VM (contains DVWA)
- Import both into VirtualBox

4. Connection
- Open VirtualBox → Settings → Network
- Set both Kali & Metasploitable to NAT Network or Host-Only Adapter
- Start both machines

5. Where to Access
- On Metasploitable:
  - username: msfadmin
  - password: msfadmin
  - Find IP: ifconfig
- On Kali Linux:
  - Open browser: http://<Metasploitable-IP>/dvwa
- Login to DVWA: username: admin, password: password
- DVWA Setup:
  - Setup/Reset Database → Create/Reset Database
  - DVWA Security → Set Security Level = Low

6. Perform Attacks in DVWA
A. SQL Injection
- Open SQL Injection page
- Enter: 1' OR '1'='1
- Result: All user data shown (Login bypass)

B. XSS
- Open XSS page
- Enter: <script>alert('XSS')</script>
- Result: Popup alert appears

C. Command Injection
- Open Command Injection page
- Enter: 127.0.0.1; ls
- Result: Server files displayed

7. Brute Force (Without Command)
- Open DVWA Login Page
- Try username: admin, multiple passwords manually
- Hydra automates this to find correct password

8. Where to Find Logs (Metasploitable)
- Go to terminal: cd /var/log/apache2
- View logs: cat access.log
- You will see IPs, login attempts, attack requests

9. Analyze Logs Using Splunk
- Open Splunk: http://localhost:8000
- Add Data → Upload access.log
- Set Source type: access_combined, Index: main
- Search for suspicious activity, e.g., repeated login attempts, script tags

Final Flow:
Kali (Attacker) → DVWA (Victim) → Apache Logs (Record Activity) → Splunk (Analyze Attacks)

Simple Understanding:
- DVWA → vulnerable website
- Kali → attacker
- Hydra → password guesser
- Apache logs → evidence
- Splunk → investigation tool

