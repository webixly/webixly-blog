# CIDR (Classless Inter-Domain Routing)

## 📘 Overview

CIDR — short for **Classless Inter-Domain Routing** — is a modern method used to allocate IP addresses and route traffic efficiently.
Before CIDR, IP networks were divided into fixed classes (A, B, C), which caused massive waste of IP addresses and inefficient routing. CIDR fixed this by introducing **variable-length subnet masking (VLSM)**.

---

## 🧩 The Problem with Classful Addressing

Previously, IP addresses were grouped into classes:

* **Class A**: ~16 million hosts
* **Class B**: ~65,000 hosts
* **Class C**: 254 hosts

This rigid division wasted many IPs since organizations often received more addresses than they needed.

---

## ⚙️ How CIDR Works

CIDR replaces the old "class" system with **prefix notation**.
An IP address looks like this:

```
192.168.1.0/24
```

Here:

* `192.168.1.0` → Network address
* `/24` → Number of bits used for the network portion

So 24 bits identify the network, and 8 bits remain for hosts.

---

## 🧮 Calculating the Number of Hosts

$$
\text{Number of Hosts} = 2^{(32 - \text{CIDR})} - 2
$$

**Example:**
For a `/24` network:

$$
2^{(32 - 24)} - 2 = 254
$$

So, you have **254 usable hosts**.

---

## 🔍 CIDR to Subnet Mask Conversion

| CIDR | Subnet Mask     | Usable Hosts |
| ---- | --------------- | ------------ |
| /24  | 255.255.255.0   | 254          |
| /25  | 255.255.255.128 | 126          |
| /26  | 255.255.255.192 | 62           |
| /27  | 255.255.255.224 | 30           |
| /28  | 255.255.255.240 | 14           |
| /29  | 255.255.255.248 | 6            |

---

## 💡 Tip

CIDR notation is used for both **IPv4** and **IPv6** networks.
In IPv6, the same prefix principle applies, but the address length is **128 bits** instead of 32.
