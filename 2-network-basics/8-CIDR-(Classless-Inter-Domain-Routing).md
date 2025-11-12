# 🌐 CIDR (Classless Inter-Domain Routing)

## 🧩 Introduction

CIDR, short for **Classless Inter-Domain Routing**, is a modern method used to allocate IP addresses and route packets efficiently. It was introduced in 1993 to replace the old class-based addressing system (Class A, B, C), which caused massive waste of IP addresses.

CIDR simplifies how we represent networks and improves the scalability of the Internet. Instead of relying on fixed classes, CIDR allows flexible network sizes based on actual needs.

---

## 📘 CIDR Notation

CIDR uses a simple format:

```
IP Address / Prefix Length
```

For example:

```
192.168.10.0/24
```

This means that the **first 24 bits** represent the **network part**, and the remaining bits (32 − 24 = 8) represent the **host part**.

Each prefix length determines how many IP addresses belong to that network.

| CIDR Notation | Subnet Mask     | # of Hosts |
| ------------- | --------------- | ---------- |
| /8            | 255.0.0.0       | 16,777,214 |
| /16           | 255.255.0.0     | 65,534     |
| /24           | 255.255.255.0   | 254        |
| /30           | 255.255.255.252 | 2          |

---

## 🧮 Calculating the Number of Hosts

The number of usable hosts per subnet is determined by:

[ \text{Number of Hosts} = 2^{(32 - \text{CIDR})} - 2 ]

For example:

* `/24` → 2^(32 - 24) - 2 = 254 hosts
* `/30` → 2^(32 - 30) - 2 = 2 hosts

The subtraction by 2 accounts for the **network address** and the **broadcast address**.

---

## 🧠 Why CIDR Replaced Classful Addressing

Before CIDR, IP addresses were divided into rigid classes:

* **Class A**: /8 → 16 million hosts (too large for most networks)
* **Class B**: /16 → 65,000 hosts
* **Class C**: /24 → 254 hosts

This led to huge inefficiency — many organizations received more addresses than needed. CIDR introduced **variable-length subnet masking (VLSM)**, allowing custom subnet sizes.

---

## ⚙️ CIDR and Routing

CIDR plays a vital role in Internet routing by allowing **route aggregation**, also known as **supernetting**. This reduces the size of global routing tables, improving the speed and efficiency of routers.

Example:
Instead of listing:

```
192.168.0.0/24
192.168.1.0/24
192.168.2.0/24
192.168.3.0/24
```

We can aggregate them as:

```
192.168.0.0/22
```

This single route covers all four subnets, reducing the routing table entries.

---

## 🔒 CIDR in Cybersecurity

CIDR notation is widely used in **firewalls**, **access control lists (ACLs)**, and **intrusion detection systems (IDS)** to define IP ranges.

Example (Firewall Rule):

```
Allow: 192.168.10.0/24
Deny: 203.0.113.0/25
```

This ensures that access rules apply to entire networks instead of individual IPs — essential for scalability and network segmentation.

In **ethical hacking and penetration testing**, CIDR is also used for **network scanning** (e.g., using Nmap):

```
nmap -sP 192.168.1.0/24
```

This scans all devices within that subnet.

---

## 💡 Tip

CIDR mastery is fundamental in understanding how **networks are structured, secured, and exploited**. Whether configuring routers, building firewalls, or scanning networks, CIDR is at the core of modern network management.

---

## 🧭 Summary

| Concept          | Description                                         |
| ---------------- | --------------------------------------------------- |
| **CIDR**         | Flexible IP addressing system replacing old classes |
| **Purpose**      | Efficient allocation and routing of IP addresses    |
| **Key Feature**  | Uses prefix length to define subnet size            |
| **Main Benefit** | Reduces routing table size and address waste        |

---

### 🧑‍💻 Author

**Pablo (Webixly)**
Cybersecurity & Networking Enthusiast
[GitHub Profile](https://github.com/webixly)

---

⭐ *If you found this helpful, consider starring the repository — it helps support the cybersecurity learning journey!*
