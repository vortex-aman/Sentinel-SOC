# ⚔️ Attack Simulation

## Overview

To validate the Sentinel SOC environment, multiple attack techniques were executed on the Windows 10 endpoint. These activities generated security events that were collected by Sysmon, forwarded by the Wazuh Agent, and analyzed by the Wazuh Manager.

The purpose of these simulations was to verify log collection, improve detection engineering skills, and test custom Wazuh detection rules.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Wazuh |
| Endpoint | Windows 10 |
| Monitoring | Sysmon |
| Attacker | Kali Linux |
| Virtualization | Oracle VirtualBox |

---

# Attack 1 – Windows Account Enumeration

## Objective

Simulate an attacker enumerating local user accounts.

## Command

```cmd
net user
```

## Expected Behavior

The command lists all local user accounts.

This activity can indicate reconnaissance performed after an attacker gains access to a system.

## Detection

A custom Wazuh rule was created to detect execution of the `net user` command.

## MITRE ATT&CK

- T1087 – Account Discovery

---

# Attack 2 – Current User Discovery

## Objective

Identify the currently logged-in user.

## Command

```cmd
whoami
```

## Expected Behavior

Displays the current username.

Although commonly used by administrators, attackers frequently execute this command immediately after obtaining access.

## Detection

The activity is captured through Sysmon Process Creation events and analyzed by Wazuh.

## MITRE ATT&CK

- T1033 – System Owner/User Discovery

---

# Attack 3 – Command Prompt Activity

## Objective

Generate command execution telemetry for detection testing.

## Example Commands

```cmd
hostname
ipconfig
systeminfo
```

## Detection

Sysmon records each process execution.

Wazuh ingests these events and can trigger alerts when suspicious command patterns are observed.

---

# Attack Flow

```
Attack Executed

        ↓

Windows 10

        ↓

Sysmon Logs Event

        ↓

Wazuh Agent

        ↓

Ubuntu Wazuh Manager

        ↓

Rule Evaluation

        ↓

Alert Generated
```

---

# Detection Summary

| Attack | Detection Status |
|----------|-----------------|
| net user | ✅ Detected |
| whoami | ✅ Logged |
| hostname | ✅ Logged |
| ipconfig | ✅ Logged |
| systeminfo | ✅ Logged |

---

# Lessons Learned

The simulations demonstrated how endpoint activity is transformed into actionable security telemetry.

Using Sysmon together with Wazuh improves visibility into endpoint behavior and provides valuable data for threat detection and incident response.

---

# Skills Demonstrated

- Attack Simulation
- Endpoint Monitoring
- Detection Engineering
- Windows Security Logging
- Threat Detection
- MITRE ATT&CK Mapping
