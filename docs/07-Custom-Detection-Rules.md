# 🛡️ Custom Detection Rules

## Overview

While Wazuh includes many built-in detection rules, custom rules allow security analysts to detect organization-specific activities, reduce false positives, and improve visibility into suspicious behavior.

As part of the Sentinel SOC project, custom Wazuh rules were developed to detect Windows reconnaissance and command execution activities generated during attack simulations.

---

# Objective

The goals of creating custom detection rules were to:

- Detect attacker reconnaissance commands
- Improve endpoint visibility
- Learn Wazuh rule syntax
- Understand the detection pipeline
- Map detections to the MITRE ATT&CK Framework

---

# Detection Workflow

```
Attacker Command

        ↓

Windows 10

        ↓

Sysmon

        ↓

Windows Event Log

        ↓

Wazuh Agent

        ↓

Wazuh Manager

        ↓

Custom Rule

        ↓

Security Alert
```

---

# Rule 1 – Windows Account Enumeration

## Purpose

Detect execution of the `net user` command.

### Rule ID

```
100001
```

### MITRE ATT&CK

- T1087 – Account Discovery

### Detection Logic

When Sysmon records execution of the `net user` command, Wazuh evaluates the event against the custom rule and generates an alert.

---

# Rule 2 – Current User Discovery

## Purpose

Detect execution of the `whoami` command.

### Rule ID

```
100002
```

### MITRE ATT&CK

- T1033 – System Owner/User Discovery

### Detection Logic

The rule monitors process creation events and triggers an alert whenever the `whoami` command is executed.

---

# Detection Summary

| Rule ID | Detection | Status |
|----------|-----------|--------|
| 100001 | net user | ✅ Tested |
| 100002 | whoami | ✅ Tested |

---

# Benefits of Custom Rules

Creating custom rules provides several advantages:

- Detect environment-specific behavior
- Improve detection accuracy
- Reduce false positives
- Enhance incident investigations
- Strengthen detection engineering skills

---

# Future Rules

The following custom rules are planned:

- Encoded PowerShell Detection
- Mimikatz Detection
- PsExec Detection
- Reverse Shell Detection
- Nmap Scan Detection
- Failed Login Detection
- Suspicious CMD Activity

---

# Lessons Learned

Developing custom Wazuh rules provided hands-on experience with:

- Detection Engineering
- Threat Detection
- Windows Event Analysis
- Sysmon Event Monitoring
- MITRE ATT&CK Mapping
- Security Operations

These rules improve the SOC's ability to identify suspicious activities that may not be fully covered by default detections.
