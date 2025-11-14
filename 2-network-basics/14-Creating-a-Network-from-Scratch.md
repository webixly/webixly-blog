# Creating a Network from Scratch

**Laboratory Exercise – Networking Fundamentals**

This lesson provides a structured, academic approach to building a network from the ground up. The goal is to understand how hosts, switches, routers, and IP addressing work together in a functional LAN environment.

---

## 1. Objective

By the end of this lab, you will be able to:

* Design a simple network topology.
* Configure IP addressing manually.
* Connect end devices through switches and routers.
* Verify connectivity using essential network tools.

---

## 2. Required Tools

To perform this lab, you need one of the following:

* **Cisco Packet Tracer** (recommended)
* GNS3
* EVE-NG

For academic demonstrations, Packet Tracer is the standard due to simplicity and clarity.

---

## 3. Network Topology Overview

You will create a small network consisting of:

* **Two PCs**
* **One Switch**
* **One Router**

This basic structure models a typical small-office network.

```
PC1 ----\
          Switch ---- Router ---- (Optional) Internet
PC2 ----/
```

---

## 4. Step-by-Step Procedure

### **4.1 Step 1: Add Devices to the Workspace**

1. Open Packet Tracer.
2. From the device list:

   * Add **2 PCs**
   * Add **1 Switch (e.g., 2960)**
   * Add **1 Router (e.g., 1941)**
3. Arrange them logically.

---

### **4.2 Step 2: Connect Devices**

Use **Copper Straight-Through** cables:

* PC1 → Switch (FastEthernet0)
* PC2 → Switch
* Switch → Router (GigabitEthernet0/0)

Ensure all device interfaces turn green (link is up).

---

### **4.3 Step 3: Assign IP Addresses to PCs**

#### **PC1 Configuration**

1. Select **PC1**
2. Go to **Desktop → IP Configuration**
3. Set:

   * IP Address: `192.168.10.10`
   * Subnet Mask: `255.255.255.0`
   * Default Gateway: `192.168.10.1`

#### **PC2 Configuration**

* IP Address: `192.168.10.11`
* Subnet Mask: `255.255.255.0`
* Default Gateway: `192.168.10.1`

---

### **4.4 Step 4: Configure Router Interface**

1. Click the router → **CLI**
2. Enter:

```
enable
configure terminal
interface gigabitEthernet 0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
write memory
```

This sets the router as the gateway for the network.

---

### **4.5 Step 5: Verify Connectivity**

#### Test 1 — PC-to-PC:

* On PC1 → Desktop → Command Prompt:

```
ping 192.168.10.11
```

Both PCs must reach each other.

#### Test 2 — PC-to-Router:

```
ping 192.168.10.1
```

If all replies are successful → the LAN is fully operational.

---

## 5. Troubleshooting Checklist

If connectivity fails, verify:

* Are the cables the correct type?
* Do the interface lights turn green?
* Are IP addresses in the same network?
* Is the router interface enabled (`no shutdown`)?
* Are default gateways set correctly?

---

## 6. Summary

In this lab, you learned:

* How to build a functional LAN from scratch.
* How to assign IP addresses and configure a gateway.
* How switches and routers interact to move data across the network.
* How to validate connectivity using `ping`.

This forms the foundation of all networking labs and prepares you for more advanced topics such as VLANs, Routing Protocols, and ACLs.

---
