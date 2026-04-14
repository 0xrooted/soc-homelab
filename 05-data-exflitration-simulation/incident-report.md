# Incident Report: Suspicious Data Exfiltration Activity

## 1. Incident Summary

Suspicious outbound communication was detected from a Windows system to an external host. The activity involved repeated HTTP requests and may indicate potential data exfiltration behavior.

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

The system initiated multiple HTTP connections to an external IP address. The activity was performed using PowerShell and involved repeated requests over a short time period.

---

## 5. Analysis

The outbound connections to an external system, combined with the use of PowerShell, suggest potential data transfer behavior. Repeated communication patterns may indicate automated or scripted activity.

---

## 6. MITRE ATT&CK Mapping

* T1041 – Exfiltration Over C2 Channel

---

## 7. Severity

Medium

---

## 8. Recommendations

* Monitor outbound traffic to external systems
* Restrict use of scripting tools for network communication
* Implement alerting for repeated connections to the same destination

---

## 9. Conclusion

The observed behavior indicates possible data exfiltration activity. Continuous monitoring of outbound connections is essential to detect and prevent unauthorized data transfer.