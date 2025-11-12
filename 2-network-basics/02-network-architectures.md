# 🌐 Network Architectures & Models

Understanding **network architectures and models** is essential for anyone who wants to master networking and cybersecurity.  
They describe **how devices communicate**, **how data flows**, and **how networks are structured** — from small home setups to the vast internet.

---

## 🧱 1. What is a Network Architecture?

A **network architecture** defines the **structure**, **design**, and **communication principles** of a network.  
It explains how devices, protocols, and services work together to ensure reliable data exchange.

There are two main types of network architectures:

---

### 🖥️ a) Client–Server Architecture

This is the most common network design used today.

**How it works:**
- A **server** provides services or resources (like files, websites, or emails).  
- **Clients** (computers or devices) request these services from the server.

**Example:**  
When you visit a website — your browser (client) requests the page from a web server.

**Advantages:**
- Centralized control  
- Easier to manage and secure  
- Scalable for large organizations  

**Disadvantages:**
- If the server fails, all clients are affected  
- Requires more powerful hardware for the server  

---

### 🧑‍🤝‍🧑 b) Peer-to-Peer (P2P) Architecture

In a **P2P network**, every device acts as both a **client and a server**.  
Devices can share files, printers, or other resources **without a central server**.

**Example:**  
File-sharing systems like BitTorrent.

**Advantages:**
- Easy to set up  
- No need for a central server  
- Great for small networks  

**Disadvantages:**
- Less secure and harder to manage  
- Limited scalability  

---

## 🧩 2. Network Models Overview

Network **models** describe how data travels between devices in a structured way.  
The two most important models are **OSI** and **TCP/IP**.

---

### ⚙️ a) OSI Model (Open Systems Interconnection)

The **OSI model** divides network communication into **seven layers** — each responsible for a specific function.

| Layer | Name | Description |
|-------|------|-------------|
| 7 | Application | Interface for users and software (HTTP, DNS) |
| 6 | Presentation | Data formatting, encryption, compression |
| 5 | Session | Establishes, manages, and terminates connections |
| 4 | Transport | Ensures reliable delivery (TCP, UDP) |
| 3 | Network | Handles routing and IP addressing |
| 2 | Data Link | Manages MAC addresses and switches |
| 1 | Physical | Transmission of raw bits (cables, signals) |

🧠 **Tip:** Each layer communicates only with the layer directly above or below it — creating a modular and organized design.

---

### 🌍 b) TCP/IP Model

The **TCP/IP model** is the practical framework used on the internet today.  
It is simpler — made up of **four layers** that correspond to the OSI model.

| TCP/IP Layer | Equivalent OSI Layers | Example Protocols |
|---------------|------------------------|--------------------|
| Application | 5–7 | HTTP, HTTPS, DNS, FTP |
| Transport | 4 | TCP, UDP |
| Internet | 3 | IP, ICMP, ARP |
| Network Access | 1–2 | Ethernet, Wi-Fi |

📡 The TCP/IP model is the foundation of **modern networking**, especially for internet communication.

---

## 🧠 3. Key Differences Between OSI and TCP/IP

| Feature | OSI Model | TCP/IP Model |
|----------|------------|--------------|
| Layers | 7 | 4 |
| Developed By | ISO | DoD (Department of Defense) |
| Usage | Theoretical, educational | Practical, real-world |
| Protocol Dependence | Protocol-independent | Built around TCP/IP stack |

---

## 🚀 Summary

- **Architectures** define *how* devices connect and share resources.  
- **Models** define *how* data moves* between those devices.  
- Together, they provide the **blueprint** for reliable, secure communication.

---

## 🔗 Next Lesson  
👉 [Copper Cables (Ethernet)](3-copper-cables.md)
