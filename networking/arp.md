# Address Resolution Protocol (ARP)

## What is ARP?

**ARP (Address Resolution Protocol)** is a network protocol used to find the **MAC address** of a device when its **IP address** is known.

It works only within a **Local Area Network (LAN)**.

---

## Why is ARP Needed?

Devices communicate using:

- **IP addresses** at Layer 3
- **MAC addresses** at Layer 2

Before sending data on a local network, a device must know the destination device's MAC address.

ARP helps discover that MAC address.

---

## How ARP Works

Suppose:

- Computer A
  - IP: `192.168.1.10`
  - MAC: `AA:AA:AA:AA:AA:AA`

- Computer B
  - IP: `192.168.1.20`
  - MAC: `BB:BB:BB:BB:BB:BB`

### Step 1

Computer A wants to send data to `192.168.1.20`.

It checks its **ARP Cache**.

If the MAC address is not found...

---

### Step 2

Computer A sends an **ARP Request**.

Example:

```
Who has 192.168.1.20?
Tell 192.168.1.10
```

This request is broadcast to every device on the LAN.

Destination MAC:

```
FF:FF:FF:FF:FF:FF
```

---

### Step 3

Computer B recognizes its IP address and replies.

Example:

```
192.168.1.20 is at BB:BB:BB:BB:BB:BB
```

This is called an **ARP Reply**.

---

### Step 4

Computer A stores the MAC address in its **ARP Cache**.

Now it can send Ethernet frames directly to Computer B.

---

## ARP Request vs ARP Reply

| ARP Request | ARP Reply |
|-------------|-----------|
| Broadcast | Unicast |
| Sent to every device | Sent only to the requester |
| Asks for a MAC address | Provides the MAC address |

---

## ARP Cache

The ARP Cache stores recently discovered IP-to-MAC mappings.

This prevents sending an ARP request every time data is transmitted.

---

## View ARP Cache

### Linux

```bash
arp -a
```

or

```bash
ip neigh
```

### Windows

```cmd
arp -a
```

---

## Example Output

```
192.168.1.1
MAC: 84:16:F9:AB:CD:12

192.168.1.20
MAC: BB:BB:BB:BB:BB:BB
```

---

## Advantages

- Automatically discovers MAC addresses.
- Enables communication within a LAN.
- Reduces manual configuration.

---

## Security Risks

### ARP Spoofing (ARP Poisoning)

An attacker sends fake ARP replies so that devices associate the attacker's MAC address with another device's IP address.

This can lead to:

- Man-in-the-Middle (MITM) attacks
- Data interception
- Session hijacking
- Traffic manipulation

---

## Prevention

- Static ARP entries
- Dynamic ARP Inspection (DAI)
- Switch security features
- Secure network monitoring

---

## Key Points

- ARP stands for **Address Resolution Protocol**.
- ARP maps **IP addresses** to **MAC addresses**.
- It works only on a **Local Area Network (LAN)**.
- ARP Request is **Broadcast**.
- ARP Reply is **Unicast**.
- Devices store mappings in an **ARP Cache**.

---

## References

- RFC 826 – Address Resolution Protocol
- Cisco Networking Academy
- CompTIA Network+
