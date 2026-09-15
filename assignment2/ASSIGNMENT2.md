# Assignment 2 — Linux VM Configuration

**Student:** Ishimwe Jean Francois  
**VM Name:** cloud-uok (Azure)  
**OS:** Ubuntu 24.04 LTS  

---

## 1. IP Addresses — Public and Private

| Type | Address |
|------|---------|
| **Public IP** | 20.121.113.179 |
| **Private IP** | 172.16.0.4 |

**Evidence:** Azure Portal → VM **cloud-uok** → Overview (screenshot).

**Verify on VM (SSH):**
```bash
curl -s ifconfig.me && echo
ip -4 addr show
```

---

## 2. Three Port Configuration

| Port | Protocol | Purpose |
|------|----------|---------|
| 22 | TCP | SSH |
| 80 | TCP | HTTP (website) |
| 443 | TCP | HTTPS |

**Azure:** VM → **Networking** → Inbound port rules (22, 80, 443).

**Ubuntu UFW (on VM):**
```bash
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable
sudo ufw status
```

**Evidence:** Screenshot of Azure inbound rules showing **HTTP 80, HTTPS 443, SSH 22** (Allow) + `sudo ufw status` on VM.

---

## 3. Disk Size

| Item | Value |
|------|-------|
| OS disk | 127 GiB (Azure) |

**Verify on VM:**
```bash
df -h
lsblk
```

**Evidence:** Screenshot of `df -h` output.

---

## 4. Network Configuration

| Setting | Value |
|---------|-------|
| Virtual network | cloud-uok-vnet / default |
| Private IP | 172.16.0.4 |
| Public IP | 20.121.113.179 |
| Region | East US |

**Verify on VM:**
```bash
ip addr
ip route
resolvectl status
```

**Evidence:** Screenshots of the above commands.

---

## 5. One Linux VM

| Setting | Value |
|---------|-------|
| VM Name | cloud-uok |
| OS | Ubuntu 24.04 LTS (64-bit) |
| Size | Standard D2s v3 (2 vCPU, 8 GiB RAM) |
| Web server | Nginx |
| Homepage | `index.html` / `assign2.html` |

**Evidence:** Azure VM Overview + `nginx -v` + browser showing homepage.

---

## Website test (class method)

On VM:
```bash
curl http://localhost/index.html
curl http://localhost/assign2.html
```

From your PC browser:
```
http://20.121.113.179/
```

---

## Screenshots to submit (checklist)

- [ ] Azure VM running (Overview)
- [ ] Public + Private IP
- [ ] Networking ports 22, 80, 443
- [ ] `sudo ufw status`
- [ ] `df -h`
- [ ] `ip addr` / `ip route`
- [ ] Nginx welcome OR your homepage in browser
- [ ] `curl localhost` showing your HTML
