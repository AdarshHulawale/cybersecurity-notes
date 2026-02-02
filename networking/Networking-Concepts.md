# 🌐 Networking Basics – Study Notes

These notes cover all the networking fundamentals I learned while completing the TryHackMe Networking Module. The explanations are written in a recruiter-friendly, technically accurate way.

---

## 1️⃣ OSI Model (Open Systems Interconnection)

The OSI Model standardizes how data moves across a network. It has **7 layers**, each with defined responsibilities.

| Layer | Name | Purpose | Common Protocols |
|------|------|----------|------------------|
| 7 | **Application** | User-facing services | HTTP, DNS, FTP, SMTP, IMAP, POP3 |
| 6 | **Presentation** | Data formatting, encryption | SSL/TLS, MIME |
| 5 | **Session** | Establish & manage sessions | RPC, NetBIOS |
| 4 | **Transport** | Reliable/unreliable delivery | TCP, UDP |
| 3 | **Network** | Logical addressing & routing | IP, ICMP |
| 2 | **Data Link** | MAC addressing, frames | Ethernet (802.3), WiFi (802.11) |
| 1 | **Physical** | Electric signals, cabling | Physical medium |

### Key Points Learned:
- Each layer adds its own header (encapsulation).
- Data moves down the OSI layers on the sender side and up on the receiver side.
- Troubleshooting network issues often requires knowing which layer is failing.

---

## 2️⃣ TCP/IP Model

The TCP/IP model is a simplified version of OSI used in real networks today.

| TCP/IP Layer | Corresponding OSI Layers | Components |
|--------------|--------------------------|------------|
| **Application** | 7, 6, 5 | HTTP, FTP, DNS, SMTP, TLS |
| **Transport** | 4 | TCP, UDP, Ports |
| **Internet** | 3 | IP, ICMP, Routing |
| **Link** | 2, 1 | MAC, Ethernet, ARP |

### Key Learning:
- **TCP** provides reliability (3-way handshake, ACKs).  
- **UDP** is faster but unreliable (used in gaming & streaming).

---

## 3️⃣ IP Addressing & Subnets

### Private IPv4 Address Ranges:
- **10.0.0.0 – 10.255.255.255**
- **172.16.0.0 – 172.31.255.255**
- **192.168.0.0 – 192.168.255.255**

### Other Concepts Learnt:
- Difference between **Network ID** and **Host ID**
- Subnet masks and CIDR notation (e.g., /24 = 256 hosts)
- How routers forward packets across networks
- How subnetting helps reduce broadcast traffic

---

## 4️⃣ TCP vs UDP

### **TCP (Transmission Control Protocol)**
- Reliable, connection-oriented  
- Uses **3-way handshake**  
- Guarantees ordered and accurate delivery  
- Uses **segments**

### **UDP (User Datagram Protocol)**
- Fast, connectionless  
- No guarantee of delivery  
- Used for video streaming, gaming, VoIP  
- Uses **datagrams**

---

## 5️⃣ Encapsulation & Data Flow

When data is transmitted:

- Application layer → Data  
- Transport layer → TCP Segment / UDP Datagram  
- Internet layer → IP Packet  
- Link layer → Frame

Each layer adds a header, enabling devices to interpret the data correctly.

---

## 6️⃣ Telnet (Theory + Practical)

Used for interacting with servers directly over TCP.

### Commands Used:
 telnet <IP> <port>

 
### Ports Tested:
- **7** – Echo  
- **13** – Daytime  
- **80** – HTTP  

### Key Learning:
- How servers respond to raw manual requests  
- How to verify open ports without advanced tools  
- How to perform simple banner grabbing using Telnet  

---

## 7️⃣ Tools Used in Networking Module

### 🟦 **Wireshark**
- Captured and analysed packets  
- Inspected TCP handshake, UDP traffic  
- Used filters (`http`, `tcp.port == 80`, etc.)

### 🔶 **tcpdump**
- CLI packet capture tool  
- Useful for remote machine analysis  
- Learned common flags (`-i`, `-n`, `-nn`, `-w`, etc.)

### 🟩 **Nmap**
- Port scanning (SYN Scan, Full Scan)  
- Service enumeration (`-sV`)  
- OS detection (`-O`)  
- Host discovery (`-sn`)  

---

## 8️⃣ Summary of Skills Gained

- Understanding of core networking concepts  
- Hands-on packet capture and analysis  
- Port scanning and service enumeration  
- Ability to identify protocols and traffic patterns  
- Practical experience with foundational security tooling (Wireshark, Nmap, tcpdump)

---

## ✔ Completed Rooms (TryHackMe Networking Module)
- OSI Model  
- TCP/IP Model  
- Subnets  
- DNS in Detail  
- HTTP in Detail  
- Wireshark Basics  
- tcpdump  
- Nmap Live Host Discovery  
- Nmap Port Scanning  
