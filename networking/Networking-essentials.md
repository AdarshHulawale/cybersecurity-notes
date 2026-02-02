# 🌐 Networking Essentials – Part 2 (Advanced Fundamentals)

These notes cover the advanced networking concepts I learned in the TryHackMe Networking Essentials module. The explanations are technically accurate and recruiter-friendly.

---

## 1️⃣ DHCP (Dynamic Host Configuration Protocol)

DHCP automatically assigns network configuration to client devices.

### ✔ What DHCP Provides
- IP Address  
- Subnet Mask  
- Default Gateway  
- DNS Server  
- Lease Time  

### ✔ Ports Used
- **UDP 67 → Server**
- **UDP 68 → Client**

### ✔ DHCP Process (DORA)
1. **Discover** – Client broadcasts to `255.255.255.255` using source IP `0.0.0.0`
2. **Offer** – Server responds with an available IP
3. **Request** – Client requests the offered IP
4. **Acknowledge** – Server confirms assignment

Understanding DHCP is crucial for troubleshooting IP address issues in networks.

---

## 2️⃣ ARP (Address Resolution Protocol)

ARP resolves a **known IP address** to a **MAC address**.

### ✔ Why ARP Exists
Devices communicate on a LAN using MAC addresses.  
If a device knows the IP but not the MAC, it uses ARP.

### ✔ Key Concepts
- ARP Request = Broadcast → `FF:FF:FF:FF:FF:FF`
- ARP Reply = Unicast back to the requester
- Used only on local networks

ARP tables can be viewed using:
arp -a


---

## 3️⃣ ICMP (Internet Control Message Protocol)

ICMP is used for **diagnostics and troubleshooting**.

### 📌 Tools Using ICMP
- **ping** – Tests host reachability & latency  
- **traceroute (Linux)**  
- **tracert (Windows)**  

### What ICMP Helps with:
- Network debugging  
- Finding hops between hosts  
- Identifying packet loss  

---

## 4️⃣ Routing Algorithms

Routers use algorithms to determine the best path for packet delivery.

### ✔ Interior Gateway Protocols (IGP)
- **OSPF** (Open Shortest Path First) – Fast, modern, metric: cost  
- **EIGRP** (Enhanced Interior Gateway Routing Protocol) – Cisco proprietary, metric: bandwidth + delay  
- **RIP** (Routing Information Protocol) – Old, metric: hop count  

### ✔ Exterior Gateway Protocol
- **BGP** (Border Gateway Protocol) – The protocol that runs the entire internet; used between autonomous systems.

Routers choose routes based on metrics like speed, cost, or reliability.

---

## 5️⃣ NAT (Network Address Translation)

NAT allows private IP addresses to access the internet.

### ✔ Why NAT?
Private IPs **cannot** access the internet directly.

NAT translates:
- **Private → Public IP (outbound)**
- **Public → Private IP (inbound)**

This improves:
- Security  
- Scalability  
- IP address conservation  

---

## 6️⃣ DNS (Domain Name System)

DNS converts human-readable domain names into IP addresses.

### ✔ Common DNS Record Types
| Record | Meaning | Purpose |
|--------|----------|----------|
| **A** | Address | Maps hostname → IPv4 |
| **AAAA** | IPv6 Address | Maps hostname → IPv6 |
| **CNAME** | Canonical Name | Alias for another domain |
| **MX** | Mail Exchange | Directs email traffic |

### Useful Commands:
whois domain.com
nslookup domain.com
dig domain.com


---

## 7️⃣ Email Protocols

### ✔ SMTP (Simple Mail Transfer Protocol)
Used for **sending** mail.

- **Port:** 25 (TCP)
- Commands learned:
  - `HELO` / `EHLO`
  - `MAIL FROM`
  - `RCPT TO`
  - `DATA`
  - `. ` (single dot = end of message)

### ✔ POP3 (Post Office Protocol v3)
Used to **download** emails.  
- **Port:** 110 (TCP)

### ✔ IMAP (Internet Message Access Protocol)
Used to **manage email on the server**  
- **Port:** 143 (TCP)

---

## 8️⃣ Web Protocols

### ✔ HTTP
- Port **80**  
- Unencrypted  

### ✔ HTTPS
- Port **443**  
- Uses TLS encryption  

---

## 9️⃣ Telnet (Manual Testing of Servers)

Telnet lets you manually test TCP connections.

### Example:
telnet <IP> 80
GET /index.html HTTP/1.1
Host: <domain>


Useful for:
- Banner grabbing  
- Testing HTTP manually  
- Understanding raw communication  

---

## 🔟 Common Protocols & Default Ports

| Protocol | Port | Transport |
|----------|------|-----------|
| Telnet | 23 | TCP |
| DNS | 53 | UDP/TCP |
| HTTP | 80 | TCP |
| HTTPS | 443 | TCP |
| FTP | 21 | TCP |
| SMTP | 25 | TCP |
| POP3 | 110 | TCP |
| IMAP | 143 | TCP |

---

## ✔ Skills Gained (Recruiter-Friendly Summary)

- Strong understanding of core networking services (DHCP, ARP, ICMP, DNS)
- Ability to troubleshoot using ping, traceroute, nslookup, whois
- Knowledge of email protocols and raw SMTP communication
- Understanding of routing algorithms like OSPF, BGP, RIP
- Familiarity with NAT and how private networks access the internet
- Manual testing of HTTP and SMTP using Telnet
- Port & protocol identification skills essential for cybersecurity

---


ARP tables can be viewed using:

