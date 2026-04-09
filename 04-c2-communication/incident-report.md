# Incident Report: Suspicious Outbound Network Communication

## 1. Incident Summary

Suspicious outbound communication was detected from a Windows system to an external host. The activity was initiated using PowerShell and is indicative of potential command-and-control (C2) behavior.

---

## 2. Detection Details

* Detection Source: Splunk
* Log Source: Sysmon (Event ID 3)
* Detection Method: Monitoring outbound network connections

---

## 3. Affected System

* Host: VICTIM_MACHINE

---

## 4. Observed Activity

The system initiated an HTTP connection to an external IP address. The connection was performed using PowerShell, which is not typically associated with standard user browsing activity.

---

## 5. Analysis

Logs indicate that the victim system established communication with an external host over HTTP. The process involved (PowerShell) and the nature of the connection suggest potential command-and-control activity.

Repeated or periodic connections to the same destination may indicate beaconing behavior.

---

## 6. MITRE ATT&CK Mapping

* T1071 – Application Layer Protocol

---

## 7. Severity

Medium

---

## 8. Recommendations

* Monitor outbound connections initiated by scripting tools
* Restrict unnecessary PowerShell usage
* Implement alerting for connections to unknown external hosts

---

## 9. Conclusion

The activity demonstrates characteristics of command-and-control communication. Continuous monitoring of outbound traffic is necessary to detect and respond to such threats effectively.