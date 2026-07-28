# 🔍 Sysmon Configuration

## Overview

Sysmon (System Monitor) is a Microsoft Sysinternals tool that provides detailed visibility into Windows system activity. It records security-relevant events that are not available through standard Windows Event Logs.

In the Sentinel SOC lab, Sysmon is used to generate enhanced telemetry that enables Wazuh to detect suspicious and malicious activities.

---

## Why Sysmon?

By default, Windows logs do not capture enough detail for effective threat detection.

Sysmon provides additional event data, including:

- Process creation
- Network connections
- File creation
- Registry modifications
- Driver loading
- Process termination
- DNS queries (depending on configuration)

This additional telemetry helps security analysts investigate incidents more effectively.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Endpoint | Windows 10 |
| Monitoring Tool | Sysmon |
| Log Collection | Wazuh Agent |
| SIEM | Wazuh |

---

## Installation

Sysmon was installed on the Windows 10 virtual machine using Microsoft's Sysinternals Sysmon utility.

A Sysmon configuration file was applied to improve logging quality and capture security-relevant events.

After installation, Sysmon began recording detailed endpoint activity.

---

## Integration with Wazuh

The Wazuh Agent collects Sysmon events from the Windows endpoint and forwards them to the Wazuh Manager.

This enables:

- Threat detection
- Security monitoring
- Alert generation
- Incident investigation

---

## Verification

The following checks confirmed successful integration:

- Sysmon service running
- Sysmon events visible in Event Viewer
- Events received by Wazuh
- Logs searchable in the Wazuh Dashboard

---

## Result

Sysmon significantly improved endpoint visibility by generating detailed security telemetry.

Combined with Wazuh, it provides a powerful platform for monitoring, detection engineering, and incident response.

---

## Skills Demonstrated

- Windows Endpoint Monitoring
- Sysmon Deployment
- Log Collection
- Detection Engineering
- Blue Team Operations
