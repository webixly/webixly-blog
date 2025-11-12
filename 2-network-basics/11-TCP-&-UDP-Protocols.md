# 🌐 TCP & UDP Protocols

## 🧩 Introduction

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the primary transport layer protocols used in networking. They define how data is transmitted between devices over IP networks, each with distinct mechanisms, advantages, and limitations.

Mastering TCP and UDP is crucial for **network configuration, performance optimization, cybersecurity, and application development**.

---

## 📘 TCP (Transmission Control Protocol)

TCP is a **connection-oriented** protocol that provides reliable, ordered, and error-checked delivery of data between applications.

### Key Features

1. **Connection-Oriented:** A TCP session starts with a **three-way handshake** (SYN → SYN-ACK → ACK) before data transfer.
2. **Reliability:** Guarantees that all packets reach their destination correctly and in order.
3. **Flow Control:** Uses a sliding window mechanism to manage data flow and prevent congestion.
4. **Error Detection and Correction:** Uses checksums and retransmission for lost or corrupted packets.
5. **Segmentation:** Splits large messages into smaller segments for transmission, then reassembles them at the receiver.

### Common TCP Ports

| Service | Port |
| ------- | ---- |
| HTTP    | 80   |
| HTTPS   | 443  |
| FTP     | 21   |
| SSH     | 22   |
| SMTP    | 25   |

### Use Cases

* Web browsing (HTTP/HTTPS)
* Email transmission (SMTP, IMAP, POP3)
* File transfer (FTP, SFTP)
* Database communication (MySQL, PostgreSQL)

**Example:** Establishing a TCP connection to a web server:

```
TCP connection to 192.168.1.1:80
```

---

## 📘 UDP (User Datagram Protocol)

UDP is a **connectionless** protocol designed for speed and low overhead. It does not guarantee delivery, order, or error correction.

### Key Features

1. **Connectionless:** No handshake or session establishment required.
2. **Unreliable:** No acknowledgments or retransmissions.
3. **Low Latency:** Minimal protocol overhead allows fast data transfer.
4. **No Segmentation Control:** Sends messages as datagrams without ensuring order.

### Common UDP Ports

| Service | Port    |
| ------- | ------- |
| DNS     | 53      |
| DHCP    | 67/68   |
| SNMP    | 161     |
| TFTP    | 69      |
| VoIP    | Various |

### Use Cases

* Real-time video/audio streaming
* Online gaming
* DNS queries and responses
* Voice over IP (VoIP)

**Example:** Sending a DNS request using UDP:

```
UDP packet sent to 8.8.8.8:53
```

---

## 🔄 TCP vs UDP: Detailed Comparison

| Feature            | TCP                            | UDP                          |
| ------------------ | ------------------------------ | ---------------------------- |
| Type               | Connection-oriented            | Connectionless               |
| Reliability        | Reliable, error-checked        | Unreliable                   |
| Ordering           | Ensures in-order delivery      | No ordering guarantee        |
| Flow Control       | Yes (sliding window)           | No                           |
| Congestion Control | Yes                            | No                           |
| Speed              | Slower due to overhead         | Faster due to low overhead   |
| Header Size        | 20 bytes minimum               | 8 bytes                      |
| Use Cases          | Web, Email, File transfer      | Streaming, Gaming, DNS, VoIP |
| Error Handling     | Retransmission, acknowledgment | None                         |

---

## ⚙️ Practical Examples

**TCP Scan with Nmap:**

```
nmap -sT 192.168.1.1
```

**UDP Scan with Nmap:**

```
nmap -sU 192.168.1.1
```

**Wireshark Example:**

* TCP handshake: observe SYN, SYN-ACK, ACK packets.
* UDP packet: observe datagram with no handshake or acknowledgment.

**Programming Example (Python):**

```python
# TCP Client

import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(('example.com', 80))
s.send(b'GET / HTTP/1.1\r\nHost: example.com\r\n\r\n')
print(s.recv(1024))
s.close()

# UDP Client

import socket
s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
s.sendto(b'Hello', ('example.com', 12345))
response, addr = s.recvfrom(1024)
print(response)
s.close()
```

---

## 💡 Tip

* Use **TCP** for applications where **reliability, order, and error correction** are essential.
* Use **UDP** for applications requiring **speed, low latency, and tolerance to packet loss**.

---

### 🧑‍💻 Author

**Pablo (Webixly)**
Cybersecurity & Networking Enthusiast
[GitHub Profile](https://github.com/webixly)

---

⭐ *Prepared as a professional educational resource for university presentation.*
