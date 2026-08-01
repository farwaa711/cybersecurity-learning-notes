# MAC Address

## What is a MAC Address?

A **MAC (Media Access Control) Address** is a unique hardware identifier assigned to a network interface card (NIC). It is used to identify devices on a **Local Area Network (LAN)**.

Unlike an IP address, which can change, a MAC address is usually assigned by the manufacturer and remains the same.

---

## Format of a MAC Address

A MAC address consists of **48 bits (6 bytes)** and is written as six pairs of hexadecimal numbers.

### Example

```
00:1A:2B:3C:4D:5E
```

or

```
00-1A-2B-3C-4D-5E
```

Each pair contains hexadecimal digits (0-9 and A-F).

---

## MAC Address vs IP Address

| MAC Address | IP Address |
|-------------|------------|
| Physical address | Logical address |
| Assigned by manufacturer | Assigned by network/router |
| Used inside a LAN | Used across networks |
| Usually does not change | Can change |
| Works at OSI Layer 2 | Works at OSI Layer 3 |

---

## Where is a MAC Address Used?

A MAC address is used to:

- Identify devices on a local network
- Deliver Ethernet frames
- Allow switches to forward data correctly
- Support communication within the same LAN

---

## Structure of a MAC Address

A MAC address has two parts:

1. **OUI (Organizationally Unique Identifier)**
   - First 24 bits
   - Identifies the manufacturer

2. **Device Identifier**
   - Last 24 bits
   - Uniquely identifies the device

Example:

```
00:1A:2B : 3C:4D:5E
^^^^^^^^   ^^^^^^^^^
Manufacturer  Device ID
```

---

## OSI Layer

MAC addresses operate at:

**OSI Layer 2 – Data Link Layer**

---

## How to Find Your MAC Address

### Linux

```bash
ip link
```

or

```bash
ip a
```

or

```bash
ifconfig
```

---

### Windows

```cmd
ipconfig /all
```

or

```cmd
getmac
```

---

## Example Output

```
2: eth0
link/ether 08:00:27:4b:8d:2a brd ff:ff:ff:ff:ff:ff
```

Here,

```
08:00:27:4b:8d:2a
```

is the MAC address.

---

## Broadcast MAC Address

The broadcast MAC address is:

```
FF:FF:FF:FF:FF:FF
```

It sends data to **all devices** on the local network.

---

## Common Uses

- Ethernet communication
- Wi-Fi communication
- ARP (Address Resolution Protocol)
- Switch forwarding
- Device identification

---

## Security Considerations

Attackers may perform:

- MAC Spoofing
- MAC Flooding

These attacks can bypass simple network restrictions or overload network switches.

---

## Key Points

- MAC stands for **Media Access Control**.
- It is a **48-bit hardware address**.
- It identifies devices on a local network.
- It operates at **OSI Layer 2**.
- It is different from an IP address.
- Switches use MAC addresses to forward Ethernet frames.

---

## References

- IEEE 802 Standards
- Cisco Networking Academy
- CompTIA Network+
