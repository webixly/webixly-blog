# 🧮 Lesson 01 — Number Systems  
### Computer Fundamentals for Cybersecurity  
### USTHB University → MSc Cybersecurity Preparation 2025–2027  

---


## 🎯 Lesson Purpose  
This foundational lesson builds the essential mathematical and logical understanding of number systems. These concepts are the basis for cryptography, network protocol analysis, security encoding, malware analysis, and digital forensics.

---

# 🔥 1. Executive Summary  

Number systems form the **language of computers** and the foundation of all cybersecurity technologies.  
Cryptographic algorithms, memory forensics, malware payloads, hashing functions, and network protocols all rely directly on binary, hexadecimal, and modular arithmetic.

This lesson ensures strong mastery of:

- Binary representation  
- Hexadecimal notation  
- Base conversions  
- Bitwise operations  
- Entropy & data strength  
- Encoding & obfuscation techniques  
- Cryptographic primitives using number systems  

---

# 🔢 2. Number Systems Fundamentals  

Computers operate strictly using binary logic. Cybersecurity requires understanding this representation for:

- Packet inspection  
- Memory analysis  
- Hashing  
- Encryption  
- Reverse engineering  
- Firmware analysis  

### 🟦 Supported Number Systems  

| System | Base | Digits Used | Cybersecurity Use |
|--------|------|--------------|--------------------|
| **Binary** | 2 | 0–1 | Cryptography, hashing, networking |
| **Hexadecimal** | 16 | 0–F | Memory, forensics, disassembly |
| **Decimal** | 10 | 0–9 | Human interpretation |
| **Octal** | 8 | 0–7 | File permissions (Unix), legacy computing |

---

# 🧮 3. Mathematical Concepts  

### ✔ Positional Notation  
Each digit’s value depends on its position multiplied by the base's power.

Example:  
Hex number `0x3AF`:

3 × 16² + 10 × 16¹ + 15 × 16⁰

---

### ✔ Base Conversion Algorithms  

#### 🔄 Decimal → Binary  
Divide by 2 and track remainders.

#### 🔄 Binary → Hex  
Group bits in sets of 4.

#### 🔄 Decimal → Hex  
Divide by 16 and convert remainders.

---

### ✔ Bitwise Operations  
Cybersecurity relies heavily on these operations.

| Operator | Symbol | Effect |
|----------|--------|--------|
| AND | `&` | Masking bits |
| OR | `\|` | Setting bits |
| NOT | `~` | Bit inversion |
| XOR | `^` | Cryptography, encryption |

---

# 🛡️ 4. Cybersecurity Applications  

## 🔐 Cryptography  

### ✔ XOR Cipher  
The XOR operation is the mathematical backbone of:

- Stream ciphers  
- PRNG generators  
- OTP encryption  
- Hash function mixing  

Example:

```python
def xor_cipher(data, key):
    return bytes([data[i] ^ key[i % len(key)] for i in range(len(data))])
```

---

## 🔍 Digital Forensics  
Hexadecimal used in:

- Memory dumps  
- Disk imaging  
- Malware signatures  
- Hash values  

Example:

```
4D 5A 90 00 — file header of a Windows EXE
```

---

## 🌐 Network Security  
Binary and hex are required for:

- Packet dissection  
- Protocol decoding  
- Payload extraction  
- Steganography detection  

---

# 💻 5. Full Project: Number Systems Security Toolkit  

This is your first advanced security tool built using mathematical foundations.

```python
#!/usr/bin/env python3
"""
Number Systems Security Toolkit
Cryptographic applications of number system conversions
"""

class NumberSystemSecurity:
    def __init__(self):
        self.character_sets = {
            'binary': '01',
            'decimal': '0123456789',
            'hexadecimal': '0123456789ABCDEF',
            'base64': 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
        }
    
    def analyze_entropy(self, data, base_system):
        """Calculate information entropy for security assessment"""
        from math import log2
        
        base = 2 if base_system == 'binary' else \
               16 if base_system == 'hexadecimal' else \
               len(self.character_sets[base_system])
        
        entropy = len(data) * log2(base)
        return entropy
    
    def xor_encrypt(self, plaintext, key):
        """Basic XOR encryption demonstrating bitwise operations"""
        encrypted = []
        key_length = len(key)
        
        for i, char in enumerate(plaintext):
            key_char = key[i % key_length]
            encrypted_char = chr(ord(char) ^ ord(key_char))
            encrypted.append(encrypted_char)
        
        return ''.join(encrypted)
    
    def password_strength_analysis(self, password):
        """Analyze password strength using number system concepts"""
        import string
        
        char_sets_used = 0
        if any(c in string.digits for c in password):
            char_sets_used += 10
        if any(c in string.ascii_lowercase for c in password):
            char_sets_used += 26
        if any(c in string.ascii_uppercase for c in password):
            char_sets_used += 26
        if any(c in string.punctuation for c in password):
            char_sets_used += 32
        
        possible_combinations = char_sets_used ** len(password)
        time_to_crack = possible_combinations / (1e9 * 3600)
        
        return {
            'password_length': len(password),
            'character_set_size': char_sets_used,
            'possible_combinations': possible_combinations,
            'estimated_crack_time_hours': time_to_crack
        }

# Demonstration
if __name__ == "__main__":
    nst = NumberSystemSecurity()
    
    print("\n--- Entropy Calculation ---")
    entropy = nst.analyze_entropy("110010101001", 'binary')
    print(f"Binary Data Entropy: {entropy:.2f} bits")
    
    print("\n--- XOR Encryption Demo ---")
    message = "ConfidentialData"
    key = "SecretKey"
    encrypted = nst.xor_encrypt(message, key)
    decrypted = nst.xor_encrypt(encrypted, key)
    print("Original:", message)
    print("Encrypted:", encrypted)
    print("Decrypted:", decrypted)
    
    print("\n--- Password Strength ---")
    strength = nst.password_strength_analysis("MySecure123!")
    print(strength)
```

---

# 🧪 6. Security Lab Exercises  

## 🧩 Lab 1 — Base Conversions for Cryptography  
```python
def crypto_base_conversion():
    memory_address = 4096
    hex_address = hex(memory_address)
    print(f"Memory Address: {memory_address} -> {hex_address}")
    
    binary_data = 0b11001010
    mask = 0b11110000
    result = binary_data & mask
    print(f"Bitwise AND: {bin(binary_data)} & {bin(mask)} = {bin(result)}")
```

---

## 🧩 Lab 2 — Data Obfuscation  
```python
def data_obfuscation():
    sensitive_data = "AdminPassword123"
    
    hex_representation = sensitive_data.encode().hex()
    print(f"Hex Obfuscated: {hex_representation}")
    
    restored = bytes.fromhex(hex_representation).decode()
    print(f"Restored: {restored}")
```

---

# 📚 7. Academic Integration  

### ➤ Electrical Engineering Value  
Your EE background adds powerful advantages:

- Binary logic circuits  
- Signal encoding  
- Information theory (entropy)  
- Numerical analysis  

### ➤ Cybersecurity Relevance  
Number systems apply directly in:

- Encryption  
- Memory forensics  
- Steganography  
- Protocol analysis  
- Secure coding  
- Hashing algorithms  

---

# 🎓 8. Learning Outcomes  

### ✔ Technical Competencies  
- Full mastery of number systems  
- Bitwise logic and cryptographic reasoning  
- Entropy and strength analysis  
- Development of complete security tools  

### ✔ Analytical Skills  
- Mathematical thinking applied to cybersecurity  
- System decomposition  
- Low-level data interpretation  

---

# 📅 9. Lesson Status  
**Completed: November 2025**  
Part of: *USTHB Electrical Engineering → MSc Cybersecurity Preparation (2025–2027)*  

---

> **"True cybersecurity starts with understanding how data is represented, stored, and transformed."**

