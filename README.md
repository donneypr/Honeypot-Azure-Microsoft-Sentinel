# Azure Sentinel RDP Honeypot

## Overview
Welcome to the **Azure Sentinel RDP Honeypot** project! This repository demonstrates how to set up a dynamic honeypot using Azure Sentinel. In this setup, a Windows virtual machine (VM) acts as a decoy with an intentionally disabled firewall to attract attackers. RDP (Remote Desktop Protocol) logs are captured using PowerShell scripts, and attacks are visualized globally in Azure Sentinel.

## Description
This project features a PowerShell script that parses Windows Event Log data for failed RDP login attempts. It also integrates with a third-party API (ipgeolocation.io) to fetch geolocation data, allowing us to identify the physical location of the attackers.

In the accompanying demo, the following steps are covered:

### 1. VM Creation and Configuration:
- A Windows VM is set up and configured for access via Remote Desktop Protocol (RDP).
- RDP connection failures are logged and monitored using the Windows Event Viewer.

### 2. PowerShell Script for Log Enrichment:
- A custom PowerShell script is used to capture and log RDP failed connection attempts.
- The script enhances the logs with geolocation data obtained from the ipgeolocation.io API, giving more insight into where the attacks are coming from.

### 3. Log Analytics Integration:
- The VM is connected to Log Analytics to analyze and query RDP failure data using Kusto Query Language (KQL).

### 4. Azure Sentinel Workbook:
- The enriched log data is visualized within an Azure Sentinel workbook, providing a global view of RDP attack attempts.
- The workbook includes detailed graphs showing both the frequency and geographical distribution of failed RDP attempts.

## Features
- **RDP Failure Logs with IP Geolocation**: Retrieves and analyzes RDP failed logon attempts from the Windows Event Viewer, enriched with geolocation data via the ipgeolocation.io API.
  
- **Real-Time Attack Visualization**: Azure Sentinel is connected to the honeypot VM to capture and visualize real-time brute force RDP attacks.

- **Custom PowerShell Script**: A bespoke PowerShell script enhances the logs with geolocation data, providing a clear view of the attackers’ locations.

- **Log Analytics Integration**: The VM is integrated with Azure Log Analytics, where KQL queries are used to extract and analyze raw RDP failure data.

- **Azure Sentinel Workbook**: The enriched data is presented in an Azure Sentinel workbook, featuring visual representations of attack frequency and their geographical sources.

## Languages Used
- **PowerShell**: Used to extract and enhance RDP failed logon events from the Windows Event Viewer.
