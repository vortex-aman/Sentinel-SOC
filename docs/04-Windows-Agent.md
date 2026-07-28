# 💻 Windows 10 Agent Configuration

## Overview

To monitor endpoint activity, the Wazuh Agent was installed on a Windows 10 virtual machine and connected to the Wazuh Manager running on Ubuntu Server.

Once connected, the endpoint began forwarding Windows Event Logs and Sysmon telemetry to the Wazuh server for analysis.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Agent | Wazuh Agent |
| Monitoring | Sysmon |
| Manager | Ubuntu Server 25.04 |

---

## Agent Installation

The Wazuh Agent was installed on the Windows 10 virtual machine using the official Wazuh agent package.

During the installation, the following information was configured:

- Wazuh Manager IP Address
- Agent Registration
- Agent Service

After installation, the Wazuh Agent service was started successfully.

---

## Agent Registration

The Windows endpoint successfully registered with the Wazuh Manager.

After registration, the endpoint appeared in the Wazuh Dashboard as an active agent.

This confirmed that communication between the Windows endpoint and the Wazuh Manager was working correctly.

---

## Log Collection

After the agent was connected, Windows Event Logs were forwarded to the Wazuh Manager.

The collected logs included:

- Security Events
- System Events
- Application Events
- Sysmon Events

These logs provide the telemetry required for threat detection and incident investigation.

---

## Verification

The following checks confirmed that the Windows endpoint was communicating successfully:

- Windows Agent connected successfully
- Agent status displayed as **Active**
- Events visible in the Wazuh Dashboard
- Logs received without errors

---

## Result

The Windows 10 endpoint was successfully integrated into the Sentinel SOC environment.

The endpoint now continuously sends security telemetry to Wazuh, enabling real-time monitoring and detection.

---

## Skills Demonstrated

- Windows Endpoint Monitoring
- Wazuh Agent Deployment
- Endpoint Registration
- Log Collection
- Security Monitoring
