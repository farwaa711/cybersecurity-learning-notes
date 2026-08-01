# Virtual Private Network (VPN)

## What is a VPN?

A **Virtual Private Network (VPN)** is a technology that creates a **secure and encrypted connection** between your device and a VPN server over the Internet.

A VPN protects your data from being intercepted and helps keep your online activity private.

---

## Why is a VPN Needed?

Without a VPN:

- Your Internet Service Provider (ISP) can see the websites you visit.
- Attackers on public Wi-Fi may intercept your traffic.
- Your real IP address is visible to websites.

A VPN encrypts your traffic and hides your public IP address.

---

## How a VPN Works

1. You connect to a VPN server.
2. A secure encrypted tunnel is established.
3. All your Internet traffic passes through the VPN tunnel.
4. The VPN server forwards your traffic to the destination.
5. Websites see the VPN server's IP address instead of yours.

```
Your Device
      │
      │ Encrypted Tunnel
      ▼
+----------------+
|   VPN Server   |
+----------------+
      │
      ▼
   Internet
      │
      ▼
 Website/Server
```

---

## Benefits of Using a VPN

- Encrypts Internet traffic.
- Protects data on public Wi-Fi.
- Hides your public IP address.
- Improves online privacy.
- Allows secure remote access to company networks.

---

## Types of VPN

### 1. Remote Access VPN

Allows individual users to securely connect to a private network from anywhere.

Example:

- Employees working from home.

---

### 2. Site-to-Site VPN

Connects two or more office networks securely over the Internet.

Example:

- Headquarters connected to branch offices.

---

### 3. SSL VPN

Uses SSL/TLS to provide secure access through a web browser or VPN client.

---

### 4. IPsec VPN

Uses the Internet Protocol Security (IPsec) suite to encrypt and authenticate network traffic.

Commonly used in enterprise environments.

---

## VPN Protocols

| Protocol | Description |
|----------|-------------|
| OpenVPN | Open-source, secure, widely used |
| WireGuard | Modern, fast, lightweight |
| IPsec | Enterprise VPN protocol |
| L2TP/IPsec | Tunnel protocol combined with IPsec |
| SSTP | Microsoft VPN protocol |

---

## Advantages

- Encrypts network traffic.
- Protects sensitive information.
- Improves privacy.
- Enables secure remote work.
- Protects users on public Wi-Fi.

---

## Disadvantages

- May reduce Internet speed.
- Requires trust in the VPN provider.
- Some websites block VPN traffic.
- Free VPNs may log user activity.

---

## VPN and Cybersecurity

VPNs help protect against:

- Packet sniffing
- Man-in-the-Middle (MITM) attacks on unsecured networks
- IP address exposure

However, a VPN **does not**:

- Prevent malware infections.
- Replace antivirus software.
- Replace a firewall.

---

## How to Check Your Public IP

### Linux

```bash
curl ifconfig.me
```

### Windows (PowerShell)

```powershell
curl ifconfig.me
```

Connect to a VPN and run the command again. Your public IP should be different.

---

## Best Practices

- Use trusted VPN providers.
- Enable strong encryption.
- Keep VPN software updated.
- Disconnect when not needed if required by your organization.
- Use Multi-Factor Authentication (MFA) when available.

---

## Key Points

- VPN stands for **Virtual Private Network**.
- A VPN encrypts your Internet connection.
- It hides your public IP address.
- VPNs improve privacy and security.
- Common VPN protocols include OpenVPN, WireGuard, and IPsec.
- VPNs are useful but should be used together with other security measures.

---

## References

- Cisco Networking Academy
- CompTIA Network+
- NIST SP 800-77 – Guide to IPsec VPNs
