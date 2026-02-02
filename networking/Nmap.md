NMAP NOTES (BASICS)

What is Nmap?
Nmap (Network Mapper) is a powerful network scanning tool used for host discovery, port scanning, OS detection, service enumeration, and general reconnaissance.

----------------------------------------------------
1. HOST DISCOVERY (WHO IS ONLINE?)
----------------------------------------------------
Used to identify which hosts are up on a network.

• Target formats:
  - IP Range: 192.168.1.1-50
  - Subnet: 192.168.1.0/24
  - Hostname: scanme.nmap.org

• Ping Scan (discover live hosts):
  nmap -sn <target>
  (Does NOT scan ports, only checks which hosts are up)

• List Scan (no actual scan, just lists targets):
  nmap -sL <target>

• Scan a local or remote network:
  nmap -sn 192.168.1.0/24

----------------------------------------------------
2. PORT SCANNING (WHO IS LISTENING?)
----------------------------------------------------

A. TCP Connect Scan (Full handshake)
• Performs full TCP 3-way handshake (not stealthy)
  nmap -sT <target>

B. SYN Scan / Stealth Scan (default, requires sudo)
• Sends SYN only, never completes handshake
  nmap -sS <target>

C. UDP Scan
• Slower; checks UDP open/filtered ports
  nmap -sU <target>

----------------------------------------------------
3. LIMITING TARGETING (SELECTING PORTS)
----------------------------------------------------

• Fast mode (scans top 100 ports instead of 1000)
  nmap -F <target>

• Select port range:
  nmap -p 1-1000 <target>

• Scan ALL 65535 ports:
  nmap -p- <target>

• Scan well-known ports (1–1024):
  nmap -p-1024 <target>

----------------------------------------------------
4. OS DETECTION & VERSION ENUMERATION
----------------------------------------------------

• OS Detection:
  nmap -O <target>

• Version Detection:
  nmap -sV <target>

• Aggressive Scan:
  nmap -A <target>
  (Does: OS detection + version detection + scripts + traceroute)

----------------------------------------------------
5. FORCE / OVERRIDE SCAN
----------------------------------------------------

• Treat all hosts as online (scan even if ping fails):
  nmap -Pn <target>

----------------------------------------------------
6. TIMING TEMPLATES (SCAN SPEED)
----------------------------------------------------

Nmap has 6 timing modes:
0 = paranoid
1 = sneaky
2 = polite
3 = normal
4 = aggressive
5 = insane

• Using timing template:
  nmap -T4 <target>
  or
  nmap -T aggressive <target>

----------------------------------------------------
7. RATE & PARALLELISM CONTROL
----------------------------------------------------

• Parallel service probes:
  --min-parallelism <num>
  --max-parallelism <num>

• Packet rate control:
  --min-rate <num>
  --max-rate <num>

----------------------------------------------------
8. OUTPUT CONTROL (VERBOSITY & DEBUGGING)
----------------------------------------------------

• Verbose Output:
  -v, -vv, -vvv, -vvvv, -v2, -v4

• Debugging Output:
  -d, -dd ... up to -d9 (maximum)

• Host timeout:
  --host-timeout <time>

----------------------------------------------------
9. SAVING/EXPORTING SCAN REPORTS
----------------------------------------------------

• Normal output:
  nmap -oN filename.txt <target>

• XML output:
  nmap -oX filename.xml <target>

• Greppable output:
  nmap -oG filename.grep <target>

• All major formats at once:
  nmap -oA basename <target>

----------------------------------------------------
10. DEFAULT BEHAVIOR (IMPORTANT)
----------------------------------------------------

• Running Nmap WITHOUT sudo = uses TCP Connect Scan (-sT)
• Running Nmap WITH sudo = uses SYN Scan (-sS)

----------------------------------------------------
Usage Reminder:
All flags follow the 'nmap' command:
nmap [flags] <target>
----------------------------------------------------
