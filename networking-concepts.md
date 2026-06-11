# 🌐 Networking Notes

> Easy-to-understand notes covering key networking concepts, protocols, and models.

---

## 📡 Basic Networking Concepts

### VPN (Virtual Private Network)
- Creates a **secure, encrypted tunnel** over the internet
- Used to protect your data and hide your IP address
- Example: Employees working from home access company resources via VPN

### DNS (Domain Name System)
- Converts **human-readable names → IP addresses**
- Example: `google.com` → `142.250.190.78`
- Think of it like a **phone book for the internet**

### DHCP (Dynamic Host Configuration Protocol)
- Automatically **assigns IP addresses** to new devices from a pool
- When you connect to Wi-Fi, DHCP gives your device an IP address automatically
- No need to manually set an IP!

### NAT (Network Address Translation)
- **Modifies the source or destination IP** as data passes through a Router
- Allows multiple devices in your home to share **one public IP**
- Example: Your router has 1 public IP → all your devices (phone, laptop, TV) share it

```
 [ Device 1 ] ──┐
 [ Device 2 ] ──┤──► [ Router / NAT ] ──► 🌐 Internet
 [ Device 3 ] ──┘
   (Private IPs)        (Single Public IP)
```

### VLAN (Virtual LAN)
- **Admins** use VLANs to create **logically separated networks** within a physical network
- Example: HR and Engineering departments share the same physical switches but are on separate VLANs — they can't see each other's traffic

---

## 🔧 Network Devices

### Routers
- Connects your **local network → Internet**
- Also acts as:
  - 🔥 **Firewall** – blocks unwanted traffic
  - 📋 **DHCP server** – assigns IP addresses

### Switches
- Connects **multiple devices within the same network**
- Example: Connecting computers in an office together

### Firewall
- A **security device** that monitors **incoming & outgoing traffic**
- Blocks suspicious or unauthorized connections
- Think of it as a **security guard** for your network

---

## 📦 Protocols

| Protocol | Full Name | Purpose |
|----------|-----------|---------|
| **ARP** | Address Resolution Protocol | Maps IP address → MAC address |
| **ICMP** | Internet Control Message Protocol | Error reporting & diagnostics (e.g., `ping`) |
| **VoIP** | Voice over Internet Protocol | Voice calls over the internet instead of phone lines |
| **BGP** | Border Gateway Protocol | Manages how data is routed between different networks on the internet |

### ARP – Address Resolution Protocol
- Your device knows the IP but needs the **MAC address** to send data on a local network
- ARP says: *"Who has IP 192.168.1.5? Tell me your MAC address!"*

### ICMP – Internet Control Message Protocol
- Used for **error reporting and diagnostics**
- The `ping` command uses ICMP → tests if a device is reachable

### VoIP – Voice over Internet Protocol
- Transmits **voice communication over the Internet** instead of traditional phone lines
- Examples: WhatsApp calls, Zoom, Google Meet

### BGP – Border Gateway Protocol
- The "postal system" of the internet
- Manages how data is **routed between different networks** (like between ISPs)

---

## 🏠 Network Types

### LAN (Local Area Network)
- Network for a **small geographic area**
- Examples: Home Wi-Fi, office network, school lab

### WAN (Wide Area Network)
- Network covering a **large geographic area**
- Can include **multiple LANs**
- The biggest example: **The Internet** 🌍

```
 [ LAN 1: Office A ] ─────┐
                           ├──► WAN (Internet) ──► Global Connection
 [ LAN 2: Office B ] ─────┘
```

---

## 🔖 Addresses

### MAC Address (Media Access Control)
- A **unique identifier** assigned to every network interface card (NIC)
- Operates at the **Data Link Layer (Layer 2)** of the OSI model
- Ensures data is sent to the **correct physical device**
- Format: `AA:BB:CC:DD:EE:FF` (6 pairs of hex digits)

> 💡 Think of MAC address as your device's **permanent ID card**, and IP address as your **current home address** (can change).

---

## 🧱 OSI Model — 7 Layers

The **OSI (Open System Interconnection) Model** is a framework that explains how data travels from one device to another over a network.

```
┌─────────────────────────────────────────────────────┐
│  Layer 7 │ Application  │ User-facing apps (HTTP, FTP)│
├──────────┼──────────────┼────────────────────────────┤
│  Layer 6 │ Presentation │ Encrypt & format data       │
├──────────┼──────────────┼────────────────────────────┤
│  Layer 5 │ Session      │ Manage communication state  │
├──────────┼──────────────┼────────────────────────────┤
│  Layer 4 │ Transport    │ Reliable delivery (TCP/UDP) │
├──────────┼──────────────┼────────────────────────────┤
│  Layer 3 │ Network      │ Routing via IP addresses    │
├──────────┼──────────────┼────────────────────────────┤
│  Layer 2 │ Data Link    │ MAC address, data frames    │
├──────────┼──────────────┼────────────────────────────┤
│  Layer 1 │ Physical     │ Cables, wireless signals    │
└─────────────────────────────────────────────────────┘
```

### Layer 1 – Physical Layer
- Deals with actual **hardware**: cables, wireless signals
- Just raw bits (0s and 1s) transmitted as electrical/light/radio signals

### Layer 2 – Data Link Layer
- Ensures **reliable connection between two devices**
- Manages **MAC addresses** and **data frames**

### Layer 3 – Network Layer
- **Routes data** to the correct destination based on **IP address**
- Devices: Routers

### Layer 4 – Transport Layer
- Ensures **reliable end-to-end communication**
- Provides **flow control** and **error correction**
- Protocols: **TCP** (reliable) and **UDP** (fast, no guarantee)

### Layer 5 – Session Layer
- **Manages and maintains** the state of a communication session
- Opens, maintains, and closes sessions between devices

### Layer 6 – Presentation Layer
- **Formats and encrypts** data for the Application layer
- Example: SSL/TLS encryption happens here

### Layer 7 – Application Layer
- Interacts directly with **software applications**
- Provides **network services** to the user
- Examples: HTTP, FTP, DNS, SMTP (email)

---

## 🔀 Advanced Networking

### NFC (Near Field Communication)
- Share data over **very short distances (~10 cm)**
- Used for **contactless payments** (Google Pay, Apple Pay)

### MPLS (Multiprotocol Label Switching)
- A **routing technique** used in large networks to **improve speed**
- Adds labels to data packets so routers don't need to look up IP addresses every time

### SD-WAN (Software-Defined Wide Area Network)
- A **modern approach to managing WAN**
- Uses **software to control the flow of data** across network connections
- More flexible and cost-effective than traditional WAN

### Proxy Server
- Acts as an **intermediary between your device and the internet**
- Hides your real IP address
- Can also **filter** or **cache** content

```
 [ Your Device ] ──► [ Proxy Server ] ──► 🌐 Internet
                           ↑
                    (Hides your IP,
                     can filter content)
```

---

### QoS (Quality of Service)
- A technique used to **manage network traffic**
- Ensures **critical applications** (like video calls) get **high priority**
- High-priority traffic is sent with **low latency** (less delay)
- Example: In a hospital, medical monitoring data gets priority over regular internet browsing

---

## 🧠 Quick Reference Cheat Sheet

| Term | Simple Definition |
|------|-------------------|
| IP Address | Your device's address on the network |
| MAC Address | Your device's permanent hardware ID |
| DNS | Phone book — name → IP |
| DHCP | Auto-assigns IP addresses |
| NAT | Many devices share one public IP |
| VPN | Secure encrypted tunnel |
| Firewall | Security guard for your network |
| Router | Connects local network to internet |
| Switch | Connects devices within same network |
| LAN | Small local network |
| WAN | Large wide-area network |
| VLAN | Virtual separation in a network |
| Proxy | Middleman between you and internet |
| ARP | IP → MAC address lookup |
| ICMP | Ping / error messages |
| BGP | Routing between big networks |
| QoS | Priority management for traffic |
| VoIP | Voice calls over internet |
| NFC | Tap-to-pay, short range data |
| MPLS | Fast routing with labels |
| SD-WAN | Software-controlled WAN |

---

> 📝 **Study Tip:** Draw the OSI model from memory every day until you can do it without looking. The 7 layers are the foundation of almost all networking concepts!
