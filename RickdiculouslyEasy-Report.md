# RickdiculouslyEasy VulnHub CTF Report 📜

---

## 📌 Target Information

- **VM Name:** RickdiculouslyEasy  
- **Author:** Luke Childs  
- **Platform:** VulnHub (VirtualBox image)  
- **Operating System:** Fedora (Apache/2.4.27, vsFTPd 3.0.3)

---

## 🎯 Objective

Boot-to-root CTF to capture flags and obtain root access.  
Total expected points based on found flags: **50 points**

---

## 🛠️ Tools Used

- `nmap`
- `ftp`
- `gobuster`
- `nc` (netcat)
- Browser (for HTTP enumeration)
- Basic Linux enumeration commands (`cat`, `ls`)

---

## 🔍 Service Enumeration Summary

| Port  | Service  | Version         | Status                  |
|:------|:----------|:----------------|:------------------------|
| 21    | FTP      | vsFTPd 3.0.3     | Anonymous login enabled  |
| 22    | SSH      | Unknown          | Open, no creds            |
| 80    | HTTP     | Apache/2.4.27    | Open                     |
| 9090  | HTTP     | Cockpit Service  | Open                     |
| 13337 | Unknown  | Custom Service   | Backdoor flag             |
| 22222 | SSH      | OpenSSH 7.5      | No valid login            |
| 60000 | Unknown  | Custom Reverse Shell | Root access           |

---

## 📜 Flags Captured

| Location                        | Flag                                           | Points |
|:--------------------------------|:------------------------------------------------|:--------|
| FTP anonymous root dir (FLAG.txt) | `FLAG{Whoa this is unexpected}`                  | 10     |
| HTTP Homepage source            | `FLAG{Yeah d- just don't do it.}`                 | 10     |
| HTTP on port 9090               | `FLAG{There is no Zeus, in your face!}`          | 10     |
| Custom service on port 13337    | `FLAG:{TheyFoundMyBackDoorMorty}`                | 10     |
| Reverse Shell on port 60000     | `FLAG{Flip the pickle Morty!}`                   | 10     |

**🎉 Total Points:** 50  

---

## 🔓 Exploitation Path

- **FTP Enumeration:**  
  Anonymous login enabled. Discovered `FLAG.txt` in root FTP directory.

- **HTTP (port 80):**  
  Found flag hidden in homepage HTML source comments.

- **HTTP (port 9090):**  
  Flag presented directly via Cockpit service.

- **Gobus**
