# Network Protocols Reference

> A comprehensive reference guide covering **Application, Transport, and Internet layer protocols** used in modern networking and the internet.  
> This repo is organized into two focused documents — use the links below to navigate.

---

## What's Covered

### [Application & Transport Layer Protocols](./application-transport-protocols.md)

Covers protocols that applications and users interact with directly — from file transfer to email, web browsing, and security.

| Protocol | Purpose |
|----------|---------|
| **TCP** | Reliable, connection-oriented data delivery |
| **UDP** | Fast, connectionless data delivery |
| **FTP** | File transfer over IP |
| **SFTP** | Secure file transfer via SSH |
| **TFTP** | Simple, lightweight file transfer |
| **NFS** | Cross-platform file system sharing |
| **SMTP** | Sending emails |
| **POP3** | Receiving/downloading emails |
| **IMAP4** | Server-side email management |
| **HTTP** | Web browser ↔ server communication |
| **HTTPS** | Secure web communication |
| **DHCP** | Automatic IP address assignment |
| **TLS/SSL** | Encrypted data transfer |
| **SSH** | Secure remote access & file transfer |
| **Telnet** | Remote access (legacy, unsecured) |
| **IGMP** | IP multicast session management |

---

### [Internet Layer Protocols](./InternetLayerProtocols.md)

Covers protocols responsible for logical addressing, packet routing, and hardware address resolution across networks.

| Protocol | Purpose |
|----------|---------|
| **IP** | Logical addressing & best-path packet routing |
| **ICMP** | Network diagnostics & error reporting (Ping, Traceroute) |
| **ARP** | Resolves IP address → MAC address |
| **RARP** | Resolves MAC address → IP address (diskless machines) |


---

##  DoD Model — Where Each Protocol Lives

```
┌─────────────────────────────────────────────┐
│         Process / Application Layer         │
│  HTTP · HTTPS · FTP · SFTP · TFTP · SMTP   │
│  POP3 · IMAP4 · DHCP · Telnet · SSH        │
│  TLS/SSL · NFS · IGMP                       │
├─────────────────────────────────────────────┤
│           Host-to-Host Layer                │
│              TCP · UDP                      │
├─────────────────────────────────────────────┤
│             Internet Layer                  │
│          IP · ICMP · ARP · RARP             │
├─────────────────────────────────────────────┤
│           Network Access Layer              │
│         Ethernet · Token Ring · ...         │
└─────────────────────────────────────────────┘
```

## Contributing

Contributions are welcome! You can:
- Add new protocols
- Fix errors or outdated information
- Improve diagrams or examples
- Suggest better organization

Please open an **issue** or submit a **pull request**.

---
