# My Week 1 Cybersecurity Lab

Week 1, Networkwalks Cybersecurity Internship, Batch B084M, task WK1-PM1. I am building my own test lab on my Mac, so I can learn scanning and vulnerability checks without touching any real network.

<p>
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

## Why I am making this lab

I want a place of my own where I can try security tools and see how networks behave. On my own Mac, inside a VM, a mistake stays inside the VM. That is the whole point for me in Week 1: get the lab right first, then use it for the later weeks.

I made this repo before the lab was finished, so I can note things down as I do them. Screenshots and final results will come from my own setup, once it is done. I am not putting in any screenshot I did not take.

## My setup at a glance

| Thing | My choice |
| --- | --- |
| My computer | MacBook Air M2, macOS |
| Tool to run VMs | UTM, because VirtualBox does not fit Apple Silicon well |
| Attacker VM | Kali Linux, arm64 build |
| Lab network | 10.0.0.0/24, private |
| Kali IP I plan to use | 10.0.0.2/24 |
| Gateway I plan to use | 10.0.0.1 |
| DNS | 8.8.8.8 |
| Machines I can add later | 10.0.0.7, 10.0.0.9, 10.0.0.10, 10.0.0.11, 10.0.0.16, Windows 7, Server 2016 and Android, optional for now |

The task sheet names VirtualBox. I am using UTM for the same job on my Mac, and the network idea stays the same: Kali on one private network, with space for target machines on that same network later.

My layout, in short: MacBook -> UTM -> Kali, 10.0.0.2, and later, MacBook -> UTM -> target VMs on 10.0.0.0/24.

## How I am building it, step by step

1. Get the Kali arm64 image from kali.org/get-kali.
2. Make a new VM for it in UTM.
3. Put that VM on a private network in the 10.0.0.0/24 range.
4. Set Kali to a fixed IP, 10.0.0.2, with gateway 10.0.0.1 and DNS 8.8.8.8.
5. Switch on clipboard sharing, drag and drop, and a shared Downloads folder, as the task asks.
6. Take a snapshot of the clean VM before I test anything, so I can restore it if I break the setup.

## How I will know it works

| What I will check | Command | What I expect to see |
| --- | --- | --- |
| Kali IP | `ip a` | 10.0.0.2 |
| Gateway | `ping 10.0.0.1` | Replies come back |
| Internet | `ping 8.8.8.8` | Replies come back |
| DNS | `nslookup networkwalks.com` | The name resolves |
| Nmap is there | `nmap --version` | Version shows up |
| Snapshot works | Restore it, then run `ip a` | Same 10.0.0.2 setup comes back |

Once I run these, I will add the real output here, not just what I expected.

## Screenshots I will add

These will all be from my own Mac and VM:

- UTM settings for my Kali VM
- Kali desktop after I log in
- Kali network settings showing 10.0.0.2
- Ping and DNS results
- My snapshot, with its name and date

## Problems I actually run into

I will fill this in with real problems only, in my own words: what went wrong, what I tried, and what fixed it. If a fix from the task sheet works for me, I will say so. If it does not, I will say that instead.

One thing I am watching for, because the task sheet mentions it: after a static IP is set, Kali can lose internet on newer builds, and the sheet gives nmcli commands for that. I will write about it only if it happens on my setup.

## What I am learning

I will fill this in after the setup, with what I actually learned from doing it, not a list I wrote in advance.

## Rules I am following

This lab is only for learning, and only on machines I own or have permission to test. I will not point these tools at systems that are not mine.

## About this project

Program: Networkwalks Cybersecurity Internship
Batch: B084M
Week: 1
Task: WK1-PM1, lab setup, adapted to UTM on Apple Silicon
Author: Muhammad Abdul Hanan

Links I used:
- Kali Linux: https://kali.org/get-kali
- Networkwalks project submission: https://networkwalks.com/project-submit/
