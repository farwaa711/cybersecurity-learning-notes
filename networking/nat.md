# Network Address Translation (NAT)

## What is NAT?

**Network Address Translation (NAT)** is a networking technique used by routers to translate **private IP addresses** into **public IP addresses** and vice versa.

NAT allows multiple devices on a private network to share a single public IP address when accessing the Internet.

---

## Why is NAT Needed?

Private IP addresses cannot be used directly on the Internet.

A router uses NAT to:

- Allow private devices to access the Internet
- Reduce the number of public IP addresses required
- Improve network security by hiding internal IP addresses

---

## Example

Suppose a home network has three devices:

| Device | Private IP |
|---------|------------|
| Laptop | 192.168.1.10 |
| Phone | 192.168.1.20 |
| Smart TV | 192.168.1.30 |

The router has one public IP:

```
203.0.113.5
```

When these devices access the Internet, the router translates their private IP addresses to the single public IP.

```
Laptop (192.168.1.10)
        |
Phone (192.168.1.20)
        |
TV (192.168.1.30)
        |
     Router (NAT)
        |
Public IP: 203.0.113.5
        |
      Internet
```

---

## How NAT Works

1. A device sends a packet to the router.
2. The router replaces the source private IP with its public IP.
3. The packet is sent to the Internet.
4. The destination server replies.
5. The router checks its NAT table.
6. The router forwards the reply to the correct internal device.

---

## Types of NAT

### 1. Static NAT

- One private IP maps to one public IP.
- Used for servers that must always have the same public address.

Example:

```
192.168.1.10
↓

203.0.113.10
```

---

### 2. Dynamic NAT

- Maps private IPs to available public IPs from a pool.
- The mapping changes based on availability.

---

### 3. PAT (Port Address Translation)

Also called **NAT Overload**.

- Many private IP addresses share one public IP.
- Uses different port numbers to distinguish connections.
- Most commonly used in home and office networks.

---

## NAT Table

Example:

| Private IP | Public IP | Port |
|------------|-----------|------|
| 192.168.1.10 | 203.0.113.5 | 50001 |
| 192.168.1.20 | 203.0.113.5 | 50002 |
| 192.168.1.30 | 203.0.113.5 | 50003 |

---

## Advantages

- Conserves public IPv4 addresses.
- Allows multiple devices to share one public IP.
- Hides internal network structure.
- Adds a basic layer of security.

---

## Disadvantages

- Can make troubleshooting more difficult.
- Some applications require port forwarding.
- Does not replace a firewall.

---

## NAT and Cybersecurity

NAT provides basic protection because devices on the Internet cannot directly access private devices unless configured.

However:

- NAT is **not** a firewall.
- A firewall should still be used to filter unwanted traffic.

---

## Commands

### Linux

Display routing information:

```bash
ip route
```

Show network interfaces:

```bash
ip a
```

---

### Windows

View IP configuration:

```cmd
ipconfig
```

---

## Key Points

- NAT stands for **Network Address Translation**.
- It translates private IP addresses to public IP addresses.
- It allows multiple devices to share one public IP.
- NAT is performed by routers.
- The three main types are:
  - Static NAT
  - Dynamic NAT
  - PAT (NAT Overload)

---

## References

- RFC 3022 – Traditional NAT
- Cisco Networking Academy
- CompTIA Network+
