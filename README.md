# Snort IDS Setup and Nmap Scan Detection

##  Project Overview

This project involved the setup and configuration of Snort, a powerful open-source intrusion detection system (IDS), to monitor local network traffic and detect potential threats. To simulate real-world attacker behavior, I used Nmap to perform a stealth TCP scan on a test machine. The scan attempted to detect open services like Microsoft RPC, NetBIOS, and SMB.

Snort successfully detected the scan, generating real-time alerts for suspicious UDP traffic and flagging UPnP discovery attempts, a common sign of reconnaissance. This exercise modeled a complete Red Team vs. Blue Team scenario, demonstrating a practical understanding of both offensive tactics and defensive strategies.

##  Skills & Technologies

* **Intrusion Detection System (IDS):** Snort
* **Network Scanning:** Nmap
* **Security Monitoring:** Real-time log and alert analysis
* **Operating System:** Ubuntu Linux
* **Networking:** TCP/UDP, UPnP, RPC, NetBIOS
* **Cybersecurity:** Red Team (Offensive) vs. Blue Team (Defensive) simulation

##  workflow Architecture & Workflow

The diagram below outlines the two parallel processes: the Red Team's attack initiation using Nmap and the Blue Team's defensive monitoring using Snort.

<p align="center">
  <img src=".assets/Snort IDS Architecture.jpg" alt="Snort IDS Workflow" width="600"/>
</p>
<p align="center">Figure 1: Workflow diagram of Nmap scan initiation and Snort's detection response.</p>

##  Live Detection Output

The screenshot below provides proof of the successful detection. The terminal on the right shows the Nmap scan being launched, while the terminal on the left shows Snort immediately generating alerts for the corresponding network reconnaissance activity.

<p align="center">
  <img src=".assets/Snort Output.jpg" alt="Snort Detecting Nmap Scan" width="800"/>
</p>
<p align="center">Figure 2: Snort (left) detecting the Nmap UPnP scan (right) in real-time.</p>

##  Key Configuration & Code

This scenario is broken into two parts: the offensive (Red Team) command used to initiate the scan, and the defensive (Blue Team) configuration and logs showing the detection.

### Red Team: Nmap Scan Command

A TCP SYN scan (`-sS`) was used to stealthily identify open ports.

```bash
# Nmap scan targeting a specific host to identify common services
nmap -sS 172.27.128.1
