# 🧩 Subnet Mask — Understanding Network Division  

## 🧠 Overview  
The **Subnet Mask** is a 32-bit number used to divide an IP address into **network** and **host** portions.  
It tells routers and devices which part of the address identifies the **network**, and which part identifies the **specific device** (host) inside that network.

Every device in a network uses a subnet mask to know **whether another IP address belongs to the same network or not**.

---

## 📘 Example  

| IP Address | Subnet Mask | Network Portion | Host Portion |
|-------------|--------------|------------------|----------------|
| `192.168.1.10` | `255.255.255.0` | `192.168.1` | `.10` |

➡️ The mask `255.255.255.0` means the **first 24 bits** (3 octets) represent the **network**, and the **last 8 bits** represent the **host**.

---

## 🧮 Binary Representation  

| Decimal | Binary Representation |
|----------|------------------------|
| 255 | 11111111 |
| 0 | 00000000 |

So,  
`255.255.255.0` → `11111111.11111111.11111111.00000000`  

Bits set to **1** = **network**  
Bits set to **0** = **host**

---

## 🧰 CIDR Notation  
CIDR (Classless Inter-Domain Routing) is a simplified way to represent subnet masks.

| Subnet Mask | CIDR | Hosts per Network |
|--------------|------|-------------------|
| 255.0.0.0 | /8 | 16,777,214 |
| 255.255.0.0 | /16 | 65,534 |
| 255.255.255.0 | /24 | 254 |
| 255.255.255.128 | /25 | 126 |

> Example:  
> `192.168.1.0/24` = Network with 256 addresses (254 usable for hosts)

---

## ⚙️ Formula for Hosts  

**Number of Hosts = 2^(32 − CIDR) − 2**


- Subtract **2** because one address is for **network ID**, and one for **broadcast**.

> Example:  
> `/24 → 2^{(32-24)} - 2 = 254 usable hosts`

---

## 🔍 Why Subnetting Matters  
Subnetting allows you to:  
- Reduce network congestion by dividing large networks into smaller ones.  
- Improve **security** and **performance**.  
- Organize devices logically by department, location, or function.  

---

## 🧱 Common Subnet Masks  

| CIDR | Subnet Mask | # of Hosts | Network Bits | Host Bits |
|------|--------------|-------------|---------------|-------------|
| /8 | 255.0.0.0 | 16,777,214 | 8 | 24 |
| /16 | 255.255.0.0 | 65,534 | 16 | 16 |
| /24 | 255.255.255.0 | 254 | 24 | 8 |
| /30 | 255.255.255.252 | 2 | 30 | 2 |

---

## 🧠 Quick Tip  
If two devices have **the same network portion** (as defined by their subnet mask),  
they can **communicate directly** without going through a router.  
Otherwise, their traffic must pass through one.

---

## 🧩 Example Test  

| Device | IP | Subnet Mask |
|---------|----|--------------|
| PC1 | 192.168.1.10 | 255.255.255.0 |
| PC2 | 192.168.1.200 | 255.255.255.0 |
| PC3 | 192.168.2.5 | 255.255.255.0 |

✅ PC1 ↔ PC2 → Same network  
❌ PC1 ↔ PC3 → Different network (router needed)

---

## 🧭 Summary  
- Subnet masks define which part of an IP identifies the **network** and which part identifies the **host**.  
- CIDR notation simplifies representation (e.g., `/24` = `255.255.255.0`).  
- Subnetting improves network organization, security, and efficiency.
