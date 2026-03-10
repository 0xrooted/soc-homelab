# SOC Homelab – Lab Setup

## Overview

This stage documents the initial setup of a small SOC homelab environment used to simulate attacker activity and analyze host telemetry.

The goal of this stage is to establish an isolated lab where security events can be generated and later investigated using SIEM tools.

---

## Lab Architecture

```text
Attacker Machine (Kali Linux)
        │
        │  Reconnaissance Activity
        V
Windows 10 Virtual Machine
(Sysmon Telemetry)
        │
        │  Windows Event Logs
        V
Splunk Enterprise (SIEM)
```

This architecture allows attack simulation while keeping the host system isolated from the lab network.

---

## Network Configuration

The lab runs inside a **host-only virtual network** to ensure that all activity remains isolated.

Lab Network Range:

```
192.168.x.x (Host-only virtual network)
```

Example configuration:

| System        | Role             |
| ------------- | ---------------- |
| Kali Linux VM | Attacker machine |
| Windows 10 VM | Target system    |
| Host Machine  | Splunk SIEM      |

---

## Tools Used

### Attacker Machine

* Kali Linux
* Nmap
* Hydra
* Netcat
* Curl

### Victim System

* Windows 10 Virtual Machine
* Sysmon (system telemetry)

### Monitoring

* Splunk Enterprise (log analysis)
* Wireshark (optional packet inspection)

---

## Environment Validation

To confirm that the lab environment was configured correctly, connectivity between the attacker and target machines was tested.

Example command:

```
ping <target-system>
```

Successful replies confirm communication between the two systems.

---

## Reconnaissance Simulation

A basic network reconnaissance scan was performed from the attacker machine.

Example command:

```
nmap -sT -Pn <target-system>
```

The scan identified several Windows services exposed on the system, including services commonly associated with RPC and SMB.

From a defensive perspective, this type of activity is typically associated with **network reconnaissance** performed before an attack.

---

## SOC Perspective

Port scanning and service discovery are categorized as reconnaissance activities.

Relevant MITRE ATT&CK technique:

```
T1046 – Network Service Discovery
```

Security analysts monitor such activity to detect potential attackers mapping the network before attempting exploitation or lateral movement.

---

## Key Takeaways

* A controlled SOC homelab environment was successfully created.
* Network connectivity between attacker and victim machines was verified.
* Basic reconnaissance activity was simulated.
* The lab is now ready for log ingestion and detection analysis.

---

## Next Stage

The next phase of the project focuses on:

* ingesting Windows logs into Splunk
* building detection queries
* investigating simulated attack activity