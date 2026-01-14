# Networking Fundamentals 🌐

This README contains my notes from completing the Networking Fundamentals module. These concepts form the backbone of cybersecurity, helping understand how devices communicate and how data moves across networks.

---

## What is Networking?
Networking is the practice of connecting devices so they can communicate and share data.

## What is the Internet?
The Internet is a global network of interconnected networks that communicate using standard protocols.

---

## Identifying Devices on a Network

### IP Address
An IP address uniquely identifies a device on a network.
- IPv4 has 2^32 possible addresses
- IPv6 has 2^128 possible addresses

### MAC Address
A MAC address is a 12-character hexadecimal value.
- First 6 characters identify the manufacturer
- Last 6 characters are a unique device identifier
- MAC addresses can be spoofed (MAC spoofing), which can be used to bypass firewalls

---

## ICMP and Ping
Ping uses ICMP (Internet Control Message Protocol) to test connectivity between devices.

Syntax:
ping <IP address or domain>

---

## Local Area Network (LAN)

### LAN Topologies
- Star topology
- Bus topology
- Ring topology
- Other hybrid topologies

---

## Subnetting Basics
Subnetting divides networks into smaller parts for efficient communication.
- Network address
- Host address
- Default gateway

---

## ARP (Address Resolution Protocol)
ARP resolves IP addresses to MAC addresses.
It works using:
- ARP Request
- ARP Reply

---

## DHCP (Dynamic Host Configuration Protocol)
DHCP automatically assigns IP configuration to devices using four steps:
1. DHCP Discover
2. DHCP Offer
3. DHCP Request
4. DHCP Acknowledgement

---

## OSI Model (Open Systems Interconnection)

1. Physical Layer
2. Data Link Layer
   - Uses Network Interface Card (NIC)
3. Network Layer
   - Routing protocols: OSPF, RIP
   - Determines shortest, fastest, and most reliable path
4. Transport Layer
   - TCP: reliable, connection-oriented, error-checking
   - UDP: fast, unreliable, stateless
5. Session Layer
6. Presentation Layer
   - Translation and encryption (HTTPS)
7. Application Layer
   - DNS

---

## Packets and Frames
- A packet is a unit of data at the Network layer
- A frame is a packet encapsulated at the Data Link layer
- Frame headers include source MAC, destination MAC, TTL, checksum

---

## TCP/IP Model
The TCP/IP model has four layers:
1. Application
2. Transport
3. Internet
4. Network Interface

### TCP Three-Way Handshake
- SYN
- SYN-ACK
- ACK

### TCP Headers Include
- Source port and destination port
- Source IP and destination IP
- Sequence number and acknowledgment number
- Checksum
- Flags (SYN, ACK, FIN, RST)

Connection termination uses FIN, and connection reset uses RST.

---

## UDP/IP
UDP is fast but unreliable and connectionless.
Headers include:
- Time to Live (TTL)
- Source and destination IP
- Source and destination port
- Data

---

## Ports 101
Port range: 0–65535

Common ports:
- FTP: 21
- SSH: 22
- HTTP: 80
- HTTPS: 443
- SMB: 445
- RDP: 3389

---

## Extending Your Network

### Port Forwarding
Allows external traffic to access internal network services.

### Firewalls
Firewalls control traffic entering a network.
Types:
- Stateful firewall
- Stateless firewall

---

## VPN Basics
VPNs allow networks in different geographical locations to connect securely and privately.

VPN technologies:
- PPP
- PPTP (Point-to-Point Tunneling Protocol)
- IPsec (Internet Protocol Security)

---

## Networking Devices
- Router: connects different networks
- Switch: operates at Layer 2 and Layer 3
- VLAN: logically separates networks within the same physical network

---

## Status
Networking Fundamentals completed.
Next focus: Web, HTTP, and Security Basics.
