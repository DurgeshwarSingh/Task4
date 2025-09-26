# Task4
About windows and ufw for Linux 

🛡️ Linux (UFW - Uncomplicated Firewall)

✅ Basic UFW Commands

[ ] Enable firewall: sudo ufw enable

[ ] Disable firewall: sudo ufw disable

[ ] Check status: sudo ufw status verbose

[ ] Reset all rules: sudo ufw reset


🔽 Inbound Rules (Incoming Traffic)

[ ] Allow SSH (port 22): sudo ufw allow 22/tcp

[ ] Allow HTTP (port 80): sudo ufw allow 80/tcp

[ ] Allow HTTPS (port 443): sudo ufw allow 443/tcp

[ ] Allow custom port (e.g., 8080): sudo ufw allow 8080/tcp

[ ] Deny all other inbound by default: sudo ufw default deny incoming


🔼 Outbound Rules (Outgoing Traffic)

[ ] Allow all outgoing by default: sudo ufw default allow outgoing

[ ] Restrict specific outbound port (example – block SMTP spam):
sudo ufw deny out 25/tcp

[ ] Allow only DNS & HTTPS outbound (example for servers):

sudo ufw default deny outgoing  
sudo ufw allow out 53  
sudo ufw allow out 443



🪟 Windows Firewall

✅ Basic Windows Firewall Management

[ ] Open Firewall settings: wf.msc

[ ] Check firewall profiles (Domain, Private, Public)

[ ] Export/Import rules:

Export: wf.msc → Action → Export Policy

Import: wf.msc → Action → Import Policy



🔽 Inbound Rules (Incoming Traffic)

[ ] Allow SSH (port 22):
New-NetFirewallRule -DisplayName "Allow SSH" -Direction Inbound -Protocol TCP -LocalPort 22 -Action Allow

[ ] Allow RDP (port 3389):
New-NetFirewallRule -DisplayName "Allow RDP" -Direction Inbound -Protocol TCP -LocalPort 3389 -Action Allow

[ ] Allow HTTP/HTTPS:

HTTP: port 80

HTTPS: port 443


[ ] Block all other inbound except required services.


🔼 Outbound Rules (Outgoing Traffic)

[ ] Allow all outbound by default.

[ ] Create restriction for sensitive apps:
Example – block app outbound:
New-NetFirewallRule -DisplayName "Block App" -Direction Outbound -Program "C:\path\to\app.exe" -Action Block

[ ] Block outbound on specific ports (e.g., SMTP spam port 25).


