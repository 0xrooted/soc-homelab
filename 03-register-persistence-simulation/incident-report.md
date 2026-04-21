# Incident Report: Persistence Mechanisms Detected

## 1. Incident Summary

Persistence mechanisms were identified on a Windows system involving registry modification and scheduled task creation. These actions indicate an attempt to maintain access across system restarts.

---

## 2. Detection Details

* Detection Source: Splunk
* Log Source: Sysmon (Event ID 13 and Event ID 1)
* Detection Method: Monitoring registry changes and command execution

---

## 3. Affected System

* Host: VICTIM_MACHINE_1

---

## 4. Observed Activity

The following persistence techniques were observed:

* Addition of a registry run key pointing to an executable
* Creation of a scheduled task configured to run at logon

---

## 5. Analysis

The registry modification ensures automatic execution of a program during user login. Additionally, the scheduled task provides another method for maintaining persistence.

Both techniques are commonly used by attackers to retain access after initial compromise.

---

## 6. MITRE ATT&CK Mapping

* T1547 – Boot or Logon Autostart Execution
* T1053 – Scheduled Task/Job

---

## 7. Severity

Medium

---

## 8. Recommendations

* Monitor registry Run keys for unauthorized changes
* Restrict creation of scheduled tasks
* Implement alerting for persistence-related behaviors

---

## 9. Conclusion

The detected activity suggests an attempt to establish persistence on the system. Continuous monitoring and detection mechanisms are necessary to prevent long-term unauthorized access.