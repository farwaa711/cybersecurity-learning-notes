# Subnetting

## What is Subnetting?

**Subnetting** is the process of dividing a large network into smaller, manageable networks called **subnets**.

Subnetting improves network performance, security, and efficient use of IP addresses.

---

## Why is Subnetting Needed?

Without subnetting:

- Large networks become crowded.
- Broadcast traffic increases.
- Performance decreases.
- Managing devices becomes difficult.

Subnetting solves these problems by splitting one network into multiple smaller networks.

---

## Example

Suppose we have the network:

```
192.168.1.0/24
```

A `/24` network has **256 IP addresses**.

Instead of using one large network, we can divide it into smaller subnets.

Example:

```
Subnet 1
192.168.1.0/26

Subnet 2
192.168.1.64/26

Subnet 3
192.168.1.128/26

Subnet 4
192.168.1.192/26
```

Each subnet contains **64 IP addresses**.

---

## What is a Subnet Mask?

A **Subnet Mask** identifies which part of an IP address represents the **network** and which part represents the **host**.

Example:

```
IP Address

192.168.1.25

Subnet Mask

255.255.255.0
```

CIDR notation:

```
/24
```

Both represent the same subnet.

---

## Common CIDR Prefixes

| CIDR | Subnet Mask | Total IPs |
|------|-------------|-----------|
| /8 | 255.0.0.0 | 16,777,216 |
| /16 | 255.255.0.0 | 65,536 |
| /24 | 255.255.255.0 | 256 |
| /25 | 255.255.255.128 | 128 |
| /26 | 255.255.255.192 | 64 |
| /27 | 255.255.255.224 | 32 |
| /28 | 255.255.255.240 | 16 |
| /29 | 255.255.255.248 | 8 |
| /30 | 255.255.255.252 | 4 |

---

## Network Address

The **Network Address** identifies the subnet.

Example:

```
192.168.1.0/24
```

Network Address:

```
192.168.1.0
```

---

## Broadcast Address

The **Broadcast Address** is used to send data to every device in the subnet.

Example:

```
192.168.1.255
```

---

## Usable Host Addresses

Example:

Network:

```
192.168.1.0/24
```

| Address | Value |
|----------|-------|
| Network Address | 192.168.1.0 |
| First Host | 192.168.1.1 |
| Last Host | 192.168.1.254 |
| Broadcast Address | 192.168.1.255 |

Usable Hosts:

```
254
```

---

## Advantages of Subnetting

- Better network performance
- Reduced broadcast traffic
- Improved security
- Easier troubleshooting
- Efficient IP address management

---

## Commands

### Linux

Display IP address:

```bash
ip a
```

Display routing table:

```bash
ip route
```

---

### Windows

```cmd
ipconfig
```

---

## Key Points

- Subnetting divides a large network into smaller subnetworks.
- A subnet mask separates the network and host portions of an IP address.
- CIDR notation represents the subnet mask using a prefix length (for example, `/24`).
- Every subnet has:
  - Network Address
  - Usable Host Addresses
  - Broadcast Address
- Subnetting improves efficiency and security.

---

## References

- Cisco Networking Academy
- CompTIA Network+
- RFC 950 – Internet Standard Subnetting Procedure
