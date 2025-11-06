# 🧩 Network Devices — The Building Blocks of Communication

Networking devices are the **core components** that allow computers and systems to connect, communicate, and share resources.  
They manage data flow, control traffic, and ensure that information reaches the right destination efficiently and securely.

---

## 🔌 1. Hub
A **Hub** is a simple device that connects multiple computers in a network.  
It broadcasts every packet it receives to **all connected devices**, which can cause unnecessary traffic.

**Key points:**
- Operates at **Layer 1 (Physical Layer)** of the OSI model.  
- No filtering or data inspection.  
- Rarely used today because it is inefficient.

---

## 🌐 2. Switch
A **Switch** is a smarter version of a hub.  
It uses **MAC addresses** to send data only to the intended recipient.

**Key points:**
- Operates at **Layer 2 (Data Link Layer)**.  
- Reduces network collisions.  
- Increases performance and security.

---

## 🚦 3. Router
A **Router** connects **different networks** together — for example, your local network to the internet.  
It determines the **best path** for data to travel.

**Key points:**
- Operates at **Layer 3 (Network Layer)**.  
- Uses **IP addresses** for routing.  
- Can apply **NAT (Network Address Translation)** and **firewall rules**.

---

## 📡 4. Access Point (AP)
An **Access Point** provides **wireless connectivity** for devices to join a network.  
It connects to a wired switch or router and broadcasts a **Wi-Fi signal**.

**Key points:**
- Works at **Layer 2 (Data Link)**.  
- Supports Wi-Fi standards like 802.11a/b/g/n/ac.  
- Allows mobility within the network.

---

## 🧱 5. Firewall
A **Firewall** acts as a **security barrier** that filters network traffic based on defined rules.  
It can be **hardware**, **software**, or both.

**Key points:**
- Operates across multiple layers (mainly **Layer 3 & 4**).  
- Protects against unauthorized access.  
- Monitors and logs suspicious activity.

---

## 🔁 6. Modem
A **Modem** (Modulator–Demodulator) converts **digital signals** from a computer into **analog signals** for transmission over telephone or cable lines — and vice versa.

**Key points:**
- Connects a local network to the **ISP (Internet Service Provider)**.  
- Often integrated into routers today.

---

## 🛰️ 7. Repeater
A **Repeater** strengthens or “regenerates” a weak signal to extend the distance a network can cover.

**Key points:**
- Operates at **Layer 1 (Physical)**.  
- Used in both wired and wireless networks.

---

## 🧠 Summary

| Device | OSI Layer | Function |
|--------|------------|-----------|
| Hub | Layer 1 | Broadcasts data to all devices |
| Switch | Layer 2 | Forwards data using MAC addresses |
| Router | Layer 3 | Routes data between networks |
| Access Point | Layer 2 | Provides wireless access |
| Firewall | Layer 3–4 | Secures and filters traffic |
| Modem | Layer 1 | Converts analog/digital signals |
| Repeater | Layer 1 | Boosts signal strength |

---

## 🧩 In Short

Each device plays a **unique role** in building stable, fast, and secure networks.  
Understanding them is the **first step toward mastering networking and cybersecurity**.

---

**Next Lesson →** [Network Architectures & Models](2-network-architectures.md)
