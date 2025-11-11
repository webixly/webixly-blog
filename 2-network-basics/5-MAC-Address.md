# Subnet Mask

## Introduction

A **Subnet Mask** is a fundamental concept in networking.
It determines which part of an IP address identifies the **network** and which part identifies the **host** within that network.
Understanding subnet masks is essential for efficient IP management and proper network segmentation.

---

## 1. Concept Explanation

Every IP address consists of two logical parts:

* **Network Portion** — identifies the specific network.
* **Host Portion** — identifies an individual device (host) within that network.

For example:

```
IP Address:    192.168.1.10  
Subnet Mask:   255.255.255.0
```

This means:

* `192.168.1` → Network portion
* `.10` → Host portion

In this configuration, all devices with addresses between `192.168.1.1` and `192.168.1.254` belong to the same network.

---

## 2. Binary Representation

A subnet mask is written in binary format to define how many bits are used for the network part and how many for the host part.

```
IP:        192.168.1.10   → 11000000.10101000.00000001.00001010  
Subnet:    255.255.255.0  → 11111111.11111111.11111111.00000000
```

Here:

* The first **24 bits** (ones) define the **network**.
* The remaining **8 bits** (zeros) define the **hosts**.
  This is represented in CIDR notation as **/24**.

---

## 3. Calculating Number of Hosts

Each subnet provides a certain number of usable host addresses depending on the number of bits allocated for the host part.

**Formula:**

```
Number of Hosts = 2^(32 − CIDR) − 2
```

The subtraction of 2 accounts for:

* The **Network Address** (all host bits = 0)
* The **Broadcast Address** (all host bits = 1)

### Example:

| CIDR | Subnet Mask     | Usable Hosts | Network Bits | Host Bits |
| ---- | --------------- | ------------ | ------------ | --------- |
| /24  | 255.255.255.0   | 254          | 24           | 8         |
| /25  | 255.255.255.128 | 126          | 25           | 7         |
| /26  | 255.255.255.192 | 62           | 26           | 6         |
| /27  | 255.255.255.224 | 30           | 27           | 5         |

---

## 4. Network Design Considerations

When designing or segmenting a network, subnet masks help to:

* **Control broadcast domains** and reduce congestion.
* **Enhance security** by isolating groups of hosts.
* **Improve scalability** and manage IP addresses efficiently.

**Tip:**
Always allocate slightly more host addresses than initially required.
This ensures future scalability without redesigning the network.

---

## 5. Summary

* A subnet mask separates the **network** from the **host** portion of an IP address.
* CIDR notation simplifies mask representation.
* The number of host bits directly determines subnet size.
* Proper subnetting leads to efficient, secure, and scalable networks.

---

**Author:** Pablo (Webixly)
**Focus Area:** Networking & Cybersecurity Fundamentals
