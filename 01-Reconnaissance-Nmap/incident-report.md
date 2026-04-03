# Incident Report: Suspicious Network Scanning Activity

## 1. Incident Summary

A potential reconnaissance activity was detected involving multiple connection attempts from a single source IP to various ports on a Windows system. The behavior is consistent with port scanning.

---

## 2. Detection Details

* Detection Source: Splunk
* Log Source: Sysmon (Event ID 3)
* Detection Method: High number of unique destination ports accessed by one source

---

## 3. Affected Systems

* Target Host: VICTIM_IP
* Source Host: ATTACKER_IP

---

## 4. Timeline

* Scan initiated: Start time: 09:38:39.491 AM, End time: 10:08:46.537 AM

---

## 5. Analysis

The logs indicate that a single source IP attempted connections to multiple ports within a short period. This pattern aligns with reconnaissance techniques used to identify exposed services.

---

## 6. MITRE ATT&CK Mapping

* T1046 – Network Service Discovery

---

## 7. Severity

Low

---

## 8. Recommended Actions

* Monitor the source IP for further activity
* Restrict unnecessary open ports
* Implement network-level controls if required

---

## 9. Conclusion

The activity appears to be a reconnaissance attempt. No evidence of further exploitation was observed at this stage.