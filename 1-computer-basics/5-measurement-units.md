# ⚙️ Measurement Units in Computing  

Understanding **measurement units** in computing is fundamental for anyone studying **computer architecture**, **networking**, or **cybersecurity**.  
These units define how we **quantify data**, **storage**, and **processing speed** in digital systems.

---

## 🧮 1️⃣ The Binary Foundation  

Computers work with **binary numbers (0 and 1)**.  
Each binary digit is called a **bit** — the smallest unit of data.  

| Unit | Symbol | Equivalent | Description |
|------|---------|-------------|--------------|
| **Bit** | b | 0 or 1 | Smallest data unit |
| **Byte** | B | 8 bits | Represents a single character |

> Example: The letter **A** = `01000001` → 1 byte (8 bits)

---

## 📦 2️⃣ Storage Capacity Units  

Storage is measured using multiples of bytes.  
There are two systems to represent these values:

### 🔹 Decimal System (Base 10)  
Used by **manufacturers** (1 KB = 1,000 bytes)

| Unit | Symbol | Value |
|------|---------|-------|
| Kilobyte | KB | 10³ = 1,000 bytes |
| Megabyte | MB | 10⁶ = 1,000,000 bytes |
| Gigabyte | GB | 10⁹ = 1,000,000,000 bytes |
| Terabyte | TB | 10¹² = 1,000,000,000,000 bytes |

### 🔹 Binary System (Base 2)  
Used by **operating systems** (1 KiB = 1,024 bytes)

| Unit | Symbol | Value |
|------|---------|-------|
| Kibibyte | KiB | 2¹⁰ = 1,024 bytes |
| Mebibyte | MiB | 2²⁰ = 1,048,576 bytes |
| Gibibyte | GiB | 2³⁰ = 1,073,741,824 bytes |
| Tebibyte | TiB | 2⁴⁰ = 1,099,511,627,776 bytes |

> 💡 This explains why your **“500 GB” drive** shows up as **≈465 GB** in Windows or Linux — the OS uses the binary system.

---

## 🚀 3️⃣ Data Transfer & Speed Units  

When discussing **network speed** or **data transfer**, we use **bits per second (bps)**.

| Unit | Description |
|------|--------------|
| **bps** | bits per second |
| **Kbps** | kilobits per second (1,000 bps) |
| **Mbps** | megabits per second (1,000,000 bps) |
| **Gbps** | gigabits per second (1,000,000,000 bps) |

> ⚠️ **Network speeds** are measured in **bits**, while **file sizes** use **bytes**.  
To convert:  
`1 Byte = 8 bits`  
Example → 100 Mbps ≈ 12.5 MB/s

---

## 🧠 4️⃣ CPU Clock Speed  

CPU performance is often expressed in **Hertz (Hz)** — the number of cycles per second.

| Unit | Symbol | Value |
|------|---------|-------|
| **Hz** | Hertz | 1 cycle per second |
| **kHz** | Kilohertz | 1,000 Hz |
| **MHz** | Megahertz | 1,000,000 Hz |
| **GHz** | Gigahertz | 1,000,000,000 Hz |

> Example: A 3.2 GHz processor performs **3.2 billion operations per second**.

---

## 💾 5️⃣ Memory Hierarchy Example  

Here’s a real-world comparison of data sizes:

| Data Example | Approximate Size |
|---------------|------------------|
| One text character | 1 byte |
| One MP3 song | 3–5 MB |
| HD Movie | 2–4 GB |
| 4K Movie | 20–60 GB |
| Full HDD Backup | 1 TB or more |

---

## 🔍 Summary  

- Computers use **binary units** based on powers of 2.  
- **Storage** is usually in **bytes**, **speed** in **bits per second**, and **frequency** in **Hertz**.  
- Knowing these distinctions is essential for **network configuration**, **system performance analysis**, and **cybersecurity assessments**.

---

## 🧠 Next Lesson  

➡️ [CPU and RAM Explained](6-cpu-and-ram.md)
