# Network Ports

## What is a Port?

A port is a logical communication endpoint on a device. While an IP address identifies a device on a network, a **port identifies a specific service or application** running on that device.

Think of it like this:

- **IP Address = House Address**
- **Port = Room Number**

Example:

```
192.168.1.10:80
```

- `192.168.1.10` → Device
- `80` → Web server (HTTP)

---

# Port Number Range

Ports range from:

```
0 - 65535
```

They are divided into three categories:

## 1. Well-Known Ports (0–1023)

Used by common services.

Examples:

| Port | Protocol | Service |
|------|----------|---------|
| 20 | TCP | FTP (Data) |
| 21 | TCP | FTP (Control) |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 143 | TCP | IMAP |
| 443 | TCP | HTTPS |

---

## 2. Registered Ports (1024–49151)

Used by applications and software.

Examples:

| Port | Service |
|------|---------|
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 6379 | Redis |
| 8080 | Alternative HTTP |

---

## 3. Dynamic / Private Ports (49152–65535)

Used temporarily by client devices for outgoing connections.

---

# Open vs Closed Ports

## Open Port

An application is listening and accepting connections.

Example:

```
22/tcp open ssh
```

## Closed Port

No application is listening.

---

# Why Ports Matter

Ports allow multiple services to run on the same IP address.

For example:

- Port 22 → SSH
- Port 80 → HTTP
- Port 443 → HTTPS

A single server can provide all of these services at once.

---

# TCP and UDP Ports

## TCP

- Connection-oriented
- Reliable
- Used for:
  - HTTP
  - HTTPS
  - SSH
  - FTP

## UDP

- Connectionless
- Faster
- Used for:
  - DNS
  - DHCP
  - Streaming
  - Online gaming

---

# Common Commands

## View listening ports (Linux)

```bash
ss -tuln
```

or

```bash
netstat -tuln
```

---

## Scan ports with Nmap

```bash
nmap 192.168.1.1
```

Scan a specific port:

```bash
nmap -p 80 192.168.1.1
```

Scan multiple ports:

```bash
nmap -p 22,80,443 192.168.1.1
```

---

# Ports in Cybersecurity

Attackers and penetration testers often scan ports to discover:

- Running services
- Operating systems
- Potential vulnerabilities
- Misconfigured servers

Open ports may expose services that can be exploited if they are outdated or improperly configured.

---

# Best Practices

- Close unused ports.
- Keep services updated.
- Use firewalls to restrict access.
- Monitor unexpected open ports.
- Disable insecure services like Telnet when possible.

---

# Summary

- A port identifies a service running on a device.
- Port numbers range from 0 to 65535.
- Well-known ports are used by common services.
- Open ports can reveal attack surfaces.
- Port scanning is an essential skill in penetration testing.
