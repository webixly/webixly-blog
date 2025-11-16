# Computer Architecture Fundamentals: A Cybersecurity Perspective

**Level:** Intermediate\
**Category:** Computer Fundamentals for Cybersecurity\
**Author:** Hemia Mouhamed Aymen \| Electrical Engineering Student\
**Academic Context:** USTHB University \| MSc Cybersecurity Candidate
2027

------------------------------------------------------------------------

## 🎯 Executive Summary

This document demonstrates my systematic approach to understanding
computer systems from a cybersecurity perspective. As an Electrical
Engineering student transitioning into cybersecurity, I bridge
hardware-level understanding with software security applications.

------------------------------------------------------------------------

## 🔬 Technical Deep Dive

### Computer System Architecture

A computer is an electronic device that processes information through
coordinated hardware and software components. My electrical engineering
background provides unique insights into the physical layer of
computing.

### Hardware-Software Integration

-   **Hardware Layer**: Physical components (CPU, RAM, storage,
    motherboard)\
-   **Software Layer**: Operating systems, applications, and security
    protocols\
-   **Security Interface**: The critical intersection where
    vulnerabilities emerge

------------------------------------------------------------------------

## ⚙️ Component Security Analysis

### 🧠 CPU Architecture & Security

**Technical Analysis:** - Instruction execution pipeline and potential
hijacking points\
- Multi-core processing security implications\
- Cache-based side-channel attack vectors

**My Research Focus:** - Analyzing Spectre/Meltdown vulnerabilities at
architectural level\
- Developing CPU performance benchmarks for anomaly detection

------------------------------------------------------------------------

### 💾 Memory Hierarchy Security

**RAM Security Challenges:** - Volatile memory forensics and data
recovery\
- Memory allocation vulnerabilities (heap/stack attacks)\
- DMA (Direct Memory Access) security risks

**Practical Implementation:**

``` python
# Advanced memory analysis script
import psutil
import struct

def analyze_memory_patterns():
    \"\"\"Analyze memory usage patterns for security anomalies\"\"\"
    processes = []
    for proc in psutil.process_iter(['pid', 'name', 'memory_info']):
        try:
            mem_usage = proc.info['memory_info'].rss / 1024 / 1024  # MB
            processes.append({
                'pid': proc.info['pid'],
                'name': proc.info['name'],
                'memory_mb': round(mem_usage, 2)
            })
        except (psutil.NoSuchProcess, psutil.AccessDenied):
            continue

    processes.sort(key=lambda x: x['memory_mb'], reverse=True)
    return processes[:10]
```

------------------------------------------------------------------------

## 💽 Storage System Security

**Threat Model Analysis:** - Data persistence vs. data remanence
implications\
- SSD vs. HDD vulnerability profiles\
- Firmware-level storage attacks

------------------------------------------------------------------------

## 🛡️ Hands-On Security Labs

### Lab 1: Comprehensive System Reconnaissance

``` bash
#!/bin/bash
# Advanced system security assessment script

echo "=== SYSTEM SECURITY BASELINE ==="
echo "Timestamp: $(date)"
echo "---------------------------------"

# Hardware Security Assessment
echo "### HARDWARE SECURITY ###"
sudo dmidecode -t processor | grep -E "(Version|Core Count|Current Speed)"
sudo dmidecode -t memory | grep -E "(Size|Speed|Type)"
sudo lshw -short | grep -E "(disk|network|processor)"

# Firmware Security
echo "### FIRMWARE SECURITY ###"
sudo cat /sys/class/dmi/id/bios_version
sudo efibootmgr 2>/dev/null || echo "UEFI not available"

# Running Services Analysis
echo "### SERVICES & PORTS ###"
ss -tulnp | awk 'NR>1 {print $5, $7}' | sort -u
sudo netstat -tulnp 2>/dev/null | grep LISTEN

# Security Configuration
echo "### SECURITY CONFIG ###"
sudo getenforce 2>/dev/null || echo "SELinux not available"
sudo ufw status 2>/dev/null || echo "UFW not available"
```

------------------------------------------------------------------------

### Lab 2: Advanced Python Security Monitor

``` python
#!/usr/bin/env python3
\"\"\"
Advanced System Security Monitoring Tool
Developed as part of my cybersecurity preparation journey
\"\"\"

import psutil
import datetime
import json
from collections import defaultdict

class AdvancedSecurityMonitor:
    def __init__(self):
        self.baseline_established = False
        self.process_baseline = set()

    def establish_baseline(self):
        current_processes = {p.pid for p in psutil.process_iter()}
        self.process_baseline = current_processes
        self.baseline_established = True
        print("Baseline established")

    def detect_anomalies(self):
        if not self.baseline_established:
            self.establish_baseline()
            return {}

        current_processes = {p.pid for p in psutil.process_iter()}
        new_processes = current_processes - self.process_baseline

        anomalies = {
            'timestamp': str(datetime.datetime.now()),
            'new_processes': len(new_processes),
            'suspicious_ports': self.check_suspicious_ports(),
            'high_cpu_processes': self.get_high_cpu_processes(),
            'network_anomalies': self.check_network_anomalies()
        }
        return anomalies

    def check_suspicious_ports(self):
        suspicious_ports = []
        for conn in psutil.net_connections(kind='inet'):
            if conn.status == 'LISTEN' and conn.laddr.port > 30000:
                suspicious_ports.append(conn.laddr.port)
        return suspicious_ports

    def get_high_cpu_processes(self):
        high_cpu = []
        for proc in psutil.process_iter(['pid', 'name', 'cpu_percent']):
            try:
                if proc.info['cpu_percent'] > 20.0:
                    high_cpu.append(proc.info)
            except (psutil.NoSuchProcess, psutil.AccessDenied):
                continue
        return high_cpu

    def check_network_anomalies(self):
        connections = psutil.net_connections()
        conn_by_remote = defaultdict(int)

        for conn in connections:
            if conn.raddr:
                conn_by_remote[conn.raddr.ip] += 1

        return {ip: count for ip, count in conn_by_remote.items() if count > 10}

if __name__ == "__main__":
    monitor = AdvancedSecurityMonitor()
    anomalies = monitor.detect_anomalies()
    print("Security Anomalies Detected:")
    print(json.dumps(anomalies, indent=2))
```

------------------------------------------------------------------------

## 🎓 Academic Integration

### Connecting Electrical Engineering to Cybersecurity

-   Signal Processing → Network traffic pattern analysis\
-   Circuit Theory → Hardware-based attack vectors\
-   Control Systems → System stability models for security

### Research Directions

-   Hardware-Assisted Security\
-   Energy-Based Intrusion Detection\
-   Embedded Systems Security for IoT

------------------------------------------------------------------------

## 📊 Project Portfolio Integration

-   Network Security Analyzer\
-   System Hardening Scripts\
-   Malware Execution Environment Analysis

------------------------------------------------------------------------

## 🔐 Professional Insights

-   Defense in depth through architectural understanding\
-   Proactive security via behavior baselining\
-   Cross-disciplinary approach to solving security challenges

------------------------------------------------------------------------

## 🚀 Next Evolution

Developing specialized security tools and contributing to academic
research in system security architecture.
