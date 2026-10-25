<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-UTM-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-arm64-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Host-MacBook%20Air%20M2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Muhammad%20Abdul%20Hanan-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This is my Week 1 project for the Networkwalks Cybersecurity Internship, Batch B084M. Task code: WK1-PM1.

I built this lab so I can practise scanning and vulnerability assessment on machines I own, without touching a real network. Everything here stays inside a private virtual network, and target machines can be added to the same network later.

Status: I made this repo first, so I can write things down as I go. The screenshots and final check results will go in after I finish the setup on my Mac. I will not add a screenshot I did not take myself.

---

## 🎯 Objectives

- Set up a hypervisor on my Mac and create a Kali Linux VM in it.
- Create a private network for the lab, in the 10.0.0.0/24 range.
- Give Kali a fixed IP address, 10.0.0.2, and check that it can reach the internet.
- Turn on clipboard sharing, drag and drop, and a shared Downloads folder.
- Take a clean snapshot of the VM, so I can go back to a working setup.
- Write down the full setup, with my own screenshots, problems, and fixes.

---

## 🛡️ Purpose of the Lab

This lab is for learning only. I will use it for network reconnaissance, port scanning, vulnerability assessment, packet analysis, and other security testing, but only on systems I own or have permission to test.

---

## 🏗️ Lab Architecture

MacBook (host) -> UTM -> Kali Linux, 10.0.0.2
MacBook (host) -> UTM -> future target VMs, same 10.0.0.0/24 network

Future machines, as in the task diagram, are 10.0.0.7, 10.0.0.9, 10.0.0.10, 10.0.0.11 and 10.0.0.16. Those are Windows 7, Server 2016 and Android machines, and they are optional for now.

A note on VirtualBox: the task sheet says VirtualBox. On Apple Silicon, VirtualBox is not a straight fit, so I used UTM instead. The network plan is the same: one private network, Kali as the attacker, and room for target machines later.

---

## ⚙️ Lab Configuration

| Component | Configuration |
| --- | --- |
| Host OS | macOS, MacBook Air M2 |
| Hypervisor | UTM |
| Security OS | Kali Linux, arm64 build |
| Virtual Network | Private network |
| Network Address | 10.0.0.0/24 |
| Kali IP Address | 10.0.0.2/24 |
| Default Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |
| Future VM Range | 10.0.0.3-10.0.0.99 |

---

## 🪜 Lab Setup Procedure

### Step 1. Download Kali Linux

Download the Kali Linux arm64 image from the official Kali site, kali.org/get-kali.

### Step 2. Create the VM in UTM

Create a new VM in UTM and attach the Kali image to it.

### Step 3. Set up the private network

Set the VM network to a private network in the 10.0.0.0/24 range, so Kali and future target VMs can talk to each other, and Kali can still reach the internet.

### Step 4. Set a static IP on Kali

Set Kali to 10.0.0.2, subnet mask 255.255.255.0, gateway 10.0.0.1, DNS 8.8.8.8. A fixed IP makes the lab easier to write about and to use again later.

### Step 5. Turn on sharing

Turn on clipboard sharing, file drag and drop, and a shared folder for Downloads, as the task asks, so I can move files between the Mac and Kali.

### Step 6. Take a clean snapshot

Take a snapshot of the clean, working VM before I run any tests. If a later test breaks the setup, I can restore this snapshot instead of starting again.

---

## 🔎 Lab Verification

| Test | Command | Expected Result |
| --- | --- | --- |
| Check IP address | `ip a` | Kali shows 10.0.0.2 |
| Test gateway | `ping 10.0.0.1` | Successful replies |
| Test internet | `ping 8.8.8.8` | Successful replies |
| Test DNS | `nslookup networkwalks.com` | Domain resolves |
| Verify Nmap | `nmap --version` | Nmap version displayed |
| Verify snapshot | Restore snapshot and run `ip a` | Baseline configuration restored |

I will put the real output here, not just the expected output, once I run these checks.

---

## 🐞 Problems Encountered & Solutions

To be updated with the real problems I hit. I will write each one in my own words, what I tried, and what fixed it. If a fix from the task sheet works, I will say so. If it does not, I will say that too.

One issue I already know to watch for, from the task sheet: after setting a static IP, Kali can lose internet on newer builds. The task sheet gives nmcli commands for that case. I will only write that section once I see whether it happens on my setup.

---

## 💡 What I Learned

To be updated after the setup. I do not want to list lessons I have not done yet.

---

## 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only, on machines I own or have permission to test.

---

## 🔗 Tools & Resources

- **Kali Linux:** https://kali.org/get-kali
- **Networkwalks project submission:** https://networkwalks.com/project-submit/

---

## 👤 Author

**Muhammad Abdul Hanan**

Cybersecurity student, Networkwalks Batch B084M, Week 1, Task WK1-PM1
