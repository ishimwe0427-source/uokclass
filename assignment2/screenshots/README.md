# Assignment 2 — Screenshots for lecturer

**Student:** Ishimwe Jean Francois  
**Live site:** http://20.121.113.179/  
**VM:** cloud-uok (Ubuntu 24.04, Azure)

Save each screenshot **exactly** with the filename below, then push this folder to GitHub.

| # | Filename (use this exact name) | What to capture |
|---|--------------------------------|-----------------|
| 1 | `01 public private ip.png` | Azure Portal → **cloud-uok** → **Overview** (Status Running, Public **20.121.113.179**, Private **172.16.0.4**) |
| 2 | `02 ports azure nsg.png` | **Networking** → Inbound rules: SSH 22, HTTP 80, HTTPS 443 → **Allow** |
| 3 | `03 ports ufw.png` | SSH: output of `sudo ufw status` (22, 80, 443 ALLOW) |
| 4 | `04 disk dfh.png` | SSH: output of `df -h` |
| 5 | `05 network ipaddr.png` | SSH: output of `ip addr show eth0` (or `ip -4 addr show`) |
| 6 | `06 network route dns.png` | SSH: `ip route` and `cat /etc/resolv.conf` (one screenshot or two pasted in one image) |
| 7 | `07 website homepage.png` | Browser: **http://20.121.113.179/** (index.html) |
| 8 | `08 website assign2.png` | Browser: **http://20.121.113.179/assign2.html** |
