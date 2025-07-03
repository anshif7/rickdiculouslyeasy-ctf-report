# RickdiculouslyEasy VulnHub CTF — Write-Up & Report 📜

---

## 📌 Overview

This repository contains a complete penetration testing walkthrough and detailed report for the **RickdiculouslyEasy** CTF challenge hosted on **VulnHub**.  

The goal was to capture hidden flags, exploit exposed services, and gain root access on a vulnerable Fedora-based machine themed around Rick and Morty.

---

## 🎯 Objectives

- Enumerate services and open ports
- Capture multiple flags hidden across services and custom ports
- Gain root-level access via a custom reverse shell
- Document all findings and exploitation paths clearly

---

## 🛠️ Tools Used

- `nmap`
- `ftp`
- `gobuster`
- `nc` (netcat)
- Linux enumeration tools and basic commands (`cat`, `ls`)

---

## 📝 Summary

| 📌 Action                      | ✅ Status  |
|:------------------------------|:------------|
| Service Enumeration            | ✅ Completed |
| FTP Exploitation               | ✅ Flag captured
