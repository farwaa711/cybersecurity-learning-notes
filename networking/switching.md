# Network Switching

## What is a Network Switch?

A **network switch** is a networking device that connects multiple devices within a **Local Area Network (LAN)**. It forwards data only to the intended device using **MAC addresses**.

Unlike a hub, a switch sends data only to the correct destination, making the network faster and more secure.

---

## How a Switch Works

A switch learns the MAC addresses of connected devices and stores them in a **MAC Address Table (CAM Table)**.

When a frame arrives:

1. The switch reads the **source MAC address**.
2. It stores the MAC address and the port it came from.
3. It checks the **destination MAC address**.
4. If it knows the destination, it forwards the frame only to that port.
5. If it does not know the destination, it floods the frame to all ports except the incoming port.

---

## Example

```
           Switch
      +---------------+
      |               |
 PC A |               | PC B
MAC A |               | MAC B
      |               |
 PC C |               | PC D
MAC C |               | MAC D
      +---------------+
```

If PC A sends data to PC B:

- The switch checks its MAC Address Table.
- If MAC B is known, it sends the frame only to PC B.
- Other devices do not receive the frame.

---

## MAC Address Table

A switch maintains a table similar to this:

| MAC Address | Port |
|-------------|------|
| AA:AA:AA:AA:AA:AA | Fa0/1 |
| BB:BB:BB:BB:BB:BB | Fa0/2 |
| CC:CC:CC:CC:CC:CC | Fa0/3 |

This allows efficient forwarding of Ethernet frames.

---

## Types of Switching

### 1. Store-and-Forward

- Receives the entire frame.
- Checks for errors using CRC.
- Then forwards the frame.
- Most common method.

---

### 2. Cut-Through

- Starts forwarding before receiving the entire frame.
- Very fast.
- May forward corrupted frames.

---

### 3. Fragment-Free

- Reads the first 64 bytes before forwarding.
- Balances speed and reliability.

---

## Switch vs Hub

| Switch | Hub |
|---------|-----|
| Intelligent device | Simple device |
| Uses MAC addresses | Does not use MAC addresses |
| Sends data to one device | Sends data to every device |
| Faster | Slower |
| Reduces collisions | More collisions |

---

## Advantages of a Switch

- Faster communication
- Better network performance
- Reduced collisions
- Improved security
- Efficient bandwidth usage

---

## Disadvantages

- More expensive than hubs
- Requires configuration in larger networks

---

## Security Threats

Common attacks against switches include:

- MAC Flooding
- CAM Table Overflow
- VLAN Hopping
- ARP Spoofing

---

## Prevention

- Port Security
- Disable unused ports
- Dynamic ARP Inspection (DAI)
- VLAN segmentation
- Network monitoring

---

## Key Points

- A switch operates at **OSI Layer 2 (Data Link Layer)**.
- It forwards data using **MAC addresses**.
- It stores MAC addresses in a **MAC Address Table (CAM Table)**.
- Unknown destinations are flooded.
- Known destinations are forwarded to the correct port only.

---

## References

- Cisco Networking Academy
- CompTIA Network+
- IEEE 802.1 Standards
