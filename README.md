# Cybersecurity Lab Setup - Week 1

This is my Week 1 project for the Networkwalks Cybersecurity Internship, Batch B084M. Task code: WK1-PM1.

I made this lab so I can practise scanning and vulnerability assessment on machines I own. I did not want to test anything on a real network, so everything here stays inside a private virtual network.

Status: I set up this repo first, so I can write things down as I go. The screenshots and final checks will go in after I finish the setup on my Mac. I will not add a screenshot I did not take myself.

## My machine

Host: MacBook Air M2
Hypervisor: UTM
Attacker machine: Kali Linux, arm64 build

A note on VirtualBox: the task sheet says VirtualBox. On Apple Silicon, VirtualBox is not a straight fit, so I used UTM instead. The network plan is the same: one private network, Kali as the attacker, and room for target machines later.

## Network plan

Network: 10.0.0.0/24
Kali IP (planned): 10.0.0.2/24
Gateway (planned): 10.0.0.1
DNS: 8.8.8.8

Future machines, as in the task diagram, are 10.0.0.7, 10.0.0.9, 10.0.0.10, 10.0.0.11 and 10.0.0.16. Those are Windows 7, Server 2016 and Android machines, and they are optional for now.

In plain form, the layout is:

MacBook (host) -> UTM -> Kali Linux, 10.0.0.2
MacBook (host) -> UTM -> future target VMs, same 10.0.0.0/24 network

## Steps I am following

1. Download Kali Linux arm64 from kali.org/get-kali.
2. Create the Kali VM in UTM.
3. Set the network to a private network in the 10.0.0.0/24 range.
4. Set Kali to a static IP, 10.0.0.2.
5. Turn on clipboard sharing, drag and drop, and a shared folder for Downloads, as the task asks.
6. Take a clean snapshot before I run any tests, so I can go back if I break something.

## Checks I will run

- `ip a`, to confirm Kali really has 10.0.0.2
- `ping 10.0.0.1`, to check the gateway
- `ping 8.8.8.8`, to check internet access
- `nslookup networkwalks.com`, to check DNS
- `nmap --version`, to confirm the tool is there

I will put the real output here, not the expected output, once I run these checks.

## Screenshots

To be added from my own setup:

- UTM settings for the Kali VM
- Kali desktop after login
- Kali network settings showing 10.0.0.2
- Ping and DNS check results
- Snapshot name and date

## Problems and fixes

To be updated with the real problems I hit. I will write each one in my own words, what I tried, and what fixed it. If a fix from the task sheet works, I will say so. If it does not, I will say that too.

One issue I already know to watch for, from the task sheet: after setting a static IP, Kali can lose internet on newer builds. The task sheet gives nmcli commands for that case. I will only write that section once I see whether it happens on my setup.

## What I learned so far

To be updated after the setup. I do not want to list lessons I have not done yet.

## Use of this lab

This lab is for learning only, on machines I own or have permission to test. I will not use these tools on systems I do not own.

## Project info

Program: Networkwalks Cybersecurity Internship
Batch: B084M
Week: 1
Task: WK1-PM1, Lab Setup, VirtualBox and Kali Linux, adapted to UTM on Apple Silicon, see the note above
Author: Muhammad Abdul Hanan

Tools and links:

- Kali Linux: https://kali.org/get-kali
- Networkwalks project submission: https://networkwalks.com/project-submit/
