# Switching Fundamentals

## 1. Introduction

Switching is the foundation of modern LAN communication. It allows devices to communicate efficiently by forwarding Ethernet frames based on MAC addresses. Mastering switching concepts is essential before learning VLANs, STP, and advanced routing.

---

## 2. What Is a Switch?

A switch is a device that operates at **Layer 2 (Data Link Layer)** of the OSI model. Its role includes:

* Forwarding Ethernet frames
* Learning and storing MAC addresses
* Reducing collisions compared to hubs

Switches make networks faster, more reliable, and more scalable.

---

## 3. How Switches Learn MAC Addresses

Every switch contains a **MAC Address Table** (CAM Table).

Switches learn MACs by:

1. Reading the **source MAC address** of incoming frames.
2. Associating that MAC with the port it came from.
3. Storing the entry temporarily in the MAC table.

When forwarding frames:

* If **destination MAC is known** → forward to that port only.
* If **unknown** → flood to all ports except the source.

---

## 4. Collision Domains vs Broadcast Domains

### Collision Domain

* Each switch port = 1 collision domain.
* Eliminates collisions that were common in hubs.

### Broadcast Domain

* Switches forward broadcasts out all ports.
* Broadcast domains are only segmented by **routers** or **VLANs**.

---

## 5. Switching Forwarding Methods

### 1. Store-and-Forward

* Receives the entire frame.
* Performs error checking (CRC).
* Most reliable.

### 2. Cut-Through

* Forwards as soon as the destination MAC is read.
* Faster but less accurate.

### 3. Fragment-Free

* Reads the first 64 bytes (where errors usually appear).
* Hybrid of speed + accuracy.

---

## 6. MAC Table Aging

MAC entries expire after a default timer (often 300 seconds). If a device stops sending traffic, its MAC is removed to free memory and prevent stale mappings.

---

## 7. DuplexModes

### Half Duplex

* Communication one direction at a time.
* Old and inefficient.

### Full Duplex

* Sends and receives simultaneously.
* Requires compatible switch + NIC.
* Standard in modern networks.

---

## 8. Switch Port Speeds

Typical speeds:

* 10 Mbps — Ethernet
* 100 Mbps — Fast Ethernet
* 1 Gbps — Gigabit Ethernet
* 10+ Gbps — Enterprise and datacenter links

---

## 9. Basic Switch Security Concepts (Preview)

Switches can enhance security through:

* Port security (limiting MACs)
* MAC filtering
* Protection against MAC flooding attacks

These topics will be covered in advanced lessons.

---

## 10. Summary

Switching provides the backbone of internal network communication by:

* Learning MAC addresses
* Reducing collision domains
* Forwarding frames efficiently
* Supporting high-speed full-duplex communication

Understanding these fundamentals prepares you for VLANs, trunking, STP, and enterprise-level network design.

---
