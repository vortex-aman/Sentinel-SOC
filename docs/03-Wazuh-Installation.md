# ⚙️ Wazuh Installation

## Overview

Wazuh is an open-source Security Information and Event Management (SIEM) platform used for threat detection, security monitoring, log analysis, and incident response.

In the Sentinel SOC project, Wazuh serves as the central monitoring platform that collects and analyzes security events from monitored endpoints.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Ubuntu Server 25.04 |
| SIEM Platform | Wazuh |
| Virtualization | Oracle VirtualBox |
| Endpoint | Windows 10 |
| Attacker Machine | Kali Linux |

---

## Installation Method

The Wazuh server was installed on Ubuntu Server 25.04 using the official Wazuh installation method.

After the installation completed successfully, the following services were available:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

The Wazuh Dashboard became the central interface for monitoring endpoints, viewing alerts, and managing security events.

---

## Verification

After installation, the following checks were performed:

- Wazuh Dashboard was accessible.
- Wazuh services started successfully.
- The Ubuntu server was ready to accept endpoint agents.

This confirmed that the SIEM platform was operational.

---

## Result

The Wazuh installation completed successfully without any major issues.

The environment was ready for the next phase of the project: connecting a Windows endpoint and collecting security telemetry.

---

## Skills Demonstrated

- SIEM Deployment
- Ubuntu Server Administration
- Wazuh Installation
- Security Monitoring Setup
- Virtual Machine Configuration
