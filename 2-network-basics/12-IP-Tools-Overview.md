# 🌐 IP Tools Overview

## 🧩 Introduction

IP tools are essential utilities used for **network diagnostics, monitoring, configuration, and cybersecurity analysis**. They help network administrators, cybersecurity professionals, and developers to troubleshoot connectivity issues, analyze traffic, and manage networks efficiently.

This guide provides an overview of common IP tools and their applications.

---

## 📘 Common IP Tools

### 1. **Ping**

* Tests connectivity between devices on a network.
* Measures **round-trip time** and packet loss.
* Example:

```
ping 8.8.8.8
```

### 2. **Traceroute / Tracert**

* Displays the path packets take from source to destination.
* Helps identify **network bottlenecks or failures**.
* Example:

```
traceroute example.com   # Linux/Mac
tracert example.com      # Windows
```

### 3. **Nslookup / Dig**

* Queries DNS servers to obtain domain name or IP address mappings.
* Example:

```
nslookup example.com
```

```
dig example.com
```

### 4. **IP Config / Ifconfig / Ip**

* Displays IP configuration details of network interfaces.
* `ipconfig` for Windows, `ifconfig`/`ip addr` for Linux.
* Example:

```
ipconfig /all         # Windows
ifconfig -a           # Linux
ip addr show          # Linux
```

### 5. **Netstat**

* Shows active network connections, routing tables, and interface statistics.
* Useful for monitoring open ports and network activity.
* Example:

```
netstat -an
```

### 6. **ARP**

* Displays the ARP table that maps IP addresses to MAC addresses.
* Useful for detecting **ARP spoofing attacks**.
* Example:

```
arp -a
```

### 7. **Nmap**

* Advanced network scanning tool.
* Detects live hosts, open ports, services, and OS versions.
* Example:

```
nmap -sS 192.168.1.0/24  # TCP SYN scan
nmap -sU 192.168.1.0/24  # UDP scan
```

### 8. **Wireshark / Tcpdump**

* Packet sniffing and traffic analysis tools.
* Captures and inspects packets for troubleshooting or security analysis.
* Example:

```
tcpdump -i eth0
wireshark &  # GUI application
```

### 9. **IPerf / Speedtest**

* Measures network bandwidth and performance.
* Example:

```
iperf3 -c server_ip
speedtest-cli
```

### 10. **Whois**

* Provides ownership and registration information about IP addresses or domains.
* Example:

```
whois 8.8.8.8
```

---

## ⚙️ Practical Tips

1. **Use Ping and Traceroute first** to identify basic connectivity issues.
2. **Use Nslookup/Dig** for DNS-related problems.
3. **Monitor active connections with Netstat** to detect unauthorized access.
4. **Use Nmap for security auditing** and discovering open ports.
5. **Capture packets with Wireshark** for in-depth traffic analysis.

---

### 🧑‍💻 Author

**Pablo (Webixly)**
Cybersecurity & Networking Enthusiast
[GitHub Profile](https://github.com/webixly)

---

⭐ *Prepared as a professional educational resource for university presentation.*
