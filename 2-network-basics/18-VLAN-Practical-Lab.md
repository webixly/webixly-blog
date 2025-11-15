# VLAN Practical Lab

## 1. Introduction

This lab demonstrates how to create, assign, and verify VLANs on Cisco switches. It reinforces theoretical VLAN concepts with a real, hands‑on configuration workflow suitable for academic presentation.

---

## 2. Lab Objectives

By the end of this lab, you will be able to:

* Create VLANs on a Cisco switch
* Assign switch ports to VLANs
* Configure trunk links between switches
* Verify VLAN membership and connectivity
* Understand how VLANs segment broadcast domains

---

## 3. Topology Overview

A simple two‑switch lab:

```
PC1 ----- SW1 ----- SW2 ----- PC2
```

**VLAN Assignments:**

* VLAN 10 → PC1
* VLAN 20 → PC2

**Goal:** Devices in the same VLAN communicate; different VLANs remain isolated.

---

## 4. Step 1 — Creating VLANs

### On SW1 and SW2:

```
enable
configure terminal
vlan 10
 name HR
vlan 20
 name IT
exit
```

This creates two VLANs and labels them for clarity.

---

## 5. Step 2 — Assigning Access Ports

### On SW1:

Assign PC1 to VLAN 10:

```
interface fastEthernet0/1
 switchport mode access
 switchport access vlan 10
exit
```

### On SW2:

Assign PC2 to VLAN 20:

```
interface fastEthernet0/1
 switchport mode access
 switchport access vlan 20
exit
```

Access mode ensures each port belongs to exactly one VLAN.

---

## 6. Step 3 — Configuring Trunk Ports

To allow VLANs to pass between switches:

### On SW1:

```
interface fastEthernet0/24
 switchport mode trunk
 switchport trunk allowed vlan 10,20
exit
```

### On SW2:

```
interface fastEthernet0/24
 switchport mode trunk
 switchport trunk allowed vlan 10,20
exit
```

Trunks carry multiple VLANs and are essential when networks span multiple switches.

---

## 7. Step 4 — Verification Commands

### Check VLANs:

```
show vlan brief
```

### Check trunk links:

```
show interfaces trunk
```

### Check MAC address learning:

```
show mac address-table
```

### Ping tests:

* PC1 ↔ PC1 VLAN peers → **should work**
* PC1 ↔ PC2 → **should fail** (different VLANs)

---

## 8. Expected Results

* Devices in the same VLAN communicate normally.
* Devices in different VLANs remain isolated.
* Switches correctly forward frames using trunk links.

This demonstrates that VLANs create separate broadcast domains and improve network segmentation, security, and efficiency.

---

## 9. Conclusion

This lab validates core VLAN concepts with real configurations. Mastering VLAN creation, access ports, and trunking is essential before advancing to:

* Inter-VLAN routing
* Routed access designs
* Dynamic Trunking Protocol (DTP)
* VLAN security hardening
