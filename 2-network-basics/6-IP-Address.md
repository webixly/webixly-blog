# 🌐 IP Address (Internet Protocol Address)

## ⚙️ What Is an IP Address?

An **IP Address** (Internet Protocol Address) is a **unique logical identifier** assigned to each device connected to a network.  
It allows devices to **send and receive data** across local and global networks (like the Internet).  

Think of it as the **digital address** of your device — just like a home address used to deliver mail.

---

## 🧠 IP Address in the OSI Model

- Operates at **Layer 3 – Network Layer**
- Responsible for **logical addressing** and **routing** data between different networks.

---

## 🧩 Types of IP Versions

| Version | Name | Address Length | Example | Notes |
|----------|------|----------------|----------|-------|
| **IPv4** | Internet Protocol v4 | 32 bits | `192.168.1.10` | Most common, limited to ~4.3 billion addresses |
| **IPv6** | Internet Protocol v6 | 128 bits | `2001:0db8:85a3:0000:0000:8a2e:0370:7334` | Designed to replace IPv4, supports huge address space |

---

## 📘 IPv4 Address Structure

IPv4 addresses are made up of **4 octets (8 bits each)**, separated by dots.

### Example:

192.168.1.10


Each octet ranges from **0 to 255**, because 8 bits can represent 256 values.

---

## 📦 IP Address Classes

| Class | Range | Default Subnet Mask | Typical Use |
|--------|--------|----------------------|--------------|
| **A** | 1.0.0.0 – 126.255.255.255 | 255.0.0.0 | Large networks |
| **B** | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 | Medium networks |
| **C** | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 | Small networks |
| **D** | 224.0.0.0 – 239.255.255.255 | — | Multicasting |
| **E** | 240.0.0.0 – 255.255.255.255 | — | Experimental |

💡 **Note:** 127.0.0.1 is reserved for **loopback (localhost)**.

---

## 🏠 Private vs Public IP Addresses

| Type | Range | Usage |
|------|--------|--------|
| **Private IPs** | `10.0.0.0 – 10.255.255.255`  <br> `172.16.0.0 – 172.31.255.255`  <br> `192.168.0.0 – 192.168.255.255` | Used inside local networks (LAN) |
| **Public IPs** | All others | Used on the Internet, globally unique |

💡 Private IPs are **not routable** on the Internet — routers use **NAT (Network Address Translation)** to connect private networks to public ones.

---

## 🧮 Subnetting Basics

Subnetting divides a network into smaller parts for **efficiency and security**.

Example:  
`192.168.1.0/24` → `/24` means **24 bits for the network** and **8 bits for hosts**, allowing 254 usable IPs.

| CIDR | Hosts Available | Subnet Mask |
|------|------------------|--------------|
| /8 | 16,777,214 | 255.0.0.0 |
| /16 | 65,534 | 255.255.0.0 |
| /24 | 254 | 255.255.255.0 |

---

## 🔁 Dynamic vs Static IP

| Type | Description | Example |
|------|--------------|----------|
| **Dynamic IP** | Assigned automatically by **DHCP server** | Changes over time |
| **Static IP** | Manually configured | Fixed and permanent |

---

## 🧭 How IP Works with MAC (ARP)

When a device wants to send data:
1. It uses the **destination IP** to find the **MAC address** via **ARP (Address Resolution Protocol)**.  
2. Data is then encapsulated in an **Ethernet frame** with both IP and MAC information.  
3. Routers use the IP to **forward packets** to the next network.

---

## 🔒 In Cybersecurity

Understanding IP addressing is critical for:
- **Network scanning and reconnaissance**  
- **Firewall configuration**  
- **Intrusion detection**  
- **VPNs and tunneling protocols**

Attackers often use **IP spoofing** to hide identity or perform DDoS attacks.

---

## 🧰 Common Commands

| OS | Command | Description |
|----|----------|-------------|
| **Windows** | `ipconfig` | View IP configuration |
| **Linux/macOS** | `ifconfig` or `ip addr` | Display network interfaces |
| **All OS** | `ping [IP]` | Test connectivity |
| **All OS** | `traceroute [IP]` or `tracert [IP]` | Trace route to a destination |

---

> 💡 **Tip:**  
> Always plan your IP address scheme carefully — poor planning can cause IP conflicts, routing errors, or security issues.
