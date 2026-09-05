# 📝 TryHackMe Room: [Room Name]

* **Room Link:** [https://tryhackme.com/r/room/ROOM_SLUG](https://tryhackme.com)
* **Difficulty:** [Easy / Medium / Hard / Insane]
* **Category:** [Web / Network / Linux / Windows / Forensics / Active Directory]
* **Key Skills:** `Nmap`, `Gobuster`, `Privilege Escalation`, `SQLi`, etc.
* **Date Completed:** YYYY-MM-DD

---

## 🎯 Executive Summary / Overview
A short 2-3 sentence overview of the machine and the attack path:
* **Initial Access:** [e.g., Unauthenticated file upload leading to reverse shell]
* **Privilege Escalation:** [e.g., SUID binary / sudo misconfiguration]

---

## 1. 🔍 Reconnaissance & Scanning

### Nmap Scan
```bash
nmap -sC -sV -oN nmap_scan.txt <TARGET_IP>
```

**Open Ports & Services:**
* `Port 22/tcp` - SSH (OpenSSH x.x)
* `Port 80/tcp` - HTTP (Apache / Nginx x.x)

---

## 2. 🌐 Enumeration

### Web Enumeration / Directory Busting
```bash
gobuster dir -u http://<TARGET_IP> -w /usr/share/wordlists/dirb/common.txt -t 30
```

*Findings:*
* `/admin` - Found login portal
* `/uploads` - Directory listing enabled

---

## 3. 💥 Exploitation (Initial Access)

### Vulnerability Analysis
Explain the vulnerability found, payload used, and step-by-step reproduction.

```bash
# Example payload / command
nc -lvnp 4444
```

*Shell Obtained as:* `www-data`

---

## 4. 📈 Privilege Escalation

### Internal Enumeration
```bash
sudo -l
# or linpeas.sh
```

### Root Exploitation
Explain how root / admin privileges were obtained.

---

## 🚩 Flags
* **User Flag (`user.txt`):** `THM{u53r_fl4g_********}`
* **Root Flag (`root.txt`):** `THM{r00t_fl4g_********}`

---

## 💡 Lessons Learned & Key Takeaways
1. What was the main takeaway from this room?
2. How to patch/remediate these vulnerabilities in a real-world setting?
