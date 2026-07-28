# 🏗️ Lab Architecture

## Overview

The Sentinel SOC lab simulates a real-world Security Operations Center (SOC) environment where security events are generated, collected, analyzed, and investigated.

The environment consists of three virtual machines hosted in VirtualBox.

---

## Lab Components

### 🖥️ Ubuntu Server

Role:
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

Responsibilities:

- Collect logs
- Process security events
- Generate alerts
- Display dashboards

---

### 💻 Windows 11

Role:

- Victim Machine
- Wazuh Agent
- Sysmon Installed

Responsibilities:

- Generate Windows Events
- Send logs to Wazuh
- Execute attack simulations

---

### 🐉 Kali Linux

Role:

Attacker Machine

Responsibilities:

- Reconnaissance
- Enumeration
- PowerShell attacks
- Brute force simulations
- Network scanning

---

## Data Flow

Windows 10 generates security events.

↓

Sysmon records detailed activity.

↓

Wazuh Agent collects the logs.

↓

Ubuntu Wazuh Manager analyzes the events.

↓

Alerts appear in the Wazuh Dashboard.

---

## Network Diagram

*(A graphical architecture diagram will be added here.)*

```
              Internet
                   │
        ┌────────────────────┐
        │ Ubuntu Server      │
        │ Wazuh Manager      │
        └─────────┬──────────┘
                  │
      ┌───────────┴────────────┐
      │                        │
┌──────────────┐        ┌──────────────┐
│ Windows 10   │        │ Kali Linux   │
│ Wazuh Agent  │        │ Attacker VM  │
│ Sysmon       │        └──────────────┘
└──────────────┘
```

---

## Learning Objectives

This lab demonstrates:

- SIEM deployment
- Endpoint monitoring
- Windows logging
- Detection engineering
- Threat detection
- Blue Team operations
- Incident response
