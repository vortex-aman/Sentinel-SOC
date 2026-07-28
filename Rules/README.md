# 🛡️ Detection Rules

This directory contains the custom Wazuh detection rules developed for the Sentinel SOC project.

## Purpose

The rules in this folder are designed to detect suspicious Windows activities collected through Sysmon and analyzed by Wazuh.

## Current Rules

- Account Discovery (`net user`)
- User Discovery (`whoami`)

## Future Rules

- PowerShell Detection
- Mimikatz Detection
- PsExec Detection
- Reverse Shell Detection
- Nmap Detection
