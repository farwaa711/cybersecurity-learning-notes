# Domain Name System (DNS)

## What is DNS?

The Domain Name System (DNS) is often called the **phonebook of the Internet**. It translates human-readable domain names (like `google.com`) into IP addresses (like `142.250.190.78`) so computers can communicate with each other.

Without DNS, users would have to remember IP addresses instead of website names.

---

# Why Do We Need DNS?

Humans remember names more easily than numbers.

For example:

- Easy to remember: `google.com`
- Hard to remember: `142.250.190.78`

DNS automatically finds the correct IP address when you enter a domain name into your browser.

---

# How DNS Works

When you type `www.google.com` into your browser:

1. Your browser checks its local DNS cache.
2. If not found, it asks the operating system.
3. The operating system asks the configured DNS resolver.
4. The resolver contacts DNS servers to find the correct IP address.
5. The IP address is returned.
6. Your browser connects to the web server using that IP address.

---

# DNS Lookup Flow

```
User
  ↓
Browser Cache
  ↓
Operating System Cache
  ↓
DNS Resolver
  ↓
Root DNS Server
  ↓
TLD Server (.com)
  ↓
Authoritative DNS Server
  ↓
Returns IP Address
```

---

# Common DNS Record Types

## A Record

Maps a domain name to an IPv4 address.

Example:

```
google.com → 142.250.190.78
```

---

## AAAA Record

Maps a domain name to an IPv6 address.

Example:

```
google.com → 2404:6800:4009:80b::200e
```

---

## CNAME Record

Creates an alias for another domain.

Example:

```
blog.example.com → example.com
```

---

## MX Record

Specifies which mail server receives emails.

Example:

```
example.com → mail.example.com
```

---

## NS Record

Identifies the authoritative name servers for a domain.

Example:

```
ns1.example.com
ns2.example.com
```

---

## TXT Record

Stores text information.

Common uses:

- Domain verification
- SPF
- DKIM
- DMARC

---

# Forward DNS Lookup

Converts:

```
Domain Name → IP Address
```

Example:

```
google.com → 142.250.190.78
```

---

# Reverse DNS Lookup

Converts:

```
IP Address → Domain Name
```

Used during investigations and email security.

---

# Common DNS Commands

## Linux

Check DNS records:

```bash
dig google.com
```

Check specific record:

```bash
dig google.com MX
```

Query another DNS server:

```bash
dig @8.8.8.8 google.com
```

---

## Windows

```cmd
nslookup google.com
```

---

# DNS Cache

Operating systems and browsers temporarily store DNS results to improve speed.

Benefits:

- Faster browsing
- Reduced DNS traffic

---

# DNS Security Risks

## DNS Spoofing

Attackers provide fake DNS responses to redirect users to malicious websites.

---

## DNS Cache Poisoning

Attackers inject false DNS information into a DNS cache.

Result:

Users are redirected to fake websites.

---

## DNS Amplification Attack

A Distributed Denial-of-Service (DDoS) attack where attackers abuse DNS servers to generate large amounts of traffic toward a victim.

---

# DNSSEC

DNS Security Extensions (DNSSEC) add cryptographic signatures to DNS records.

Benefits:

- Protects against DNS spoofing
- Verifies DNS responses
- Improves trust in DNS data

---

# Why DNS Matters in Cybersecurity

Understanding DNS helps security professionals:

- Perform reconnaissance
- Investigate malicious domains
- Detect phishing attacks
- Analyze malware communication
- Secure DNS infrastructure

---

# Summary

- DNS translates domain names into IP addresses.
- A records store IPv4 addresses.
- AAAA records store IPv6 addresses.
- MX records identify mail servers.
- CNAME creates aliases.
- DNSSEC helps protect DNS from tampering.
