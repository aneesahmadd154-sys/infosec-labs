# Week 1: Lab Setup, Ethics and Rules of Engagement

## Goal
Learn the legal and ethical rules for security work, then build a safe lab to practice in.

## What I did
1. Read and signed the Rules of Engagement: only test systems I own or am allowed to test.
2. Installed VirtualBox on my computer.
3. Set up two virtual machines:
   - **Kali Linux**: the attacker machine
   - **Metasploitable2**: an intentionally vulnerable target machine
4. Put both on a **Host-only network** so they can talk to each other but not to the internet.
5. Tested the setup:
   - Kali could ping Metasploitable2 (works)
   - Metasploitable2 could not ping an internet address (fails, which is the correct result)

## Key ideas
- Unauthorized access to computer systems is a crime (in Pakistan, under PECA 2016), whatever the intention.
- Isolating the lab keeps vulnerable machines and testing tools away from real networks.
- A failed ping to the internet is proof the isolation works.

## Tools
VirtualBox, Kali Linux, Metasploitable2, `ifconfig`, `ping`

## Screenshots
Add yours here, for example:
- `screenshots/vms-running.png`
- `screenshots/ping-between-vms.png`
- `screenshots/ping-internet-fails.png`
