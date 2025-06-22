# Firewall-and-IDS
The role of Firewall and IDS in modern Network Security

Overview
This project demonstrates practical implementation of:

Firewall & IDS (Snort) setup on Kali Linux

Common Web Vulnerabilities using DVWA:

SQL Injection

Reflected Cross-Site Scripting (XSS)

Stored Cross-Site Scripting (XSS)

 Tools Used
Kali Linux (Running inside VirtualBox/VM)

DVWA (Damn Vulnerable Web Application)

Snort IDS (Snort++)

UFW Firewall

MySQL / Apache2

Browser (Firefox/Chromium)

 🔥 1. Firewall & IDS Setup
✅ UFW (Firewall) Setup
sudo apt install ufw
sudo ufw enable
sudo ufw default deny incoming
sudo ufw allow 22/tcp     # Allow SSH
sudo ufw status verbose
🔒 Result: Only essential traffic allowed — rest blocked by default.

🛡️ Snort IDS (Snort++) Setup
Installation:
sudo apt install snort
Check Version:
snort -V
Create Custom Rule (ICMP Detection):
echo 'alert icmp any any -> any any (msg:"ICMP Packet Detected"; sid:1000001; rev:1;)' | sudo tee -a /etc/snort/rules/local.rules
Run Snort
sudo snort -q -c /etc/snort/snort.conf -i eth0
Test with:
ping 127.0.0.1
🧠 Snort successfully detected and logged ICMP packet alerts based on the custom rule.


