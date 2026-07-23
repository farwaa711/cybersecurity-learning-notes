# TCP vs UDP

## Introduction

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are two transport layer protocols used to send data across networks.

Although both transfer data between devices, they work differently and are used for different purposes.

---

# TCP (Transmission Control Protocol)

TCP is a **connection-oriented** protocol.

Before sending data, it establishes a connection between the sender and receiver.

### Features

- Reliable
- Connection-oriented
- Error checking
- Data arrives in order
- Retransmits lost packets

### Common Uses

- HTTP
- HTTPS
- SSH
- FTP
- Email (SMTP, IMAP, POP3)

---

# UDP (User Datagram Protocol)

UDP is a **connectionless** protocol.

It sends data without first establishing a connection.

### Features

- Fast
- Lightweight
- No guarantee of delivery
- No retransmission
- Data may arrive out of order

### Common Uses

- DNS
- VoIP (Internet calls)
- Video streaming
- Online gaming
- DHCP

---

# TCP Three-Way Handshake

Before communication begins, TCP performs a three-step process.

```
Client                    Server

SYN   ------------------>

      <------------------  SYN-ACK

ACK   ------------------>
```

### Step 1: SYN

The client requests a connection.

### Step 2: SYN-ACK

The server acknowledges the request and responds.

### Step 3: ACK

The client confirms the connection.

Now data transmission begins.

---

# TCP Connection Termination

TCP closes a connection using a four-step process:

1. FIN
2. ACK
3. FIN
4. ACK

This ensures both sides finish communication properly.

---

# TCP vs UDP Comparison

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Yes | No |
| Reliability | High | Low |
| Speed | Slower | Faster |
| Error Checking | Yes | Limited |
| Packet Order | Guaranteed | Not guaranteed |
| Retransmission | Yes | No |

---

# Advantages of TCP

- Reliable communication
- Ordered delivery
- Error recovery
- Suitable for important data

---

# Advantages of UDP

- Very fast
- Low latency
- Less overhead
- Ideal for real-time applications

---

# Cybersecurity Perspective

Understanding TCP and UDP helps security professionals:

- Analyze network traffic
- Detect attacks
- Perform port scanning
- Troubleshoot connectivity
- Investigate suspicious activity

Examples:

- Nmap can perform TCP scans.
- DNS commonly uses UDP on port 53.
- HTTPS uses TCP on port 443.

---

# Summary

- TCP is reliable and connection-oriented.
- UDP is faster but does not guarantee delivery.
- TCP uses a three-way handshake before communication.
- Both protocols are essential for networking and cybersecurity.
