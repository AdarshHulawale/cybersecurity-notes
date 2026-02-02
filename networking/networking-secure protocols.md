# 🔐 Networking Essentials – Part 3 (Security Protocols & Encryption)

This section covers security-focused networking concepts, including TLS, HTTPS, secure email, SSH, SFTP/FTPS, and VPNs. These are foundational for cybersecurity roles.

---

## 1️⃣ TLS (Transport Layer Security)

TLS is a **cryptographic protocol** that provides secure communication over a network.

### ✔ What TLS Provides
- **Confidentiality** – Encryption of data  
- **Integrity** – Data cannot be modified silently  
- **Authentication** – Verifies server (and optionally client) identity  

---

## 2️⃣ TLS Certificates & Certificate Authorities (CA)

TLS uses **digital certificates** to prove the identity of a server.

### ✔ Certificate Issuing Workflow
1. **Server admin generates a CSR** (Certificate Signing Request).  
2. CSR is submitted to a **Certificate Authority (CA)**.  
3. CA validates ownership and **issues a signed certificate**.  
4. Client browsers trust certificates signed by recognized CAs.

### ✔ Common Certificate Types
- **DV** – Domain Validated  
- **OV** – Organization Validated  
- **EV** – Extended Validation (most trusted)

Browsers check certificates during every HTTPS connection.

---

## 3️⃣ HTTPS = HTTP over TLS

HTTPS is the secure version of HTTP.

### ✔ How HTTPS Works
1. **TCP 3-way handshake** (establish connection)  
2. **TLS handshake** begins  
   - Key exchange  
   - Certificate verification  
   - Session keys generated  
3. **Encrypted HTTP communication** starts  

HTTPS protects against:
- Eavesdropping  
- MITM attacks  
- Packet tampering  

---

## 4️⃣ Secure Versions of Email Protocols

TLS is added to email protocols to provide security.

### ✔ Original (Unsecured)
- **SMTP** – Port 25  
- **POP3** – Port 110  
- **IMAP** – Port 143  

### ✔ Secure Versions (with TLS)
| Protocol | Secure Port | Description |
|----------|-------------|-------------|
| **SMTPS** | 465 | SMTP with implicit TLS |
| **POP3S** | 995 | POP3 with TLS |
| **IMAPS** | 993 | IMAP with TLS |

Email security is important for preventing credential theft and MITM attacks.

---

## 5️⃣ SSH (Secure Shell)

SSH is the secure replacement for Telnet.

### ✔ Why SSH Replaced Telnet
- Telnet sends **all data in cleartext**, including passwords  
- SSH uses **encryption**, making it safe for remote administration  

### ✔ Ports & Syntax
- SSH Default Port: **22**
- Telnet Port: **23**

### ✔ SSH Commands
ssh username@hostname
ssh -X username@hostname # for GUI applications


### ✔ SSH Features
- Secure remote login  
- Encrypted command execution  
- Secure file transfer via SFTP  

---

## 6️⃣ SFTP vs FTPS

Two different secure file transfer methods.

### ✔ SFTP (SSH File Transfer Protocol)
- Uses **SSH** for encryption  
- Port **22**  
- More secure and widely used  

### ✔ FTPS (FTP Secure)
- Uses **TLS**  
- Port **990** (implicit FTPS)  
- Extension of traditional FTP  

Both add confidentiality + integrity to file transfer operations.

---

## 7️⃣ VPN (Virtual Private Network)

A VPN creates a **secure tunnel** between a user and a network.

### ✔ Why VPN is Used
- Encrypts all traffic  
- Hides real IP address  
- Helps remote workers securely access internal company resources  

### ✔ VPN Protocols
- **OpenVPN** (most common)  
- **IPSec**  
- **IKEv2**  
- **WireGuard** (modern, fast)

---

## ✔ Skills Gained (Recruiter-Friendly Summary)

- Strong understanding of TLS, HTTPS, certificates, CAs  
- Knowledge of secure email protocols (SMTPS, POP3S, IMAPS)  
- Clear understanding of SSH vs Telnet  
- Experience with SFTP, FTPS, secure file transfer concepts  
- Understanding of VPN tunneling and encryption models  
- Ability to differentiate secure vs insecure network protocols  
- Strong foundation for upcoming modules: BurpSuite, Web Security, and Network Traffic Analysis  

---

