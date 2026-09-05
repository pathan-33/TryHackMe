# [Medium Title] How I Cracked [Room Name] on TryHackMe: A Step-by-Step Walkthrough

> *Subtitle: Deep dive into [Vulnerability / Technique], initial foothold, and root privilege escalation.*

*(Insert a catchy banner / room image here)*

---

### 📌 Introduction
Welcome to this walkthrough of the **[Room Name]** machine on TryHackMe. In this room, we will explore:
* **Initial Access:** Exploiting [e.g., Command Injection / Insecure Direct Object Reference]
* **Privilege Escalation:** Abusing [e.g., misconfigured cronjob / SUID binary]
* **Difficulty:** [Easy / Medium / Hard]
* **Room Link:** [[Room Name] on TryHackMe](https://tryhackme.com)

---

### 🔍 Phase 1: Reconnaissance & Port Scanning
Every penetration test begins with thorough reconnaissance. Let’s fire up `nmap`:

```bash
nmap -sC -sV -oN scan.txt <TARGET_IP>
```

*(Explain the scan results and why certain ports caught your attention)*

---

### 🕵️ Phase 2: Enumeration & Web Discovery
Next, we dive deeper into the web application running on port 80.

```bash
gobuster dir -u http://<TARGET_IP> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

*(Insert screenshot or explanation of the interesting endpoints found)*

---

### 💥 Phase 3: Exploitation & Initial Foothold
Here is where we exploit the vulnerability:
1. **The Flaw:** Explain *why* the vulnerability exists in simple terms.
2. **The Payload:** Show the request or script used.
3. **Catching the Reverse Shell:**

```bash
nc -lvnp 4444
```

*(Include terminal screenshot demonstrating the interactive shell)*

---

### ⚡ Phase 4: Privilege Escalation to Root
With our low-privilege user shell, we look for misconfigurations:

```bash
sudo -l
```

*(Explain how you escalated privileges to root)*

---

### 🛡️ How to Fix It (Remediation)
In a production environment, this vulnerability could be prevented by:
1. **Input Validation:** Sanitize user input before passing it to system calls.
2. **Principle of Least Privilege:** Avoid giving users excessive `sudo` privileges without password verification.

---

### 🎯 Conclusion & Connect
Thanks for reading! If you found this breakdown helpful, please consider leaving a few claps 👏 and following for more cybersecurity walkthroughs.

* 🐙 **GitHub Repository:** [My TryHackMe Journey](https://github.com/)
* 💼 **LinkedIn:** [Connect with me on LinkedIn](https://linkedin.com/)
