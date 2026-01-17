# Windows Fundamentals – Notes (TryHackMe)

## Overview
These notes cover the Windows Fundamentals modules completed as part of the TryHackMe Pre Security learning path. The focus is on understanding Windows internals, system management, security features, and components relevant to cybersecurity and SOC roles.

---

## Windows Fundamentals 1

### Windows Editions & File Systems
- Windows 11 Home does NOT support BitLocker drive encryption.
- Windows 11 Pro supports BitLocker.
- NTFS (New Technology File System) is the modern Windows file system.
- Older file systems included FAT16, FAT32 (File Allocation Table), and HPFS.
- NTFS is a journaling file system, which improves reliability and recovery.

### NTFS Features
- Supports permissions and access control
- File compression and encryption
- Alternate Data Streams (ADS), which can be abused to hide data

### Important Windows Components
- `%windir%` – Environment variable pointing to the Windows directory
- `System32` – Contains critical system binaries and tools
- `lusrmgr.msc` – Local Users and Groups Manager
- User Account Control (UAC) – Limits unauthorized system-level changes

---

## Windows Fundamentals 2

### System Configuration
- `msconfig` – System Configuration utility
- Tabs include:
  - General
  - Boot
  - Services
  - Startup
  - Tools

### System & Management Tools
- `compmgmt.msc` – Computer Management
- Task Scheduler – Automates tasks
- Event Viewer – Logs system, security, and application events
- WMI Control – Manages Windows Management Instrumentation
- `msinfo32` – System Information
- `resmon` – Resource Monitor
  - CPU
  - Disk
  - Network
  - Memory

### Networking & Troubleshooting
- `ipconfig` – Displays network configuration
- Windows Troubleshooting:
  - `C:\Windows\System32\control.exe`
  - `Microsoft.Troubleshooting`

### User & Security Utilities
- `useraccountcontrolsettings.exe` – Configure UAC
- Sysinternals tools (Microsoft internal utilities)
- `psshutdown` – Shutdown and restart management tool

---

## Windows Fundamentals 3

### Windows Updates & Security
- Windows Update – Keeps the system patched
- Windows Security includes:
  - Virus & Threat Protection
  - Firewall & Network Protection
  - App & Browser Control
  - Device Security

### Firewall & Network Protection
- `wf.msc` – Windows Defender Firewall
- Controls inbound and outbound traffic

### App & Browser Control
- Microsoft Defender SmartScreen
- Exploit protection

### Device Security
- TPM (Trusted Platform Module)
  - Hardware-based security component
- BitLocker
  - Encrypts drives
  - Works together with TPM for secure key storage

### Additional Security Features
- VSS (Volume Shadow Copy Service)
  - Creates backups and restore points
  - Can be abused by attackers to hide malicious activity

---

## Key Cybersecurity Takeaways
- Windows internals are critical for SOC and blue-team roles
- Event logs, services, and system tools help detect threats
- Understanding Windows security features improves incident response and defense
