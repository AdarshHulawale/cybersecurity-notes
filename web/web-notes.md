# How The Web Works – TryHackMe Notes

## DNS (Domain Name System)

DNS converts human-readable domain names into IP addresses.

### Domain Structure
- TLD (Top-Level Domain)
- ccTLD (Country Code TLD)
- gTLD (Generic TLD)
- Second-Level Domain
- Subdomain

### DNS Record Types
- A Record
- AAAA Record
- CNAME
- MX
- TXT

### DNS Resolution Flow
Client → Recursive DNS Server → Root DNS Server → Authoritative DNS Server

Used `nslookup` to query DNS records.

---

## HTTP & HTTPS

- HTTP is stateless and unencrypted
- HTTPS uses TLS/SSL for secure communication

### HTTP Methods
- GET
- POST
- PUT
- DELETE

### Status Code Categories
- 1xx – Informational
- 2xx – Success
- 3xx – Redirection
- 4xx – Client Errors
- 5xx – Server Errors

Common Codes:
200, 201, 301, 302, 400, 401, 404, 405, 500, 503

---

## URL Structure

A URL consists of:
- Scheme
- User
- Host (Domain)
- Port
- Path
- Query String
- Fragment

---

## Headers & Cookies

### Request Headers
- Host
- User-Agent
- Content-Length
- Accept-Encoding
- Cookie

### Response Headers
- Set-Cookie
- Cache-Control
- Content-Type
- Content-Encoding

Cookies store session-related data and are sent with future requests.

---

## Web Security Concepts

### Sensitive Data Exposure
Occurs when confidential data is improperly protected.

### HTML Injection
Unsanitized user input is rendered as HTML.

Performed a lab where malicious HTML was injected to display an external hyperlink.

---

## Web Infrastructure

- Web servers & virtual hosts
- Static vs Dynamic content
- Load balancing (Round Robin)
- CDN (Content Delivery Network)
- Databases
- WAF (Web Application Firewall)
