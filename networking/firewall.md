# Firewall

## What is a Firewall?

A **firewall** is a network security device or software that monitors and controls incoming and outgoing network traffic based on predefined security rules.

Its primary purpose is to **protect a network or device from unauthorized access** while allowing legitimate traffic.

---

## Why is a Firewall Needed?

Without a firewall:

- Anyone on the Internet could attempt to access your device.
- Malicious traffic could enter the network.
- Sensitive information could be exposed.

A firewall acts as a **security barrier** between a trusted network and an untrusted network.

---

## How a Firewall Works

When a packet reaches the firewall:

1. The firewall inspects the packet.
2. It compares the packet against its security rules.
3. The firewall decides whether to:
   - Allow the packet
   - Block the packet
   - Log the packet for monitoring

---

## Types of Firewalls

### 1. Packet Filtering Firewall

- Examines source IP, destination IP, ports, and protocol.
- Fast and simple.
- Does not inspect packet contents.

---

### 2. Stateful Firewall

- Tracks active network connections.
- Allows packets that belong to established sessions.
- More secure than packet filtering.

---

### 3. Proxy Firewall

- Acts as an intermediary between the client and server.
- Inspects application traffic.
- Provides better security but may reduce performance.

---

### 4. Next-Generation Firewall (NGFW)

Modern firewalls include features such as:

- Deep Packet Inspection (DPI)
- Intrusion Prevention System (IPS)
- Malware Detection
- Application Control
- URL Filtering

---

## Firewall Rules

Example:

| Source | Destination | Port | Action |
|---------|-------------|------|--------|
| Any | Web Server | 80 | Allow |
| Any | Web Server | 443 | Allow |
| Any | SSH Server | 22 | Deny |

---

## Firewall Deployment

```
Internet
     |
     |
+------------+
|  Firewall  |
+------------+
     |
     |
 Local Network
     |
+-----------+
| Computers |
+-----------+
```

The firewall filters all traffic entering and leaving the local network.

---

## Advantages

- Blocks unauthorized access.
- Helps prevent cyber attacks.
- Monitors network traffic.
- Protects sensitive systems.
- Enforces security policies.

---

## Limitations

- Cannot stop attacks originating from inside the network.
- Incorrect configuration may block legitimate traffic.
- Does not protect against every type of cyber attack.

---

## Common Firewall Attacks

Attackers may attempt to:

- Scan open ports
- Bypass firewall rules
- Exploit misconfigured firewalls
- Tunnel malicious traffic through allowed ports

---

## Best Practices

- Allow only required ports.
- Block unused services.
- Keep firewall software updated.
- Monitor firewall logs.
- Review firewall rules regularly.
- Use the principle of least privilege.

---

## Host-Based vs Network Firewall

| Host-Based Firewall | Network Firewall |
|---------------------|------------------|
| Protects one device | Protects an entire network |
| Installed on a computer | Installed on a router or dedicated appliance |
| Example: Windows Defender Firewall | Example: Cisco ASA |

---

## Common Firewall Ports

| Port | Service |
|------|---------|
| 22 | SSH |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |
| 25 | SMTP |

---

## Linux Commands

Check firewall status (UFW):

```bash
sudo ufw status
```

Enable UFW:

```bash
sudo ufw enable
```

Allow SSH:

```bash
sudo ufw allow 22
```

Allow HTTP:

```bash
sudo ufw allow 80
```

Allow HTTPS:

```bash
sudo ufw allow 443
```

---

## Key Points

- A firewall monitors and filters network traffic.
- Firewalls enforce security rules.
- They help prevent unauthorized access.
- Firewalls can be hardware or software.
- Next-Generation Firewalls provide advanced security features.
- A firewall is an important layer of network defense but is not a complete security solution by itself.

---

## References

- Cisco Networking Academy
- CompTIA Network+
- NIST SP 800-41 – Guidelines on Firewalls and Firewall Policy
