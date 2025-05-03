## ICS344 Cybersecurity Project

Group 06 – Section F08

Members:
 • Duaa Alhassan (202168790)
 • Zainab Almaskeen (202175370)
 • Renad Alqahtani (202169930)

Date: 03/05/2025

⸻

## Overview

This project demonstrates the end-to-end process of identifying and exploiting a vulnerable service, analyzing the attack using a SIEM platform, and implementing a defensive security strategy. The environment consists of Kali Linux as the attacker machine and Metasploitable3 as the victim machine.

⸻

## Phase 1: Setup and Compromise the Service

## Objective:

Conduct a brute-force SSH attack using Metasploit to gain unauthorized access to the victim machine.

Steps:
 1. Identified IP addresses of both attacker and victim VMs.
 2. Verified network connectivity between machines.
 3. Performed port scanning using Nmap to discover open services.
 4. Used Metasploit’s ssh_login auxiliary module to brute-force SSH credentials.
 5. Successfully logged in using credentials (vagrant:vagrant).
 6. Performed post-exploitation commands like id, pwd, uname -a.

⸻

## Phase 2: Visual Analysis with a SIEM Dashboard

## Objective:

Use a SIEM platform (Splunk) to monitor, visualize, and analyze attack behavior.

Steps:
 1. Installed and configured Splunk on the attacker machine.
 2. Installed and configured Splunk Universal Forwarder on the victim machine.
 3. Forwarded logs from /var/log/auth.log to Splunk.
 4. Verified log integration and analyzed SSH brute-force patterns in the dashboard.

⸻

## Phase 3: Defensive Strategy Proposal

## Objective:

Implement a security measure to mitigate the brute-force SSH attack.

Defense Tool: Fail2Ban

Steps:
 1. Installed Fail2Ban on the victim machine (Metasploitable3).
 2. Configured Fail2Ban to monitor SSH logs and detect failed login attempts.
 3. Verified that Fail2Ban was active before the attack.
 4. Re-executed the brute-force attack from Kali.
 5. Fail2Ban successfully blocked the attacker IP after 8 failed attempts.
 6. Verified that the attacker was listed as banned.

⸻

## Technologies Used
 • Kali Linux
 • Metasploitable3
 • Metasploit Framework
 • Python (Paramiko library)
 • Splunk SIEM
 • Fail2Ban

⸻

## How to Run the Project
 1. Environment Setup:
        Launch both Metasploitable3 and Kali Linux VMs.
        Ensure network connectivity.
 2. Perform the Attack:
        Use Metasploit to brute-force SSH credentials.
        Alternatively, use the Python script via Paramiko.
 3. Analyze with SIEM:
        Install and configure Splunk and Universal Forwarder.
        Monitor /var/log/auth.log and visualize attack data.
 4. Defend with Fail2Ban:
        Install and configure Fail2Ban on the victim.
        Monitor its response during re-attack attempts.

⸻

Work Distribution
 • Duaa Alhassan – 33.3%
 • Zainab Almaskeen – 33.3%
 • Renad Alqahtani – 33.3%

All team members contributed equally in technical implementation, testing, documentation, and reporting.
