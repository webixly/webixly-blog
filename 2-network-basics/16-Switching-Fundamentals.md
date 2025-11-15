# Switching Fundamentals

## 1. Introduction

Switching is the core of LAN communication. It enables devices to communicate efficiently within the same network by forwarding Ethernet frames based on MAC addresses.

This lesson explains how switches work, why they are essential, and the key concepts every networking student must master.

---

## 2. What is a Switch?

A switch is a network device that operates at **Layer 2 (Data Link Layer)** of the OSI model.
Its primary job is:

* Forward frames
* Learn MAC addresses
* Reduce collisions compared to hubs

---

## 3. How Switches Learn MAC Addresses

Switches maintain a **MAC Address Table**.
They build it dynamically by:

1. Reading the source MAC address of incoming frames
2. Mapping it to the port it came from
3. Storing the entry in the MAC table

When forwarding a frame, the switch:

* Checks the destination MAC
* If known → forwards out the specific port
* If unknown → floods out all ports except the source

---

## 4. Collision Domains vs Broadcast Domains

### Collision Domain

* Each switch port represents **one collision domain**
* This eliminates collisions that happen in hubs

### Broadcast Domain

* Switches forward broadcasts across all ports
* Broadcast domains are only broken by routers or VLANs

---

## 5. Switching Methods

Switches may use different techniques to forward frames:

### **1. Store-and-Forward**

* Receives the entire frame
* Checks for errors (CRC)
* Most accurate, recommended

### **2. Cut-Through**

* Starts forwarding as soon as destination MAC is read
* Faster but may forward corrupted frames

### **3. Fragment-Free**

* Reads first 64 bytes (where most errors occur)
* Compromise between accuracy and speed

---

## 6. Switching Table Aging

MAC address entries age out after a default time (usually 300 seconds).
If no frames are received from a MAC within that time, it is removed.
This prevents stale entries.

---

## 7. Duplex Modes

### **Half Duplex**

* One-way communication at a time
* Legacy and inefficient

### **Full Duplex**

* Send + receive simultaneously
* Requires a switch + NIC that supports it
* Standard in modern networks

---

## 8. Switch Port Speeds

Common speeds:

* 10 Mbps (Ethernet)
* 100 Mbps (Fast Ethernet)
* 1 Gbps (Gigabit Ethernet)
* 10 Gbps+ (modern enterprise speeds)

---

## 9. MAC Filtering & Port Security (Preview)

Switches can secure ports by:

* Limiting allowed MAC addresses
* Blocking unknown devices
* Preventing MAC flooding attacks

(This topic will be covered in a later lesson.)

---

## 10. Summary

Switches:

* Forward frames using MAC addresses
* Reduce collision domains
* Maintain MAC address tables
* Support different forwarding methods
* Enable efficient LAN communication

Mastering switching fundamentals is essential before moving on to VLANs, STP, trunking, and enterprise network design.

---
