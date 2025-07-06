# RickdiculouslyEasy: 1 - VulnHub CTF Report 📜

---

## 📌 Target Information

- **Machine Name:** RickdiculouslyEasy: 1  
- **Author:** Luke Childs  
- **Platform:** VulnHub (VirtualBox)  
- **OS:** Fedora (Apache/2.4.27, vsFTPd 3.0.3)

---

## 🎯 Objective

Capture all hidden flags across exposed services and gain user access.  
Total expected points: **50**

---

## 🛠️ Tools Used

- `nmap`
- `ftp`
- `gobuster`
- `nc` (netcat)
- `hydra`
- `ssh`
- Linux basic commands (`cat`, `ls`, `more`)

---

## 📡 Service Enumeration

| Port  | Service                | Status                  |
|:------|:----------------------|:------------------------|
| 21    | FTP (vsFTPd 3.0.3)     | Anonymous login enabled  |
| 22    | SSH                    | Open (unused)            |
| 80    | HTTP (Apache/2.4.27)   | Open                     |
| 9090  | Cockpit Web Panel      | Open                     |
| 13337 | Custom Netcat Service  | Open                     |
| 22222 | SSH (OpenSSH 7.5)      | SSH brute-force target   |
| 60000 | Custom Netcat Service  | Open                     |

---

## 📜 Flags Captured

| Location                     | Flag                                          | Points |
|:-----------------------------|:-----------------------------------------------|:--------|
| FTP root dir (FLAG.txt)       | `FLAG{Whoa this is unexpected}`                 | 10     |
| /passwords/FLAG.txt (HTTP)    | `FLAG{Yeah d- just don't do it.}`               | 10     |
| Cockpit Panel (Port 9090)     | `FLAG{There is no Zeus, in your face!}`         | 10     |
| Netcat Service (Port 13337)   | `FLAG:{TheyFoundMyBackDoorMorty}`               | 10     |
| Netcat Service (Port 60000)   | `FLAG{Flip the pickle Morty!}`                  | 10     |

**Total Points:** 50  

---

## 🔓 Exploitation Summary

- **FTP (Port 21):** Anonymous login → Retrieved flag  
- **HTTP (Port 80):**  
  - Gobuster discovered `/passwords/` directory and `/robots.txt`
  - Found hardcoded password `winter` in `passwords.html`
  - Flags retrieved from `/passwords/FLAG.txt`
- **Command Injection:**  
  - `/cgi-bin/tracertool.cgi` vulnerable to command injection  
  - Command used: `127.0.0.1; more /etc/passwd`  
  - Users enumerated: RickSanchez, Morty, Summer  
- **Cockpit Web Panel (Port 9090):** Flag directly accessible  
- **Netcat Service (Port 13337 & 60000):** Flags retrieved via netcat connections  
- **SSH Brute-force (Port 22222):**  
  - Hydra brute-forced using password `winter`  
  - Accessed Summer’s account  
  - Retrieved cat ASCII art flag

---

## 📊 Action Summary

| Action                          | Status            |
|:--------------------------------|:------------------|
| Service Enumeration             | ✅ Completed       |
| FTP Exploitation                | ✅ Flag captured   |
| Web Directory Enumeration       | ✅ Flag & password found |
| Command Injection Exploitation  | ✅ Users enumerated |
| Netcat Service Exploitation     | ✅ Flags captured   |
| SSH Brute-force                 | ✅ Access obtained  |
| Cockpit Panel Exploitation      | ✅ Flag captured   |
| Root Privilege Escalation       | ❌ Not attempted    |

---

## 📚 Conclusion

A solid beginner-friendly CTF covering:
- Service enumeration  
- FTP, HTTP, and SSH exploitation  
- Command injection vulnerability  
- Custom backdoor services  

**Root escalation was not attempted** — box completed upon accessing Summer’s user shell and capturing all available flags.

---

## ✍️ Author

**Anshif**  
Certified Penetration Tester | Cybersecurity Enthusiast  
[GitHub Profile](https://github.com/YourGitHubUsername)

---
