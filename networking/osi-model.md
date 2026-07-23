# OSI Model

## What is the OSI Model?

The **Open Systems Interconnection (OSI) Model** is a conceptual framework that explains how data travels from one device to another over a network.

It divides network communication into **7 layers**, with each layer performing a specific function.

---

# Why is the OSI Model Important?

The OSI Model helps:

- Understand how networks work
- Troubleshoot network problems
- Design and secure networks
- Analyze cyber attacks
- Understand where protocols operate

---

# The 7 Layers of the OSI Model

```
+-----------------------+
| 7. Application        |
+-----------------------+
| 6. Presentation       |
+-----------------------+
| 5. Session            |
+-----------------------+
| 4. Transport          |
+-----------------------+
| 3. Network            |
+-----------------------+
| 2. Data Link          |
+-----------------------+
| 1. Physical           |
+-----------------------+
```

---

# Layer 7 – Application

### Purpose

Provides network services directly to end users and applications.

### Examples

- HTTP
- HTTPS
- FTP
- SMTP
- DNS

### Cybersecurity

- SQL Injection
- Cross-Site Scripting (XSS)
- Authentication attacks

---

# Layer 6 – Presentation

### Purpose

Formats, encrypts, and compresses data.

### Responsibilities

- Data encryption
- Data decryption
- Data compression
- Data translation

### Examples

- SSL/TLS
- JPEG
- PNG
- MP4

---

# Layer 5 – Session

### Purpose

Establishes, manages, and terminates communication sessions.

### Responsibilities

- Session management
- Authentication
- Synchronization

### Example

A user logging into a website and maintaining an active session.

---

# Layer 4 – Transport

### Purpose

Provides reliable or fast communication between devices.

### Protocols

- TCP
- UDP

### Responsibilities

- Segmentation
- Flow control
- Error recovery
- Reliability

---

# Layer 3 – Network

### Purpose

Determines the best path for data.

### Protocols

- IP
- ICMP

### Devices

- Routers

### Responsibilities

- Routing
- Logical addressing
- Packet forwarding

---

# Layer 2 – Data Link

### Purpose

Transfers data between devices on the same local network.

### Devices

- Switches

### Responsibilities

- MAC addressing
- Error detection
- Frame delivery

---

# Layer 1 – Physical

### Purpose

Transmits raw bits through physical media.

### Examples

- Ethernet cables
- Fiber optic cables
- Wi-Fi radio signals

### Devices

- Hubs
- Repeaters
- Network cables

---

# Data Encapsulation

When sending data:

```
Application Data
      ↓
Segment
      ↓
Packet
      ↓
Frame
      ↓
Bits
```

When receiving data, the process happens in reverse.

---

# Devices by Layer

| Device | OSI Layer |
|---------|----------|
| Hub | Layer 1 |
| Switch | Layer 2 |
| Router | Layer 3 |
| Firewall | Layer 3–7 (depending on type) |

---

# OSI Model in Cybersecurity

Understanding the OSI Model helps security professionals:

- Analyze packet captures
- Configure firewalls
- Investigate attacks
- Troubleshoot networks
- Understand where vulnerabilities exist

Examples:

- Layer 3 → IP spoofing
- Layer 4 → Port scanning
- Layer 7 → SQL Injection, XSS

---

# Mnemonic

From Layer 7 to Layer 1:

**All People Seem To Need Data Processing**

From Layer 1 to Layer 7:

**Please Do Not Throw Sausage Pizza Away**

---

# Summary

- The OSI Model has 7 layers.
- Each layer has a specific responsibility.
- Different protocols and devices operate at different layers.
- The model is widely used for networking and cybersecurity troubleshooting.
