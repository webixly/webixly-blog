# 🌐 Types of IP Addresses and IPv6 Introduction

## 🧩 Introduction

IP addresses are unique identifiers assigned to devices on a network. They allow devices to communicate over the Internet or local networks. IP addresses can be classified into different **types** based on their purpose, scope, and visibility.

With the growth of the Internet, **IPv6** was introduced to overcome the limitations of IPv4, providing a vastly larger address space and new features for modern networks.

Understanding the types of IP addresses and IPv6 is essential for **network configuration, cybersecurity, and troubleshooting**.

---

## 📘 Public vs Private IP Addresses

IP addresses are divided into **public** and **private** ranges:

* **Public IP Address**

  * Assigned by **Internet Service Providers (ISPs)**.
  * Globally unique; used to identify devices on the Internet.
  * Example: `203.0.113.25`

* **Private IP Address**

  * Used within local networks (LAN).
  * Not routable on the Internet.
  * Common ranges (IPv4):

    * `10.0.0.0 – 10.255.255.255`
    * `172.16.0.0 – 172.31.255.255`
    * `192.168.0.0 – 192.168.255.255`
  * Example: `192.168.1.10`

---

## 🧮 Static vs Dynamic IP Addresses

* **Static IP Address**

  * Manually assigned to a device.
  * Does not change over time.
  * Useful for **servers, routers, and network devices**.
  * Example: `192.168.1.100`

* **Dynamic IP Address**

  * Assigned automatically by a **DHCP server**.
  * Can change over time.
  * Common for **home users and mobile devices**.
  * Example: `192.168.1.101`

---

## 🌐 Unicast, Broadcast, and Multicast

* **Unicast**

  * One-to-one communication.
  * Example: sending data from your computer to a server.

* **Broadcast**

  * One-to-all communication within a subnet.
  * Example: `192.168.1.255` (broadcast address for `/24` subnet).

* **Multicast**

  * One-to-many communication.
  * Used for streaming, video conferencing, etc.
  * Example range: `224.0.0.0 – 239.255.255.255`

---

## 🔒 Special IP Addresses

| Type           | Purpose                                         | Example       |
| -------------- | ----------------------------------------------- | ------------- |
| **Loopback**   | Test network interface on the same device       | `127.0.0.1`   |
| **Link-local** | Auto-configured for local network communication | `169.254.x.x` |
| **APIPA**      | Automatic Private IP Addressing when DHCP fails | `169.254.x.x` |
| **Reserved**   | Reserved for future use or special protocols    | `0.0.0.0`     |

---

## 🧠 IPv4 vs IPv6

* **IPv4**

  * 32-bit addresses (`192.168.1.1`).
  * Limited address space (~4.3 billion addresses).

* **IPv6**

  * 128-bit addresses (`2001:0db8:85a3::8a2e:0370:7334`).
  * Vastly larger address space for global scalability.
  * Eliminates the need for NAT in most cases.
  * Includes built-in features for security (IPSec), auto-configuration, and simplified routing.
  * Example IPv6 ranges:

    * **Global Unicast**: `2000::/3` (routable on the Internet)
    * **Link-local**: `FE80::/10` (local network only)
    * **Multicast**: `FF00::/8`

IPv6 adoption is essential as IPv4 addresses become exhausted, enabling future-proof networking and seamless device connectivity.

---

## 💡 Tip

Knowing IP address types and IPv6 is critical for:

* **Configuring networks and firewalls**
* **Segmentation and routing**
* **Ethical hacking and penetration testing**

Example (Nmap scan using IPv6 range):

```
nmap -6 -sP 2001:db8::/64
```

This scans all devices within the specified IPv6 subnet.

---

## 🧭 Summary

| Concept                         | Description                                                        |
| ------------------------------- | ------------------------------------------------------------------ |
| **Public IP**                   | Globally unique; accessible on the Internet                        |
| **Private IP**                  | Local network only; not routable on the Internet                   |
| **Static IP**                   | Permanent assignment for servers/devices                           |
| **Dynamic IP**                  | Assigned by DHCP; can change                                       |
| **IPv6**                        | 128-bit addressing system; large address space and modern features |
| **Unicast/Broadcast/Multicast** | Defines communication type within network                          |

---

### 🧑‍💻 Author

**Pablo (Webixly)**
Cybersecurity & Networking Enthusiast
[GitHub Profile](https://github.com/webixly)

---

⭐ *Prepared as a professional educational resource for university presentation.*
