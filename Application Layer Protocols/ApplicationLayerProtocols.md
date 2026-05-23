# 📡 Network Protocols Reference

> A comprehensive reference guide covering key Application, Transport, and Network layer protocols used in modern networking and the internet.

---

## Table of Contents

- [Transport Layer Protocols](#-transport-layer-protocols)
- [File Transfer Protocols](#-file-transfer-protocols)
- [Email Protocols](#-email-protocols)
- [Web Protocols](#-web-protocols)
- [Security Protocols](#-security-protocols)
- [Network Management Protocols](#-network-management-protocols)

---

## Transport Layer Protocols

### TCP — Transmission Control Protocol

TCP takes large blocks of information from an application and breaks them into **segments**. It numbers and sequences each segment so that the destination's TCP process can reassemble them in the correct order.

**Key Features:**
- Connection-oriented
- Reliable delivery with acknowledgments
- Sequencing and error checking
- Retransmits unacknowledged segments
- Higher overhead due to complexity

---

### UDP — User Datagram Protocol

UDP is a **lightweight, connectionless** protocol that uses fewer network resources than TCP.

**Key Features:**
- Fast and low overhead
- Suitable for speed-critical applications (e.g., SNMP, NFS)
- No sequencing, acknowledgments, or error recovery
- Unreliable — does not confirm data arrival

> **Use UDP when:** Speed > Reliability (e.g., video streaming, DNS, gaming)

---

## File Transfer Protocols

### FTP — File Transfer Protocol

Allows file transfer between any two machines over an IP network.

**Capabilities:**
- Directory listing and manipulation
- File copying between hosts
- Access to both files and directories

**Limitations:**
- Cannot execute remote files as programs
- No encryption — sends data in plain text

---

### SFTP — Secure File Transfer Protocol

SFTP transfers files over an **encrypted SSH session**, providing security that standard FTP lacks.

| Feature | FTP | SFTP |
|--------|-----|------|
| Encryption | No | Yes |
| Uses SSH | No | Yes |
| File Transfer | Yes | Yes |

---

### TFTP — Trivial File Transfer Protocol

A stripped-down version of FTP — simple, fast, but limited.

**Characteristics:**
- No directory browsing
- Sends smaller data blocks than FTP
- No authentication → **insecure**
- Rarely supported due to security risks

---

### NFS — Network File System

Allows **two different file systems** (e.g., Windows NT and UNIX) to interoperate seamlessly.

**How it works:**
- NFS server software runs on one machine (e.g., NT server)
- NFS client software runs on another (e.g., UNIX host)
- A portion of the server's RAM transparently stores files for cross-platform access
- Both user types access files using their own native file systems

---

## 📧 Email Protocols

### SMTP — Simple Mail Transfer Protocol

Used to **send** emails. Uses a spooled/queued delivery method.

```
[Sender] --SMTP--> [Mail Server Queue] --SMTP--> [Recipient's Server]
```

> SMTP = **Send** | POP3 = **Receive**

---

### POP3 — Post Office Protocol v3

Used to **receive/download** emails from a mail server.

**Behavior:**
- Downloads all messages to the local device
- No selective download
- Once downloaded, local management is allowed

---

### IMAP4 — Internet Message Access Protocol v4

A more advanced alternative to POP3 with **server-side management**.

**Advantages over POP3:**
- Preview headers without downloading full email
- Download partial messages
- Server-side folder organization
- Message searching
- Strong authentication (e.g., Kerberos)

---

## Web Protocols

### HTTP — Hypertext Transfer Protocol

Manages communication between **web browsers and web servers**.

- Opens the correct resource when you click a link
- Foundation of data exchange on the Web

---

### HTTPS — Hypertext Transfer Protocol Secure

A **secure version of HTTP** for encrypted browser-server communication.

**Used for:**
- Form submissions
- Authentication / Sign-in
- Online purchases and reservations
- Encrypting HTTP messages

---

### DHCP — Dynamic Host Configuration Protocol

Automatically assigns **IP addresses** to hosts on a network.

**vs BootP:**

| Feature | DHCP | BootP |
|---------|------|-------|
| Dynamic IP assignment | Yes | NO (manual table) |
| Boots OS over network | No | Yes |
| Scalability | Yes Large networks | Limited |

---

## Security Protocols

### TLS — Transport Layer Security

A cryptographic protocol that enables **secure online data transfer**.

**Used in:**
- Web browsing (HTTPS)
- Instant messaging
- Internet faxing

>  TLS is the modern successor to **SSL (Secure Sockets Layer)**

---

### SSH — Secure Shell

Sets up a **secure, encrypted session** over a standard TCP/IP connection.

**Capabilities:**
- Login to remote systems
- Run programs on remote systems
- Move files between systems (used by SFTP)

>  SSH replaces Telnet when security is required

---

### Telnet

Allows a user (**Telnet client**) to access resources on a remote machine (**Telnet server**).

 **Security Warning:**
- No encryption
- No security features
- **Being replaced by SSH** in modern environments

---

## Network Management Protocols

### IGMP — Internet Group Management Protocol

Used for managing **IP multicast sessions**.

**Functions:**
- Sends messages to reveal multicast group membership
- Hosts use IGMP to join or leave multicast groups
- Tracks active multicast streams

---

##  Quick Reference Table

| Protocol | Layer | Purpose | Secure? |
|----------|-------|---------|---------|
| TCP | Transport | Reliable data delivery | — |
| UDP | Transport | Fast, connectionless delivery | — |
| FTP | Application | File transfer | No |
| SFTP | Application | Secure file transfer | Yes |
| TFTP | Application | Simple file transfer | No |
| NFS | Application | Cross-platform file sharing | — |
| SMTP | Application | Send email | — |
| POP3 | Application | Receive email (download) | — |
| IMAP4 | Application | Receive email (server-side) | — |
| HTTP | Application | Web communication | No |
| HTTPS | Application | Secure web communication | Yes |
| DHCP | Application | IP address assignment | — |
| TLS/SSL | Session | Encrypted data transfer | Yes |
| SSH | Application | Secure remote access | Yes |
| Telnet | Application | Remote access (legacy) | No |
| IGMP | Network | IP multicast management | — |

---

## Contributing

Contributions are welcome! Feel free to:
- Add new protocols
- Fix errors or outdated information
- Improve explanations or examples

Please open an issue or submit a pull request.

