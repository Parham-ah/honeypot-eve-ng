# honeypot-eve-ng
A practical lab project to deploy and test honeypot scenarios in a virtual network using EVE-NG

# 🕵️ Honeypot-Based Intrusion Detection & Response with EVE-NG

This project demonstrates a simulated intrusion detection and response system** using a honeypot architecture in a virtual network created in [EVE-NG](https://www.eve-ng.net/). The setup includes a Linux-based Cowrie honeypot, Snort for traffic analysis, and automated router reconfiguration using Python and SSH.

## 📌 Project Overview

> Goal: Detect suspicious activities in a simulated network and dynamically redirect the attacker to a honeypot for analysis and isolation.

### 🧱 Network Topology

- **Clients (VPC):** Simulated users
- **Cisco Switch:** Connects clients to the Linux server
- **Linux Server:** Runs Cowrie honeypot + Snort IDS
- **Snort:** Detects attacks or scans
- **Python Script:** Triggered by Snort alerts to connect via SSH to the Cisco router and:
  - Block attacker IP
  - Redirect traffic to Cowrie honeypot

## 🧰 Tools & Technologies

- 🧪 EVE-NG (Network Emulator)
- 🐍 Python (for SSH automation)
- 🐚 Cowrie Honeypot (SSH/Telnet fake shell)
- 🛡 Snort IDS (Network monitoring & alerting)
- 🖥 Cisco IOS (Router & Switch)
- 🧱 Linux Bridge (Traffic passthrough)

## ⚙️ Key Features

- Realistic honeypot scenario using Cowrie
- Live traffic monitoring with Snort
- Automatic response using Python and Paramiko SSH
- Full isolation and redirection of suspicious clients
- Visual topology in EVE-NG

## 📁 Repository Structure


## 🚀 How to Use

1. Open project in EVE-NG and load the topology.
2. Start all nodes (clients, switch, Linux server, router).
3. Run Snort on the Linux bridge server.
4. Launch the Python script to monitor Snort alerts.
5. Simulate attack from one of the VPCs (e.g., port scanning or brute-force).
6. Snort detects the threat, Python triggers SSH to router, and attacker is redirected to the honeypot.

## 🔒 Sample Python Functionality

```python
import paramiko
# Connect to router and apply ACL or static route to redirect attacker

