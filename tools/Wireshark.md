# 🦈 Wireshark Basics – Networking Essentials

Wireshark is the most widely used **network packet analyzer** for cybersecurity, incident response, penetration testing, and network troubleshooting.  
These notes summarize how Wireshark works, key features, packet navigation, capturing, filters, and analysis techniques.

---

## 1️⃣ What Wireshark Does

Wireshark enables:

- **Traffic sniffing** – capturing live network packets  
- **Protocol inspection** – view every layer (Ethernet → IP → TCP/UDP → Application)  
- **PCAP analysis** – load and investigate captured packet files  
- **Network troubleshooting** – latency, retransmissions, errors  
- **Security analysis** – detect suspicious activity, scanning, or attacks  

It is essential for:
- Blue Team (defensive analysis)  
- Pentesting recon  
- Network engineering  
- DFIR investigations  

---

## 2️⃣ Wireshark Interface Overview

### ✔ Main Components
1. **Packet List Pane** – shows each captured packet (one row = one packet)  
2. **Packet Details Pane** – shows protocol layers (Ethernet, IP, TCP/UDP, etc.)  
3. **Packet Bytes Pane** – shows raw bytes in hex + ASCII  

---

## 3️⃣ Packet Capturing Basics

### ✔ Capture Options
You can select:
- Specific interface (WiFi/Ethernet)  
- Promiscuous Mode (captures all packets)  
- Monitor Mode (Wi-Fi sniffing, if supported)  

### ✔ Capture File Operations
- **Save as .pcap / .pcapng**  
- **Merge files**  
- **Export packets**  
- **View capture file properties**  
  - Packet count  
  - Capture duration  
  - Data size  
  - Interface type  
  - OS and Wireshark version  

---

## 4️⃣ Packet Flow + Directions

Each packet shows:
- **Source IP → Destination IP**  
- Transport-layer info (TCP flags, UDP length, ports)  
- Protocol (HTTP, DNS, TLS, ARP, DHCP, FTP, etc.)

Understanding packet direction helps in:
- Identifying client vs server  
- Following TCP handshakes  
- Detecting anomalies (e.g., SYN floods)

---

## 5️⃣ Packet Navigation Techniques

### ✔ Follow TCP/UDP Stream
Right-click → **Follow → TCP Stream**

This reconstructs:
- HTTP requests  
- Login attempts  
- API calls  
- Text-based protocols  

### ✔ Time Sequence Graphs
Helps analyze:
- Latency  
- Throughput  
- Retransmissions  
- Sequence number behavior  

---

## 6️⃣ Display Filters (MOST IMPORTANT)

Wireshark filters are case-sensitive.  
These allow you to isolate the exact packets you need.

### 🔹 Common Protocol Filters
| Protocol | Filter |
|----------|--------|
| HTTP | `http` |
| DNS | `dns` |
| TCP | `tcp` |
| UDP | `udp` |
| TLS/SSL | `tls` |
| ICMP | `icmp` |

---

### 🔹 IP-Based Filters
ip.addr == 192.168.1.10
ip.src == 10.0.0.5
ip.dst == 8.8.8.8


---

### 🔹 TCP/UDP Port Filters
tcp.port == 80
udp.port == 53
tcp.dstport == 443
udp.srcport == 67


---

### 🔹 Filtering by HTTP
http.request
http.response
http contains "login"


---

### 🔹 Filtering by Errors
tcp.flags.reset == 1
tcp.analysis.retransmission
tcp.analysis.lost_segment


---

## 7️⃣ Statistics & Tools

Wireshark provides powerful analysis tools:

### ✔ Statistics Panel Includes
- Protocol hierarchy  
- Conversations (IP ↔ IP, TCP ↔ TCP)  
- Endpoints  
- Packet lengths  
- I/O graph (traffic over time)  

Useful for:
- Detecting port scanning  
- Bandwidth monitoring  
- Identifying top talkers  
- Visualizing attacks (e.g., SYN floods)

---

## 8️⃣ Practical Security Use Cases

### ✔ Detecting Recon / Scanning
- Tons of SYN packets from one IP  
- DNS brute-force attempts  
- ARP scanning patterns

### ✔ Detecting Credential Leaks
- Cleartext HTTP logins  
- FTP, Telnet, POP3 credentials  
- Unencrypted cookies

### ✔ Investigating Malware Behavior
- Strange domain lookups  
- Repeated failed TCP handshakes  
- C2 communication patterns

### ✔ Analyzing PCAPs from THM/Labs
- Follow TCP stream to reconstruct attacks  
- View TLS handshake details  
- Analyze DNS queries from malware  

---

## 9️⃣ Skills Gained (Recruiter-Friendly)

- Ability to analyze live and stored network traffic  
- Understanding of packet structure and OSI/TCP-IP layers  
- Perform protocol-based filtering  
- Identify suspicious traffic patterns  
- Investigate HTTP, DNS, ARP, ICMP, TLS packets  
- Interpret I/O graphs and protocol hierarchies  
- Comfortable with packet-level navigation and analysis  

This forms a strong foundation for:
✔ Network Security  
✔ Web Hacking  
✔ Incident Response  
✔ Malware Traffic Analysis  

---


