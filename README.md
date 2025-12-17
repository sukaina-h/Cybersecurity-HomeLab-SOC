# Cybersecurity Home Lab (SOC Analyst Beginner Project)
## 📌 Project Overview
This project documents the step-by-step creation of a Cybersecurity Home Lab designed to simulate real-world SOC (Security Operations Center) analyst tasks.

### The lab is built using VirtualBox with:
- Kali Linux (analysis / attacker / SOC tools)
- Windows 10 (log source / victim machine)

### The goal is to gain hands-on experience in:
- Endpoint monitoring
- Log analysis
- PowerShell logging
- SOC-style investigations

This repository documents everything from initial setup to future attack simulations.

### Tools & Technologies Used
- Oracle VirtualBox
- Kali Linux (Pre-built VM)
- Windows 10 (ISO – non-activated)
- Wireshark
- Sysinternals Suite
- Windows Event Viewer
- PowerShell Logging

### Host System Constraints

- CPU: 1.8 GHz
- Strategy: Run one VM at a time for stability

### Lab Architecture (Current)
| Host Machine
├── VirtualBox
│   ├── Kali Linux VM
│   └── Windows-SOC-Lab VM

## Step-by-Step Lab Setup

This section documents the exact order followed to build the lab from scratch.

### Step 1: Install VirtualBox
- Downloaded and installed Oracle VirtualBox on a Windows host system
- VirtualBox is used as the hypervisor to run multiple operating systems safely
#### Purpose: 
- Create isolated environments for attack and defense simulations

### Step 2: Kali Linux Installation
#### Installation Method
- Downloaded Kali Linux VirtualBox pre-built image (.vbox + .vdi)
- Added Kali VM via: Machine → Open → select .vbox file
#### Resource Allocation (Based on Host Limitations)
- RAM: 2048 MB
- CPU: 1 Core
- Video Memory: 128 MB
- Network: NAT
#### Purpose: 
- Kali Linux acts as the analysis and SOC tools machine
Status: ✅ Kali Linux boots successfully

### Step 3: Windows 10 VM Installation
#### Installation Method:
- Downloaded Windows 10 (22H2) ISO from Microsoft
- Created a new VM in VirtualBox
- Attached ISO during initial setup
#### VM Configuration
- RAM: 4096 MB (when running alone)
- CPU: 1 Core
- Disk Size: 50 GB (VDI, dynamically allocated)
#### Installation Notes
- Skipped product key (non-activated – lab use only)
- Installed Windows 10 Pro
#### Critical Fix
- Removed Windows ISO after installation to prevent reinstall loop
#### Purpose:
- Windows VM acts as the log-generating endpoint

### Step 4: User Account Configuration
- Created local accounts to simulate real enterprise environments:
- Primary user: labuser
- Secondary user: testuser
#### Purpose:
- Generate authentication logs
- Practice SOC investigations related to login events

Step 5: Logging & Monitoring Configuration
- Windows Event Logging
- Verified the following logs in Event Viewer:
- Security
- System
- Application
- PowerShell Logging (SOC-Level)
#### Enabled using Group Policy:
- PowerShell Script Block Logging
- PowerShell Transcription
#### Purpose:
- Capture detailed PowerShell activity
- Detect suspicious command execution

### Tools Installed on Windows
- Google Chrome
- Used to generate realistic browser activity
- Sysinternals Suite
#### Installed at:
- C:\Sysinternals
#### Key tools:
- Process Explorer
- Autoruns
- TCPView

### Documentation Approach
- Daily progress is documented
- Configuration decisions are explained
- Screenshots will be added in future commits

## Current Status

✅ Kali Linux configured ✅ Windows VM installed and hardened ✅ SOC-level logging enabled

## Next Planned Steps
- Configure VM networking (Host-only + NAT)
- Install Wireshark analysis scenarios
- Install Splunk (future – resource dependent)
- Simulate SOC incidents (brute force, suspicious PowerShell)

## Learning Outcome
- This project demonstrates:
- Virtualization skills
- Endpoint monitoring fundamentals
- SOC analyst mindset
- Hands-on cybersecurity practice

## Disclaimer
This lab is for educational purposes only. No real systems or networks are targeted.


#### This repository will continue to evolve as more SOC scenarios are implemented.
