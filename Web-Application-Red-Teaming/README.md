# Web Application Red Teaming — Learning Notes & Progress

This folder contains my hands-on notes, custom exploit scripts, vulnerability chains, and room walkthroughs for the **Web Application Red Teaming** path on TryHackMe.

While standard penetration testing focuses on discovering individual vulnerabilities, Red Teaming is about thinking like an adversary—chaining minor flaws, creating custom tooling, bypassing modern defenses, and exploiting cutting-edge application architectures:
* **Cryptographic Attacks:** Breaking weak crypto implementations, padding oracles, length extension attacks, and ECB block manipulation.
* **Custom Tooling:** Writing tailored Python automation scripts, custom Burp Suite extensions, and browser automation to defeat anti-automation/CAPTCHA controls.
* **Vulnerability Chaining:** Combining low-impact issues (like SSRF, info disclosures, or cache poisoning) to achieve critical impact and Remote Code Execution (RCE).
* **WAF Evasion:** Analyzing Web Application Firewall rules, obfuscation, and protocol-level bypasses.
* **Attacking LLM Systems:** Exploring modern AI attack surfaces—prompt injection, model poisoning, indirect prompt injection, and insecure output handling.

---

## My Progress Tracker

### 1. [Cryptographic Failures](./01-Cryptographic-Failures/README.md)
* [ ] [Breaking Crypto the Simple Way](./01-Cryptographic-Failures/Breaking-Crypto-the-Simple-Way/README.md)
* [ ] [Length Extension Attacks](./01-Cryptographic-Failures/Length-Extension-Attacks/README.md)
* [ ] [Attacking ECB Oracles](./01-Cryptographic-Failures/Attacking-ECB-Oracles/README.md)
* [ ] [Padding Oracles](./01-Cryptographic-Failures/Padding-Oracles/README.md)
* [ ] [Insecure Randomness](./01-Cryptographic-Failures/Insecure-Randomness/README.md)

### 2. [Custom Tooling](./02-Custom-Tooling/README.md)
* [ ] [Custom Tooling Using Python](./02-Custom-Tooling/Custom-Tooling-Using-Python/README.md)
* [ ] [Custom Tooling Using Burp](./02-Custom-Tooling/Custom-Tooling-Using-Burp/README.md)
* [ ] [Tooling via Browser Automation](./02-Custom-Tooling/Tooling-via-Browser-Automation/README.md)
* [ ] [NoScope Finding RCE](./02-Custom-Tooling/NoScope-Finding-RCE/README.md)
* [ ] [CAPTCHApocalypse](./02-Custom-Tooling/CAPTCHApocalypse/README.md)

### 3. [Chaining Vulnerabilities](./03-Chaining-Vulnerabilities/README.md)
* [ ] [Chaining Vulnerabilities](./03-Chaining-Vulnerabilities/Chaining-Vulnerabilities/README.md)
* [ ] [Extract](./03-Chaining-Vulnerabilities/Extract/README.md)
* [ ] [Voyage](./03-Chaining-Vulnerabilities/Voyage/README.md)
* [ ] [Sequence](./03-Chaining-Vulnerabilities/Sequence/README.md)

### 4. [Bypassing WAF](./04-Bypassing-WAF/README.md)
* [ ] [WAF Introduction](./04-Bypassing-WAF/WAF-Introduction/README.md)
* [ ] [WAF Exploitation Techniques](./04-Bypassing-WAF/WAF-Exploitation-Techniques/README.md)
* [ ] [Padelify](./04-Bypassing-WAF/Padelify/README.md)
* [ ] [Farewell](./04-Bypassing-WAF/Farewell/README.md)

### 5. [Attacking LLMs](./05-Attacking-LLMs/README.md)
* [ ] [Input Manipulation and Prompt Injection](./05-Attacking-LLMs/Input-Manipulation-and-Prompt-Injection/README.md)
* [ ] [LLM Output Handling and Privacy Risks](./05-Attacking-LLMs/LLM-Output-Handling-and-Privacy-Risks/README.md)
* [ ] [Data Integrity and Model Poisoning](./05-Attacking-LLMs/Data-Integrity-and-Model-Poisoning/README.md)
* [ ] [Juicy](./05-Attacking-LLMs/Juicy/README.md)
* [ ] [BankGPT](./05-Attacking-LLMs/BankGPT/README.md)
* [ ] [HealthGPT](./05-Attacking-LLMs/HealthGPT/README.md)

---

[Back to main portfolio](../README.md)
