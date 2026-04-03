# SOC Homelab – Lab Setup

## Overview

This stage covers the initial setup of a small SOC homelab environment used for generating and analyzing security telemetry.

The objective is to create an isolated setup where system activity can be monitored and later analyzed using a SIEM.

---

## Lab Architecture

```text
Attacker Machine (Kali Linux)
        │
        │  Simulated Activity
        ▼
Windows 10 Virtual Machine
(Sysmon Telemetry)
        │
        │  Windows Event Logs
        ▼
Splunk Enterprise (SIEM)
```

This architecture keeps all activity contained within a controlled lab environment.

---

## Network Configuration

The lab operates on a **host-only virtual network**, ensuring that all traffic remains isolated from external networks.

**Network Range:**

```
192.168.x.x
```

**System Roles:**

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
* Sysmon (for system telemetry)

### Monitoring

* Splunk Enterprise
* Wireshark *(optional)*

---

## Environment Validation

Connectivity between systems was verified to ensure proper communication within the lab network.

Example:

```bash
ping <target-system>
```

Successful responses confirm that the environment is correctly configured.

---

## SOC Perspective

From a monitoring standpoint, this setup enables:

* Collection of endpoint telemetry using Sysmon
* Centralized log analysis using Splunk
* Controlled generation of activity for analysis

This forms the foundation required for detection and investigation workflows.

---

## Key Takeaways

* A functional SOC homelab environment was successfully established
* Network isolation was implemented using a host-only configuration
* Communication between systems was verified
* The lab is ready for log ingestion and analysis

---

## Next Stage

The next phase focuses on:

* Ingesting Windows logs into Splunk
* Exploring event data
* Building initial detection queries
