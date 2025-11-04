# SafeLine Web Application Firewall (WAF) Home Lab

## Overview
This repository documents my hands-on cybersecurity lab where I built and tested a **Web Application Firewall (WAF)** using **SafeLine** on Ubuntu, with **DVWA (Damn Vulnerable Web App)** running on Kali Linux inside **VirtualBox** on macOS.

The main goal was to **understand how a WAF detects, inspects, and blocks web attacks** through practical, real-world simulation.

---

## Architecture

**Host (Mac)**  
↳ VirtualBox  
 • **Ubuntu VM** — SafeLine WAF  
 • **Kali Linux VM** — DVWA  

All VMs use **Bridged Networking** so they can communicate directly.

**Traffic Flow:**

Kali (Attacker) → SafeLine WAF (Ubuntu) → DVWA (Kali)

---

## Objectives
- Deploy and configure DVWA (vulnerable web app) inside Kali Linux  
- Use SafeLine WAF as a reverse proxy to analyze and block common web attacks  
- Test attacks (SQL Injection, XSS, HTTP Flood, Authentication Sign-in bypass, and custom rules)  
- Understand traffic inspection, rule enforcement, and WAF logging  

---

## Tools Used
| Tool | Purpose |
|------|----------|
| **VirtualBox** | VM virtualization |
| **Ubuntu** | SafeLine WAF host |
| **Kali Linux** | Attack simulation & DVWA host |
| **SafeLine WAF v9.2.6** | Web Application Firewall |
| **DVWA (Apache + MariaDB)** | Vulnerable web app |
| **OpenSSL** | SSL certificate creation |

---

##  Setup Summary
1. Created two VMs in VirtualBox (Ubuntu + Kali)  
2. Installed SafeLine WAF on Ubuntu and configured SSL  
3. Deployed DVWA on Kali with MySQL credentials  
4. Linked SafeLine → DVWA as reverse proxy  
5. Verified traffic via curl tests and host mappings  
6. Performed attacks and analyzed WAF logs  

---

## Issues Faced
- **Port mismatch** between WAF and DVWA (`8080` vs `80`) caused routing errors  
- **Hostname resolution**: fixed by adding `/etc/hosts` entry on both VMs  

---

## Results
Once configured, SafeLine WAF successfully detected and blocked multiple attacks including:  
- SQL Injection payloads  
- Authentication
- Custom Deny Rules (blockng Kali IP)
- HTTP Flood simulations  

---

## 💡 Learnings
- Networking and routing matter more than tool configuration  
- WAF rules are only as effective as traffic routing  
- Debugging teaches more than tutorials ever will  


---

## Author
**[Tanishaa S]**  
Exploring web security hands-on and documenting my learning journey.  
Connect on [LinkedIn](https://www.linkedin.com/in/tanishaa-s-196114152/)

---

## 📜 License
MIT License
