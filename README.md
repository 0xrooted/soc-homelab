# SOC Homelab

This repository documents the process of building and experimenting with a small Security Operations Center (SOC) homelab.

The objective of this project is to gain practical understanding of how attacker activity generates telemetry and how those events can be investigated using endpoint logs and a SIEM.

The lab is intentionally kept simple and focused. An attacker machine is used to simulate activity, a Windows system generates telemetry using Sysmon, and all logs are analyzed in Splunk.

---

## Lab Architecture

```
Kali Linux (Attacker)
        │
        │  Simulated Activity / Reconnaissance
        ▼
Windows 10 VM
(Sysmon Telemetry)
        │
        │  Event Logs
        ▼
Splunk Enterprise
(Log Analysis & Detection)
```

This setup enables controlled simulation of attacks while keeping everything contained within an isolated environment.

---

## Components

### Attacker Machine

* Kali Linux
* Tools used:

  * Nmap
  * Hydra
  * Netcat
  * Curl

### Victim System

* Windows 10 Virtual Machine
* Sysmon (for enhanced logging and visibility)

### Monitoring & Analysis

* Splunk Enterprise
* Wireshark *(optional, for packet-level inspection)*

---

## Project Structure

```
SOC-Homelab
│
├── 01-Lab-Setup
```

Each section represents a stage in building and using the lab, from initial setup to detection and investigation.

---

## What This Lab Covers

This project focuses on building a practical understanding of security monitoring and analysis.

Key areas include:

* Simulating network reconnaissance
* Collecting host telemetry using Sysmon
* Ingesting and searching logs in Splunk
* Writing basic detection logic
* Performing simple incident investigations

---

## Example Scenario

A basic reconnaissance scan can be simulated from the attacker machine:

```
nmap -sT -Pn <target-ip>
```

This helps demonstrate how scanning activity appears from a defender’s perspective and how it can be investigated using available logs.

---

## Learning Goals

This lab is used to practice:

* Understanding attacker behavior
* Interpreting endpoint telemetry
* Investigating events in a SIEM
* Documenting analysis and findings

---

## Notes

All activities are performed in isolated virtual environment and are intended strictly for educational purposes.
