# Day 2 – Linux Fundamentals (Users, Processes & System Management)

## Overview
Today I learned intermediate Linux concepts related to users, permissions, processes, package management, automation, file transfers, and system services. These concepts are critical in cybersecurity because they explain how Linux systems are managed, monitored, and secured in real-world environments.

---

## Accessing a Linux Machine Using SSH
SSH (Secure Shell) is used to securely access a remote Linux machine over a network.

Syntax:
ssh username@ip_address

SSH requires valid credentials and encrypts communication, making it a standard method for remote administration and security operations.

---

## Flags and Switches
Flags and switches modify the behavior of Linux commands.

Examples:
-h or --help – Display help information  
-a – Show all files including hidden files  
-l – Display detailed file information  
man command – Open the manual page  

Example:
ls -la

---

## File System Interaction
touch – Create a new file  
mkdir – Create a directory  
rm – Remove a file  
rm -r – Remove a directory recursively  
cp – Copy files or directories  
mv – Move or rename files  
file – Identify file type  
ls -l – List files with permissions and ownership  

---

## Permissions and User Management
Linux permissions are divided into user, group, and others. Permission types include read (r), write (w), and execute (x).

Commands:
chmod – Change file permissions  
su – Switch user  
su -l – Switch user with login environment  
sudo – Execute commands with root privileges  

---

## Common Linux Directories
/etc – Configuration files  
/tmp – Temporary files  
/var – Logs and variable data  
/root – Home directory of the root user  

---

## Terminal Text Editors
nano – Beginner-friendly terminal editor  
vim – Advanced terminal editor commonly used on servers  

---

## Downloading and Transferring Files
wget – Download files from the web  
curl – Transfer data from URLs  

SCP is used to securely transfer files over SSH.

Example:
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt

---

## Serving Files from Your Host
A simple web server can be created using Python.

Command:
python3 -m http.server

Files can be accessed using curl or wget.

---

## Process Management
ps – View running processes  
ps aux – Detailed process information  
top – Real-time process monitoring  

PID refers to the Process ID.

kill PID – Terminate a process  

Signals:
SIGTERM – Graceful termination  
SIGKILL – Force termination  
SIGSTOP – Pause a process  

---

## Services and Startup Management
Services are managed using systemctl.

Syntax:
systemctl [option] service

Used to start, stop, and enable services at system boot.

---

## Foreground and Background Processes
Using & allows processes to run in the background, enabling multitasking in the terminal.

---

## System Automation with Cron
Cron is used to schedule automated tasks.

Command:
crontab -e

Used for backups, maintenance tasks, and automation.

---

## Package Management
apt update – Update package lists  
apt upgrade – Upgrade installed packages  
apt install – Install new packages  
add-apt-repository – Add software repositories  
dpkg – Manage Debian packages  

---

## Logs and Monitoring
Logs store system activity and errors.

Command:
less /var/log/syslog

Logs are essential for troubleshooting, monitoring, and incident response.

---

## Practical Usage in Cybersecurity
SSH is a common attack and defense vector.  
Permissions prevent unauthorized access and privilege escalation.  
Process monitoring helps detect malicious activity.  
Cron jobs can be abused for persistence.  
Logs are crucial for forensic analysis and incident response.

---

## What I Practiced
Accessing systems via SSH, managing users and permissions, monitoring processes, installing packages, transferring files, serving files via a web server, and reading system logs.

---

## Key Takeaway
Understanding Linux users, processes, services, and system management is essential for cybersecurity because most servers and security tools operate on Linux.

---

---

## How This Helps in a Cybersecurity Internship
These Linux concepts help me understand real-world security scenarios such as:
- Investigating suspicious processes on compromised systems
- Analyzing logs during incident response
- Managing permissions to reduce attack surface
- Securing SSH access on servers
- Automating routine security tasks using cron

This foundation prepares me for roles such as SOC analyst, security intern, or system security trainee.
