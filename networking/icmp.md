# Internet Control Message Protocol (ICMP)

## What is ICMP?

**ICMP (Internet Control Message Protocol)** is a network protocol used by devices to send **error messages**, **status information**, and **diagnostic messages**.

Unlike TCP and UDP, ICMP is **not used to transfer application data**. Instead, it helps devices communicate information about network conditions.

---

## Purpose of ICMP

ICMP is mainly used to:

- Test network connectivity
- Report network errors
- Diagnose network problems
- Measure network performance

---

## How ICMP Works

Suppose Computer A wants to check if Computer B is reachable.

### Step 1

Computer A sends an **ICMP Echo Request**.

```
Ping Request
```

### Step 2

If Computer B is online, it replies with an **ICMP Echo Reply**.

```
Ping Reply
```

If no reply is received, the device may be offline or blocking ICMP traffic.

---

## Common ICMP Message Types

| Type | Description |
|------|-------------|
| Echo Request | Sent by `ping` |
| Echo Reply | Response to `ping` |
| Destination Unreachable | Destination cannot be reached |
| Time Exceeded | TTL reached zero |
| Redirect | Suggests a better route |

---

## ICMP and Ping

The **ping** command uses ICMP to test connectivity.

### Linux

```bash
ping google.com
```

Example output:

```
PING google.com (142.250.190.14)

64 bytes from 142.250.190.14:
icmp_seq=1 ttl=117 time=28 ms
```

This means:

- **64 bytes** → Size of the reply
- **ttl=117** → Time To Live value
- **time=28 ms** → Round-trip time
- **icmp_seq=1** → Packet number

---

## ICMP and Traceroute

The **traceroute** command also uses ICMP (or UDP/TCP, depending on the operating system) to discover the path packets take through the network.

Linux:

```bash
traceroute google.com
```

Windows:

```cmd
tracert google.com
```

Traceroute works by increasing the **TTL (Time To Live)** value one hop at a time.

---

## ICMP and TTL

TTL stands for **Time To Live**.

Every router decreases the TTL by **1**.

When TTL reaches **0**, the router discards the packet and sends an **ICMP Time Exceeded** message back to the sender.

This is how traceroute identifies each router along the path.

---

## Advantages of ICMP

- Helps troubleshoot networks
- Tests connectivity
- Identifies routing issues
- Detects unreachable hosts
- Measures response time

---

## Security Risks

Attackers can misuse ICMP through:

- ICMP Flood (Ping Flood)
- Smurf Attack
- Network Reconnaissance
- Ping Sweeps

These attacks may be used to discover devices or overwhelm a network.

---

## Protection

- Rate-limit ICMP traffic
- Block unnecessary ICMP messages
- Use firewalls
- Monitor unusual ICMP activity

---

## Key Points

- ICMP stands for **Internet Control Message Protocol**.
- It is used for diagnostics and error reporting.
- It does not carry application data.
- `ping` uses ICMP Echo Request and Echo Reply.
- `traceroute` uses TTL and ICMP Time Exceeded messages.
- ICMP helps troubleshoot network connectivity.

---

## References

- RFC 792 – Internet Control Message Protocol
- Cisco Networking Academy
- CompTIA Network+
