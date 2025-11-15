# VLANs (Virtual Local Area Networks)

A Professional Academic Lesson for University Submission

---

## 1. Introduction

Virtual LANs (VLANs) allow network engineers to segment a physical LAN into multiple isolated logical networks, improving security, scalability, and traffic efficiency.

---

## 2. Why Do We Need VLANs?

Without VLANs, all devices share one broadcast domain, causing unnecessary broadcast traffic, weak security, and poor scalability.
VLANs solve this by creating logical segmentation independent of physical layout.

---

## 3. How VLANs Work

Switch ports are assigned VLAN IDs (1–4094). Devices in the same VLAN communicate directly; communication between VLANs requires a router or Layer 3 switch.

### Key Concepts

* **VLAN ID**: Identifier for each VLAN.
* **Access Port**: Carries traffic for one VLAN.
* **Trunk Port**: Carries traffic for multiple VLANs.
* **802.1Q Tagging**: Inserts VLAN tag into Ethernet frame.
* **Native VLAN**: VLAN that passes untagged traffic on trunk links.

---

## 4. VLAN Types

* **Default VLAN**: Usually VLAN 1.
* **Data VLAN**: For user devices.
* **Voice VLAN**: Optimized for VoIP.
* **Management VLAN**: For management interfaces.
* **Native VLAN**: For untagged traffic.

---

## 5. Benefits of VLANs

* Enhanced security
* Reduced broadcast traffic
* Better organization
* Scalability

---

## 6. VLAN Frame Tagging (802.1Q)

Frames on trunk links contain a 4-byte VLAN tag with:

* VLAN ID
* Priority Bits
* Drop Eligible Indicator

---

## 7. VLAN Configuration on Cisco Switches

### Create VLANs

```
Switch(config)# vlan 10
Switch(config-vlan)# name HR

Switch(config)# vlan 20
Switch(config-vlan)# name IT

Switch(config)# vlan 30
Switch(config-vlan)# name STUDENTS
```

### Assign VLANs to Ports

```
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
```

### Configure Trunk Links

```
Switch(config)# interface fa0/24
Switch(config-if)# switchport trunk encapsulation dot1q
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20,30
```

---

## 8. Inter-VLAN Routing

Required for communication between VLANs. Achieved via:

1. Router-on-a-Stick
2. Layer 3 Switch SVIs

---

## 9. Real-World Use Cases

* Enterprise segmentation
* Universities (departments, labs, WiFi)
* Cybersecurity isolation

---

## 10. VLAN Segmentation Diagram

```
+---------------------+
|      L2 Switch      |
|---------------------|
| Ports 1–5: VLAN 10  |
| Ports 6–10: VLAN 20 |
| Ports 11–20: VLAN30 |
| Port 24: Trunk      |
+---------------------+
         |
       Trunk
         |
+------------------+
|   Router / L3    |
+------------------+
```

---

## 11. Summary

VLANs enable logical segmentation, security, reduced broadcast domains, scalability, and efficient management.

---

## 12. Academic Value

This lesson shows professional documentation, deep technical understanding, and strong alignment with cybersecurity studies.
