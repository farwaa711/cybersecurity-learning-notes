# IP Addressing Basics

## What is an IP Address?

An IP (Internet Protocol) address is a unique address assigned to a device on a network. It allows devices to communicate with each other.

Example: 192.168.1.10


---

# Types of IP Addresses

## 1. IPv4

IPv4 uses a 32-bit address format.

Example:  192.168.1.1


It contains four numbers separated by dots.

---

## 2. IPv6

IPv6 uses a 128-bit address format and was created because IPv4 addresses are limited.

Example: 2001:0db8:85a3::8a2e:0370:7334


---

# Public vs Private IP

## Public IP

A public IP is visible on the internet and is assigned by your ISP.

Example: 203.0.113.10


## Private IP

A private IP is used inside local networks.

Common private ranges:
10.0.0.0 - 10.255.255.255

172.16.0.0 - 172.31.255.255

192.168.0.0 - 192.168.255.255


---

# Static vs Dynamic IP

## Static IP

An IP address that does not change.

Used for:
- Servers
- Hosting
- Network devices

## Dynamic IP

An IP address assigned automatically by DHCP.

Used by:
- Home devices
- Phones
- Laptops

---

# Cybersecurity Importance

Understanding IP addresses helps security professionals with:

- Network scanning
- Reconnaissance
- Firewall rules
- Incident investigation
- Identifying attackers

---

# Useful Commands

Check IP address:

Linux:

```bash
ip a


Windows:

ipconfig

Test connectivity:

ping google.com




