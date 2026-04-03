# SOC Homelab

This repository documents the process of building and experimenting with a small Security Operations Center (SOC) homelab.
The goal of this project is to understand how attacks generate telemetry and how defenders can investigate those events using host logs and a SIEM.

The lab environment is intentionally simple: an attacker machine simulates reconnaissance and other activity, a Windows system generates telemetry using Sysmon, and logs are analyzed in Splunk.

---

## Lab Architecture

```
Kali Linux (Attacker)
        │
        │  Network Activity / Reconnaissance
        V
Windows 10 VM
(Sysmon Telemetry)
        │
        │  Event Logs
        V
Splunk Enterprise
(Log Analysis & Detection)
```

This setup allows controlled attack simulation while keeping the host system isolated.

---

## Components

**Attacker Machine**

* Kali Linux
* Tools used for simulation:

  * Nmap
  * Hydra
  * Netcat
  * Curl

**Victim System**

* Windows 10 Virtual Machine
* Sysmon for enhanced event logging

**Monitoring / Analysis**

* Splunk Enterprise (running on host)
* Wireshark (optional packet inspection)

---

## Project Structure

```
SOC-Homelab
│
├── 01-Lab-Setup
├── 02-Log-Ingestion
├── 03-Attack-Simulation
├── 04-Detection-Rules
└── 05-Incident-Investigation
```

Each section documents a specific stage of building and using the lab.

---

## What This Lab Demonstrates

This project focuses on practical understanding of how security monitoring works.

Key areas explored:

* Network reconnaissance simulation
* Host telemetry using Sysmon
* Log ingestion and searching with Splunk
* Basic detection logic
* Incident investigation workflow

---

## Example Scenario

A simple reconnaissance scan can be simulated from the attacker machine.

```
nmap -sT -Pn <target-ip>
```

This activity helps demonstrate how network probing may appear from the defender’s perspective and how analysts can investigate it through available logs.

---

## Learning Goals

This homelab is primarily used to practice:

* Understanding attacker behavior
* Interpreting system telemetry
* Investigating events in a SIEM
* Documenting security analysis workflows

---

## Notes

This lab runs inside an isolated virtual environment.
All activity is performed for educational purposes within the local lab network.