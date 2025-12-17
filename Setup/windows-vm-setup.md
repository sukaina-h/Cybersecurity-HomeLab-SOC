# Windows 10 VM Installation

## Purpose
The Windows 10 virtual machine acts as the log-generating endpoint in the SOC lab. It is intentionally configured to behave like a typical user workstation so that realistic security events and logs can be generated and analyzed.

## Installation Steps
1- Downloaded Windows 10 (22H2) ISO from Microsoft
2- Created a new VM in VirtualBox
3- Attached the ISO during initial setup
4- Allocated disk space (50 GB, dynamically allocated)
5- Skipped product key (non-activated – lab use only)
6- Installed Windows 10 Pro

## Tools Installed on Windows VM

### Google Chrome
- Installed to simulate realistic user web activity
#### Used for:
- Downloading tools
- Generating browser-related logs
- Creating normal user behavior for SOC analysis

### Sysinternals Suite
- Installed to gain deep visibility into Windows internals, commonly used by SOC analysts and incident responders.
#### Key tools included:
1- Process Explorer: Used to inspect running processes, parent-child relationships, and suspicious behavior.
2- Autoruns: Used to identify persistence mechanisms such as startup programs and scheduled tasks.
3- TCPView: Used to monitor active network connections and identify suspicious traffic.
#### Installation path:
C:\Sysinternals

## Logging Configuration (SOC-Focused)

### Windows Event Logging
Verified that the following logs are enabled and generating events:
- Security
- System
- Application

### PowerShell Logging
Enabled via Group Policy to increase visibility:
- PowerShell Script Block Logging
- PowerShell Transcription
#### Purpose:
- Capture detailed PowerShell execution
- Detect suspicious or malicious command usage

## Verification Checklist
- Windows boots normally
- Local user accounts created successfully
- Google Chrome launches correctly
- Sysinternals tools execute properly
- Security and PowerShell logs are visible in Event Viewer

## Outcome
The Windows VM is fully configured as a SOC-monitored endpoint, capable of generating realistic logs for detection, investigation, and incident response practice.
