# **Routing Basics**

## **1. Introduction to Routing**

Routing is the process of moving packets from one network to another. When a device needs to send data to a destination outside its own network, a router determines the best path based on routing tables.

Routers operate at **Layer 3 (Network Layer)** of the OSI model and use **IP addresses** to forward traffic.

---

## **2. Key Routing Concepts**

### **a. Router Interfaces**

Routers have two main types of interfaces:

* **LAN interfaces**: Connect to internal networks.
* **WAN interfaces**: Connect routers together across different networks.

Each interface must have an IP address and subnet mask.

---

### **b. Routing Table**

A routing table contains:

* Destination networks
* Next-hop router or exit interface
* Route metrics (cost values)
* Route source (how the route was learned)

Routers check their routing table for the most specific match to forward packets.

---

## **3. Types of Routes**

### **a. Directly Connected Routes**

These routes are automatically added when a router interface is configured with an IP address and enabled.

### **b. Static Routes**

Manually configured by administrators.
Used when the network is small or the path is predictable.

Example:

```
ip route 192.168.20.0 255.255.255.0 192.168.10.1
```

### **c. Dynamic Routes**

Automatically learned using routing protocols.
Used in medium to large networks.

Common dynamic protocols:

* **RIP (Routing Information Protocol)**
* **OSPF (Open Shortest Path First)**
* **EIGRP (Enhanced Interior Gateway Routing Protocol)**

---

## **4. Static Routing Configuration Example**

Scenario:

* Router R1 network: 192.168.1.0/24
* Router R2 network: 192.168.2.0/24
* Link between routers: 10.0.0.0/30

### **On R1:**

```
interface g0/0
 ip address 192.168.1.1 255.255.255.0
 no shut

interface g0/1
 ip address 10.0.0.1 255.255.255.252
 no shut

ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

### **On R2:**

```
interface g0/0
 ip address 192.168.2.1 255.255.255.0
 no shut

interface g0/1
 ip address 10.0.0.2 255.255.255.252
 no shut

ip route 192.168.1.0 255.255.255.0 10.0.0.1
```

---

## **5. Dynamic Routing Basics**

Dynamic routing protocols exchange routing information between routers.

### **Key elements:**

* **Neighbor discovery**
* **Topology exchange**
* **Metric calculation**
* **Best-path selection**

---

## **6. OSPF Overview**

OSPF is a link-state routing protocol using **Dijkstra's algorithm**.

### Features:

* Fast convergence
* Hierarchical structure (areas)
* Metric: **Cost** based on bandwidth

### Basic OSPF configuration:

```
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
 network 10.0.0.0 0.0.0.3 area 0
```

---

## **7. RIP Overview**

RIP is a distance-vector routing protocol using **hop count** as its metric.

### Limitations:

* Maximum 15 hops
* Slow convergence

### Basic RIP configuration:

```
router rip
 version 2
 network 192.168.1.0
 network 10.0.0.0
```

---

## **8. Routing Verification Commands**

### **Check routing table:**

```
show ip route
```

### **Check interface status:**

```
show ip interface brief
```

### **Check OSPF neighbors:**

```
show ip ospf neighbor
```

### **Check RIP routes:**

```
show ip rip database
```

---

## **9. Conclusion**

Routing is the backbone of network communication. Understanding static and dynamic routing allows engineers to build scalable, efficient, and stable networks.


