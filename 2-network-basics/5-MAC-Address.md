# 🧩 MAC Address (Media Access Control Address)

## ⚙️ What Is a MAC Address?

A **MAC Address** (Media Access Control Address) is a **unique identifier** assigned to a **network interface card (NIC)** by its manufacturer.  
It operates at the **Data Link Layer (Layer 2)** of the **OSI Model** and is used to **identify devices on a local network (LAN)**.

Every device connected to a network — computer, router, printer, or smartphone — has its own MAC address.

---

## 🔢 Structure of a MAC Address

A MAC address consists of **48 bits (6 bytes)**, usually written as **12 hexadecimal digits**.

### Example:

00:1A:2B:3C:4D:5E

or sometimes:
00-1A-2B-3C-4D-5E

### Breakdown:
| Section | Bits | Description |
|----------|------|-------------|
| **OUI (Organizationally Unique Identifier)** | First 24 bits | Identifies the manufacturer (e.g., Intel, Cisco) |
| **Device Identifier (NIC Specific)** | Last 24 bits | Unique to each device made by that manufacturer |

---

## 🔍 How MAC Addresses Work

When devices communicate on a local network:

1. The sender uses **ARP (Address Resolution Protocol)** to find the MAC address of the destination IP.  
2. Frames are sent from **source MAC → destination MAC** within the same LAN.  
3. Switches use **MAC tables** to forward frames to the correct port.  

💡 **Note:** MAC addresses are only used within the same local network; routers use **IP addresses** to communicate between networks.

---

## 🧠 Example: Ethernet Frame

| Field | Description |
|--------|--------------|
| **Destination MAC** | MAC of the receiving device |
| **Source MAC** | MAC of the sender |
| **Payload** | Actual data (like IP packet) |
| **FCS (Frame Check Sequence)** | Error checking |

---

## 🧬 Types of MAC Addresses

| Type | Description |
|------|--------------|
| **Unicast** | Sent to a single device |
| **Multicast** | Sent to multiple specific devices |
| **Broadcast** | Sent to **all devices** in the network (`FF:FF:FF:FF:FF:FF`) |

---

## ⚙️ MAC Address vs IP Address

| Feature | MAC Address | IP Address |
|----------|--------------|------------|
| **Layer** | Layer 2 (Data Link) | Layer 3 (Network) |
| **Purpose** | Identifies physical device | Identifies logical location |
| **Assigned By** | Manufacturer | Network admin or DHCP |
| **Changes?** | Permanent (can be spoofed) | Dynamic or static |
| **Format** | Hexadecimal (e.g., 00:1A:2B...) | Decimal (e.g., 192.168.1.10) |

---

## 🧯 Advantages & Importance

✅ **Uniqueness:** Ensures each device can be identified on a LAN  
✅ **Security:** Can be used in access control lists (MAC filtering)  
✅ **Troubleshooting:** Helps track devices or detect anomalies  
✅ **Networking:** Essential for Ethernet, Wi-Fi, and VLANs  

---

## ⚠️ MAC Spoofing

Attackers can **change (spoof)** their MAC address to:
- Bypass MAC filters or firewalls  
- Impersonate another device  
- Hide identity on a network  

💡 Network administrators can detect spoofing using **network monitoring tools** and **port security** features on switches.

---

## 🔒 In Cybersecurity

MAC addresses are crucial for:
- **Network access control** (NAC)  
- **Device fingerprinting**  
- **Intrusion detection systems (IDS)**  
- **Forensic analysis** of network activity  

---

> 💡 **Tip:** You can view your MAC address using:
> - **Windows:** `ipconfig /all`  
> - **Linux/macOS:** `ifconfig` or `ip link show`
