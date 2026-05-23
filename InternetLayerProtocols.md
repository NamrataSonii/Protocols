# Internet Layer Protocols

> Protocols operating at the Internet layer of the DoD model — responsible for logical addressing, routing, and network-wide communication.

---

## Table of Contents

- [IP — Internet Protocol](#-ip--internet-protocol)
- [ICMP — Internet Control Message Protocol](#-icmp--internet-control-message-protocol)
- [ARP — Address Resolution Protocol](#-arp--address-resolution-protocol)
- [RARP — Reverse Address Resolution Protocol](#-rarp--reverse-address-resolution-protocol)
- [Quick Reference Table](#-quick-reference-table)

---

## IP — Internet Protocol

IP is essentially **the Internet layer itself** — all other protocols at this layer exist to support it.  
Every machine on the network has a **logical (software) address** called an IP address.

### How IP Works

- Receives **segments** from the Host-to-Host layer and fragments them into **packets**
- Examines each packet's **destination IP address**
- Uses a **routing table** to determine the best forwarding path
- Reassembles packets back into segments on the **receiving end**
- Each packet carries both the **sender's** and **recipient's** IP address
- Every **router (Layer 3 device)** uses the destination IP to make routing decisions

```
[Host-to-Host Segments]
         ↓
   IP fragments into Packets
         ↓
   Assigns src IP + dst IP
         ↓
   Router reads dst IP → forwards via best path
         ↓
   Destination reassembles packets → Segments
```

>  Unlike Network Access layer protocols that handle only **physical/local links**, IP has a complete view of the **entire network**.

---

## ICMP — Internet Control Message Protocol

ICMP operates at the **Network layer** and acts as a **management and messaging service** for IP.  
Its messages are carried as **IP datagrams**.

### Characteristics

- Provides hosts with information about **network problems**
- Messages are **encapsulated within IP datagrams**

### Common ICMP Messages

| Message | Description |
|---------|-------------|
| **Destination Unreachable** | Target host or network cannot be reached |
| **Buffer Full** | Router memory buffer has no available space |
| **Hops Exceeded** | Packet's TTL (Time to Live) has expired in transit |
| **Ping** | Tests reachability and round-trip time to a host |
| **Traceroute** | Traces the full path packets take to a destination |

> **Ping** and **Traceroute** — two of the most essential network diagnostic tools — are both powered by ICMP.

---

## ARP — Address Resolution Protocol

ARP resolves a known **IP address → Hardware (MAC) address** on the local network.

### How ARP Works

When IP needs to deliver a datagram, it must know the **hardware address** of the destination on the local network.

```
IP needs to send a datagram
          ↓
Check ARP cache for MAC address
          ↓
Not found?
          ↓
Broadcast ARP Request to local network:
"Who has IP 192.168.1.5? Reply with your MAC address"
          ↓
Target machine replies with its MAC address
          ↓
ARP cache is updated
          ↓
IP delivers the datagram
```

> ARP acts as **IP's detective** — translating **logical (IP) addresses** into **physical (MAC) addresses** so data can be delivered on the local network.

---

## RARP — Reverse Address Resolution Protocol

RARP is the **opposite of ARP** — used by **diskless machines** that know their MAC address but have no way of knowing their IP address.

### How RARP Works

```
Diskless machine powers on
          ↓
Knows its MAC address — but NOT its IP address
          ↓
Broadcasts RARP Request:
"My MAC is AA:BB:CC:DD:EE:FF — what is my IP address?"
          ↓
RARP Server looks up the MAC in its table
          ↓
RARP Server replies with the assigned IP address
          ↓
Machine now has its complete network identity 
```

### ARP vs RARP

| Protocol | Known | Discovers | Direction |
|----------|-------|-----------|-----------|
| **ARP** | IP Address | MAC Address | IP → MAC |
| **RARP** | MAC Address | IP Address | MAC → IP |

---

## Quick Reference Table

| Protocol | Full Name | Purpose | Key Feature |
|----------|-----------|---------|-------------|
| **IP** | Internet Protocol | Packet addressing & routing | Logical addressing, best-path routing |
| **ICMP** | Internet Control Message Protocol | Network diagnostics & error reporting | Ping, Traceroute, error messages |
| **ARP** | Address Resolution Protocol | Resolves IP → MAC address | Broadcasts on local network |
| **RARP** | Reverse Address Resolution Protocol | Resolves MAC → IP address | Used by diskless machines |

---

## Contributing

Found an error or want to add more detail? Contributions are welcome!  
Please open an **issue** or submit a **pull request**.

---
