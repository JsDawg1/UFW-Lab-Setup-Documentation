# UFW Firewall Security Lab

A hands-on Linux firewall and network security lab built using **Debian 13, Kali Linux, UFW, and VirtualBox**.

The main goal of this project is to learn UFW through practical testing instead of only studying commands. Debian will be used as the protected server, while Kali Linux will be used to generate controlled network traffic and perform security testing against the server.

The entire lab is being built in a virtual environment using a **VirtualBox NAT Network**.

---

## Lab Environment

### Machines

* **Debian 13** — Protected server
* **Kali Linux** — Attacker / security testing machine

### Security & Networking Tools

* UFW
* Nmap
* Netcat
* OpenSSH
* curl
* Linux networking utilities

### Virtualization

* Oracle VirtualBox
* NAT Network

---

## What I Will Practice

### UFW Fundamentals

* Installing and configuring UFW
* Checking UFW status
* Understanding UFW default policies
* Enabling and disabling the firewall
* Allow, deny, and reject rules
* Viewing existing firewall rules

### Network Traffic Filtering

* Inbound traffic filtering
* Outbound traffic filtering
* TCP and UDP rules
* Port-based filtering
* Protocol-specific rules
* Source-IP-based access control
* Understanding source and destination ports

### Firewall Rule Management

* Adding rules
* Removing rules
* Numbered rules
* Inserting rules
* Rule ordering
* Duplicate and conflicting rules
* Updating firewall configurations
* Resetting and rebuilding rules

### Service Protection

Services will be introduced on the Debian server so that the firewall can be tested against real network services.

Planned testing includes:

* SSH
* HTTP
* Test services using Netcat

The objective is to understand how firewall rules affect access to running services.

---

## Security Testing

Kali Linux will be used to validate the firewall configuration.

### Nmap

Nmap will be used for:

* Host discovery
* Port scanning
* Service detection
* Comparing open and filtered ports
* Validating firewall rules

Example:

```bash
nmap <TARGET-IP>
```

```bash
nmap -sV <TARGET-IP>
```

```bash
nmap -p- <TARGET-IP>
```

### Netcat

Netcat will be used to:

* Create temporary listening services
* Test TCP connectivity
* Test whether firewall rules allow or block connections

### SSH & curl

SSH and curl will be used to test access to specific services and observe how UFW affects the connections.

---

## Logging & Monitoring

UFW logging will be enabled during the later stages of the lab.

I will generate controlled traffic from Kali and analyze the resulting firewall events on Debian.

The logs will be used to understand:

* Source IP
* Destination IP
* Source port
* Destination port
* Protocol
* Network interface
* Allowed or blocked traffic

This part of the project is focused on understanding firewall logs from a **blue-team / SOC perspective**.

---

## Attack & Defense Scenarios

After learning the individual UFW features, they will be combined into practical scenarios.

Examples include:

* Unauthorized SSH connection attempts
* Port scanning
* Blocking unnecessary services
* Allowing only specific source IPs
* Restricting inbound traffic
* Restricting outbound traffic
* Monitoring blocked traffic through firewall logs
* Validating firewall rules using Nmap
* Hardening a server based on required services

Each scenario will document:

```text
Objective
   ↓
Configuration
   ↓
Testing
   ↓
Observation
   ↓
Evidence
   ↓
Analysis
```

---

## Repository Structure

```text
UFW-Firewall-Security-Lab/
│
├── README.md
│
├── 01-Lab-Setup/
│   ├── setup.md
│   └── topology.png
│
├── 02-UFW-Basics/
│   └── ufw-basics.md
│
├── 03-Inbound-Rules/
│   └── inbound-testing.md
│
├── 04-Outbound-Rules/
│   └── outbound-testing.md
│
├── 05-Source-IP-Rules/
│   └── source-ip-filtering.md
│
├── 06-Service-Hardening/
│   └── service-hardening.md
│
├── 07-Port-Scanning/
│   └── nmap-testing.md
│
├── 08-Logging-Monitoring/
│   └── ufw-logging.md
│
├── 09-Rule-Management/
│   └── rule-management.md
│
└── 10-Attack-Scenarios/
    └── scenarios.md
```

The repository will be updated as each part of the lab is completed.

---

## Skills I Aim to Build

Through this project, I aim to gain practical experience with:

* Linux firewall administration
* Network traffic filtering
* Access control
* TCP/IP networking
* Port and service security
* Network reconnaissance
* Firewall logging
* Security-event analysis
* Server hardening
* Basic attack-and-defense workflows

---

## Goal

The goal of this project is to build a solid practical understanding of **UFW and Linux host-based firewalls** by configuring, testing, breaking, observing, and improving the firewall in a controlled environment.

This repository will serve as a record of the experiments, configurations, results, and lessons learned throughout the lab.
