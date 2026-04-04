# Incident Report: Suspicious Command Execution Activity

## 1. Incident Summary

Suspicious command execution activity was observed on a Windows system. Multiple system commands were executed within a short time frame, indicating potential attacker reconnaissance after initial access.

---

## 2. Detection Details

* Detection Source: Splunk
* Log Source: Sysmon (Event ID 1)
* Detection Method: Process execution monitoring and command-line analysis

---

## 3. Affected System

* Host: victim-machine-

---

## 4. Observed Activity

The following commands were executed:

* whoami
* ipconfig
* netstat
* tasklist
* cmd.exe with additional commands

These commands are commonly used by attackers to gather system and network information.

---

## 5. Analysis

Logs show multiple process creation events with command-line arguments indicating system reconnaissance. Parent-child relationships reveal that PowerShell and command prompt were used to execute commands.

Noise from Splunk internal processes was identified and filtered out to focus on relevant activity.

---

## 6. MITRE ATT&CK Mapping

* T1059 – Command and Scripting Interpreter

---

## 7. Severity

Medium

---

## 8. Recommendations

* Monitor command-line activity on endpoints
* Restrict unnecessary use of administrative tools
* Implement alerting for suspicious parent-child process relationships

---

## 9. Conclusion

The activity indicates potential post-compromise behavior where an attacker is gathering information about the system. Continuous monitoring and detection rules are essential to identify such behavior early.