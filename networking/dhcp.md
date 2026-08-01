# Dynamic Host Configuration Protocol (DHCP)

## What is DHCP?

**DHCP (Dynamic Host Configuration Protocol)** is a network protocol that automatically assigns **IP addresses** and other network settings to devices when they connect to a network.

Without DHCP, network administrators would have to manually configure every device.

---

## Why is DHCP Needed?

When a device joins a network, it needs:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

DHCP automatically provides all of these settings.

---

## How DHCP Works

DHCP follows a four-step process known as **DORA**.

### 1. Discover

A client broadcasts a **DHCP Discover** message to find available DHCP servers.

```
Client
   |
   |---- DHCP Discover ---->
```

---

### 2. Offer

The DHCP server responds with a **DHCP Offer**, which contains an available IP address and network configuration.

```
Server
   |
   |<---- DHCP Offer ----
```

---

### 3. Request

The client requests the offered IP address.

```
Client
   |
   |---- DHCP Request ---->
```

---

### 4. Acknowledge

The server confirms the assignment by sending a **DHCP Acknowledgement (ACK)**.

```
Server
   |
   |<---- DHCP ACK ----
```

The client can now communicate on the network.

---

## DHCP Lease

The assigned IP address is **leased** to the client for a specific period.

Example:

- Lease Time: 24 Hours

When the lease expires, the client requests a renewal.

---

## Information Provided by DHCP

A DHCP server can provide:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server
- Lease Time

---

## DHCP Ports

DHCP uses UDP.

| Device | Port |
|---------|------|
| Client | UDP 68 |
| Server | UDP 67 |

---

## Advantages

- Automatic IP assignment
- Reduces configuration errors
- Saves time
- Prevents IP address conflicts
- Easy to manage large networks

---

## Disadvantages

- Depends on the DHCP server
- If the server fails, new devices cannot obtain an IP address
- Rogue DHCP servers can distribute incorrect network settings

---

## Security Risks

Common attacks include:

### Rogue DHCP Server

An attacker installs a fake DHCP server that gives clients incorrect network information.

### DHCP Starvation Attack

An attacker floods the DHCP server with fake requests until no IP addresses remain available.

---

## Protection

- DHCP Snooping
- Port Security
- Trusted Switch Ports
- Monitor DHCP traffic
- Disable unused switch ports

---

## Commands

### Linux

View current IP address:

```bash
ip a
```

Release and renew a DHCP lease (depending on your distribution):

```bash
sudo dhclient -r
sudo dhclient
```

---

### Windows

Release the current IP:

```cmd
ipconfig /release
```

Request a new IP:

```cmd
ipconfig /renew
```

View network configuration:

```cmd
ipconfig /all
```

---

## Key Points

- DHCP stands for **Dynamic Host Configuration Protocol**.
- It automatically assigns IP addresses and network settings.
- It uses the **DORA** process:
  - Discover
  - Offer
  - Request
  - Acknowledge
- DHCP uses **UDP ports 67 and 68**.
- DHCP reduces manual configuration and prevents IP conflicts.

---

## References

- RFC 2131 – Dynamic Host Configuration Protocol
- Cisco Networking Academy
- CompTIA Network+
