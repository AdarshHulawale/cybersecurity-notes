TCPDUMP NOTES (Clean + Expanded)

➤ WHAT IS TCPDUMP?
tcpdump is a command-line network packet analyzer that captures, filters, and displays packets on an interface.  
Library dependencies:  
• Linux → libpcap  
• Windows → WinPcap / Npcap  

---------------------------------------------------
BASIC USAGE
---------------------------------------------------
• Capture on an interface:  
    tcpdump -i <interface>

• Save captured packets to a file:  
    tcpdump -w capture.pcap

• Read packets from a previously saved file:  
    tcpdump -r capture.pcap

• Limit number of packets captured:  
    tcpdump -c <count>

• Disable DNS resolution (avoid converting IP → domain):  
    tcpdump -n

• Disable BOTH DNS + port resolution:  
    tcpdump -nn

• Verbose output (more packet details):  
    -v, -vv, -vvv (more v = more detail)

---------------------------------------------------
FILTERING EXPRESSIONS
---------------------------------------------------
1. HOST-BASED FILTERS
• Specific host IP:  
    tcpdump host <IP>

• Specific hostname:  
    tcpdump host <hostname>

• Source host:  
    tcpdump src host <IP>

• Destination host:  
    tcpdump dst host <IP>

2. PORT FILTERS
• Filter by port:  
    tcpdump port 53

• Source port:  
    tcpdump src port <num>

• Destination port:  
    tcpdump dst port <num>

3. PROTOCOL FILTERS
• IP only:  
    tcpdump ip

• IPv6 only:  
    tcpdump ip6

• TCP packets:  
    tcpdump tcp

• UDP packets:  
    tcpdump udp

• ICMP packets:  
    tcpdump icmp

4. LOGICAL OPERATORS
• AND  
    tcpdump tcp and port 80

• OR  
    tcpdump port 80 or port 443

• NOT  
    tcpdump not port 22

5. ADVANCED FILTERS
• Greater than specific packet length:  
    tcpdump greater <len>

• Less than specific packet length:  
    tcpdump less <len>

6. PCAP HEADER BYTE FILTERING  
Syntax:  
    tcpdump 'proto[expr:size]'

Where:  
• proto = tcp, udp, ip, ether  
• expr = byte offset  
• size = number of bytes  

Example: filter packets with TCP SYN flag:  
    tcpdump 'tcp[13] & 2 != 0'

---------------------------------------------------
DISPLAY OPTIONS
---------------------------------------------------
• Quiet output (less verbose):  
    tcpdump -q

• Show link-layer header (Ethernet header):  
    tcpdump -e

• Print packet data in ASCII:  
    tcpdump -A

• Hex dump of packet data:  
    tcpdump -x

• Hex + ASCII (full packet dump):  
    tcpdump -xx

---------------------------------------------------
TCP FLAG-BASED FILTERS
---------------------------------------------------
• SYN packets (connection attempts):  
    tcpdump 'tcp[tcpflags] == tcp-syn'

• ACK packets:  
    tcpdump 'tcp[tcpflags] == tcp-ack'

• FIN packets:  
    tcpdump 'tcp[tcpflags] == tcp-fin'

• RST packets:  
    tcpdump 'tcp[tcpflags] == tcp-rst'

• PUSH flag packets:  
    tcpdump 'tcp[tcpflags] == tcp-push'

(Equivalent bitwise form)  
• SYN:  tcpdump 'tcp[13] & 2 != 0'  
• ACK:  tcpdump 'tcp[13] & 16 != 0'  
• FIN:  tcpdump 'tcp[13] & 1 != 0'  
• RST:  tcpdump 'tcp[13] & 4 != 0'  
• PSH:  tcpdump 'tcp[13] & 8 != 0'

---------------------------------------------------
USEFUL PRACTICAL EXAMPLES
---------------------------------------------------
• Capture all packets on wlan0:  
    tcpdump -i wlan0

• Capture only HTTP traffic (port 80):  
    tcpdump tcp port 80

• Capture only DNS traffic:  
    tcpdump udp port 53

• Capture packets to/from a specific IP:  
    tcpdump host 192.168.1.10

• Capture only TCP SYN packets (scans, connections):  
    tcpdump 'tcp[13] & 2 != 0'

• Capture traffic but don’t resolve DNS or ports:  
    tcpdump -nn -i eth0

• Capture 100 packets and save to file:  
    tcpdump -c 100 -w output.pcap

• Read the saved pcap:  
    tcpdump -r output.pcap

---------------------------------------------------
EXPERT NOTES
---------------------------------------------------
• tcpdump captures BEFORE firewall rules if using AF_PACKET (Linux).  
• Works at layer 2/3, extremely useful for debugging network attacks.  
• You can combine multiple filters with parentheses. Example:  
    tcpdump 'tcp and (port 80 or port 443) and not src host 10.0.0.1'  
• Running tcpdump requires root privileges on most systems.

A one-line introduction

“In cybersecurity, TCPDump is a command-line packet analyzer used for low-level network traffic capture and troubleshooting.”

When to use TCPDump vs Wireshark

“Use TCPDump for quick, remote, or CLI-based captures. Use Wireshark for deep GUI-based analysis.”

A small real-world example

Example:
“To capture only DNS traffic on interface eth0 and save it for later analysis:”

tcpdump -i eth0 port 53 -w dns.pcap

-------------------------------------------------------

---------------------------------------------------

