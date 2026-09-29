# 🛡️ Offensive Security & Penetration Testing Portfolio

Welcome to my personal cybersecurity portfolio. This repository contains hands-on penetration testing write-ups, vulnerability research labs, privilege escalation proofs-of-concept, and security automation scripts. 

The lab environments demonstrate practical exploits, real-world compromise paths, and remediation recommendations.

---

## 📌 Featured Security Projects

### 🔴 Project 1: InfraBreak Lab 01 – Full Network & Application Compromise
* **Goal:** Achieve total root compromise of a distributed multi-container architecture.
* **Score:** 6000 / 6000 Points (Max Score)
* **Key Attack Vectors & Steps Executed:**
  1. **Reconnaissance & Service Enumeration:** Utilized `Nmap` to identify open vectors across FTP (21), SSH (22), MySQL (3306), PostgreSQL (5432), and HTTP (8088).
  2. **FTP Anonymous Exploitation:** Extracted password-protected backup archives (`db_backup_march.zip`).
  3. **Password Hash Cracking:** Extracted file hashes via `zip2john` and cracked archive passwords using `John the Ripper` with the `rockyou.txt` wordlist.
  4. **Database Analysis & Log Leakage:** Analyzed unzipped debug logs (`db_maintenance_2024_03.log`), retrieved hardcoded credentials, and executed an SSL-bypass connection into MySQL.
  5. **SSH Key Extraction & File Permissions:** Extracted an OpenSSH private key from internal database schemas, fixed key file permissions (`chmod 600`), and achieved authenticated SSH access.
  6. **PostgreSQL RCE (CVE-2019-9193):** Leveraged Superuser capabilities to execute arbitrary shell commands via `COPY FROM PROGRAM`.
  7. **Automated Root Escalation:** Pivoted using `Metasploit` modules and exploited misconfigured sudoers execution (`NOPASSWD` on `/bin/bash`) to gain complete system root control.

---

### 🔴 Project 2: Linux Privilege Escalation Lab (Jack Daniels Sandbox)
* **Goal:** Analyze an isolated container environment, audit system scripts, and escalate a low-privilege user (`daniels`) to absolute `Root`.
* **Key Attack Vectors & Steps Executed:**
  1. **Local Enumeration:** Identified globally writable (`777`) administrative scripts in `/home/jack/scripts/user_scripts`.
  2. **Cronjob Hijacking & Injection:** Discovered that `admin_script.sh` was invoked periodically via a root crontab task.
  3. **Persistence & SUID Backdoor:** Injected malicious code to append the user to the local `sudoers` matrix and staged a persistent SUID root bash binary (`/tmp/rootbash -p`).

---

### 🌐 Web Application & Offensive Security Labs
* **Broken Authentication & Session Management:** Practical exploitation of logic flaws, MFA bypasses, session hijacking, and password reset vulnerabilities.
* **Injection Attacks:** SQL Injection (SQLi) and Command Injection execution for unauthorized data exfiltration.
* **JWT (JSON Web Token) Exploitation:** Signatures verification bypasses, Algorithm Confusion (`None` / `HS256` key confusion), and weak signing secret cracking.
* **Anti-Automation Bypasses:** Circumvented rate-limiting, IP restrictions, and captchas through HTTP header manipulation and IP rotation simulation.

---

## 🛠️️ Technical Stack & Tools
* **Offensive Tools:** Burp Suite Professional/Community, Kali Linux, Metasploit Framework, Nmap, Wireshark, John the Ripper, Hydra.
* **Networking & Systems:** CCNA Routing & Switching, Active Directory (RBAC, Domain Controllers), Linux Systems (Ubuntu/Debian, Kali), Windows Server, TCP/IP.
* **Scripting & Automation:** Python (`Scapy`, `BeautifulSoup`, Socket programming, Log Processors), Bash Scripting, SQL (`MySQL`, `PostgreSQL`).

---

## 📄 Full Documentation & Portfolio File
You can find the complete detailed PDF report inside this repository:
📁 [`Ohad Cohen's CyberSecurity Portfolio.pdf`](./Ohad%20Cohen's%20CyberSecurity%20Portfolio.pdf)

---

📬 **Contact Information:**
* **Name:** Ohad Cohen
* **Email:** Ohad6cohen@gmail.com
* **LinkedIn:** [Ohad Cohen](https://linkedin.com/in/ohad-cohen)
