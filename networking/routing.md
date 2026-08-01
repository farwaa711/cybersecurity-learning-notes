# Routing

## What is Routing?

**Routing** is the process of forwarding data packets from one network to another using a **router**.

When a device wants to communicate with another device on a different network, the router determines the best path for the packet to reach its destination.

---

## What is a Router?

A **router** is a network device that connects two or more different networks and forwards packets based on their **IP addresses**.

Unlike a switch, which uses MAC addresses, a router uses IP addresses to make forwarding decisions.

---

## How Routing Works

Suppose:

- PC A
  - IP: 192.168.1.10

- Router
  - Interface 1: 192.168.1.1
  - Interface 2: 10.0.0.1

- PC B
  - IP: 10.0.0.20

### Step 1

PC A wants to send data to PC B.

### Step 2

PC A checks whether the destination is on the same network.

Since it is not, PC A sends the packet to its **Default Gateway** (the router).

### Step 3

The router examines the destination IP address.

### Step 4

The router checks its **Routing Table**.

### Step 5

The router forwards the packet through the correct interface toward the destination network.

---

## Routing Table

A routing table contains information about available networks and the best path to reach them.

Example:

| Destination Network | Gateway | Interface |
|---------------------|----------|-----------|
| 192.168.1.0/24 | Directly Connected | eth0 |
| 10.0.0.0/24 | Directly Connected | eth1 |
| 172.16.0.0/16 | 10.0.0.2 | eth1 |

---

## Types of Routing

### 1. Static Routing

- Routes are manually configured.
- Suitable for small networks.
- Easy to understand.
- Requires manual updates.

---

### 2. Dynamic Routing

Routers automatically learn routes using routing protocols.

Examples:

- RIP
- OSPF
- EIGRP
- BGP

Suitable for large and changing networks.

---

## Default Gateway

A **Default Gateway** is the router that a device uses to send packets to other networks.

Example:

```
Default Gateway:
192.168.1.1
```

Without a default gateway, a device cannot communicate outside its own network.

---

## Router vs Switch

| Router | Switch |
|---------|--------|
| Uses IP addresses | Uses MAC addresses |
| Works at Layer 3 | Works at Layer 2 |
| Connects different networks | Connects devices within the same network |
| Makes routing decisions | Forwards Ethernet frames |

---

## Advantages of Routing

- Connects multiple networks
- Finds the best path for data
- Supports communication over the Internet
- Reduces unnecessary network traffic

---

## Common Routing Protocols

### RIP
- Simple
- Uses hop count
- Best for small networks

### OSPF
- Fast convergence
- Used in enterprise networks

### EIGRP
- Cisco proprietary (originally)
- Efficient and scalable

### BGP
- Used between Internet Service Providers (ISPs)
- Powers the Internet

---

## Security Considerations

Attackers may target routers through:

- Route Hijacking
- Routing Table Poisoning
- Denial-of-Service (DoS)
- Unauthorized Router Access

Protection methods include:

- Strong passwords
- Access Control Lists (ACLs)
- Firmware updates
- Secure routing protocols
- Disable unused services

---

## Key Points

- Routing moves packets between different networks.
- Routers operate at **OSI Layer 3 (Network Layer)**.
- Routers forward packets using **IP addresses**.
- Routing tables determine the best path.
- Static routing is manual.
- Dynamic routing uses routing protocols.
- The default gateway allows communication with other networks.

---

## References

- Cisco Networking Academy
- CompTIA Network+
- RFC 1812 – Requirements for IP Routers
