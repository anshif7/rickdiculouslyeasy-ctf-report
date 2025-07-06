# RickdiculouslyEasy VulnHub CTF — Write-Up & Report 📜

---

## 📌 Overview

This repository contains a complete penetration testing walkthrough and detailed report for the **RickdiculouslyEasy** CTF challenge hosted on **VulnHub**.

The goal was to capture hidden flags, exploit exposed services, and gain user access on a vulnerable Fedora-based machine themed around Rick and Morty.

---

## 🎯 Objectives

- Enumerate services and open ports  
- Capture multiple flags hidden across services and custom ports  
- Exploit command injection vulnerabilities  
- Perform SSH brute-force to gain user-level access  
- Document all findings and exploitation paths clearly  

---

## 🛠️ Tools Used

- `nmap` — Network scanning and service enumeration  
- `ftp` — Anonymous FTP login and file retrieval  
- `gobuster` — Web directory brute-forcing  
- `nc` (netcat) — Connecting to custom TCP services  
- `hydra` — SSH brute-force attacks  
- `ssh` — Remote login  
- Linux enumeration tools (`cat`, `ls`, `more`)  

---

## 📝 Summary

| 📌 Action                          | ✅ Status       |
|:----------------------------------|:----------------|
| Service Enumeration               | ✅ Completed     |
| FTP Exploitation                  | ✅ Flag captured |
| Web Directory Enumeration         | ✅ Flag and password found |
| Command Injection Exploitation    | ✅ Users enumerated |
| Netcat Service Exploitation (13337 & 60000) | ✅ Flags captured |
| SSH Brute-force (Port 22222)      | ✅ User access obtained (Summer) |
| Zeus Admin Panel (Port 9090)      | ✅ Flag captu
