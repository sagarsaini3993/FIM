# Wazuh File Integrity Monitoring Project

## Overview
This project shows how I used WAZUH, an open-source security tool, to detect any file or folder changes on monitored systems.  
It helps identify when files are created, deleted, or modified — an important part of protecting systems from tampering. I created this setup using virtual machines to simulate a small company network, with one system as the Wazuh Manager and another as an endpoint(agent).

---

## Project Setup

 * Host Machine is macOS(Apple Silicon) with IP 10.0.0.16. 
 * Virtualization is done using VirtualBox under Bridged Adapter mode so that all machines can be under same network.
 * Ubuntu VM is running Wazuh Manager and Dashboard with IP 10.0.0.226.
 * Windows VM has Wazuh Agent installed with IP 10.0.0.206.
 * Host machine has also been used as an endpoint.

---

## Objective
To configure Wazuh so it can:
1. Detect when a file or folder is created, modified, or deleted and currently, we are monitoring a specific folder.
2. Send alerts to the Wazuh dashboard in real time.  
3. Help understand how File Integrity Monitoring (FIM) works in real-world SOC operations.

---

## Configuration

Wazuh Agent Configuration (Windows)
Below is the configuration snippet I used to monitor file changes:

 <!-- File-Integrity-Monitoring -->
<syscheck>
  <directories realtime="yes">C:\Users\Sagar Saini\Desktop\test</directories>
</syscheck>
