# Day 13 - DNS Lab

## Overview
This lab demonstrates how DNS (Domain Name System) is used to resolve domain names into IP addresses using a Cisco router.

---

## Objective
- Understand how DNS works
- Map a hostname to an IP address
- Allow clients to access devices using names instead of IPs

---

## Topology
PC1, PC2, PC3 → Switch → Router1 (DNS Server)

---

## IP Addressing
- Network: 192.168.1.0/24
- Router1: 192.168.1.1
- Server (PC): 192.168.1.10

---

## DNS Concept
DNS translates human-readable names (like server.local) into IP addresses (like 192.168.1.10).

This allows users to access services using names instead of remembering numerical IP addresses.

---

## Configuration Breakdown

### 1. Enable DNS on Router
The command "ip domain-lookup" enables DNS functionality on the router.

---

### 2. Create Static DNS Record
The command:
ip host server.local 192.168.1.10

Maps the hostname "server.local" to the IP address 192.168.1.10.

---

### 3. DHCP Integration
DHCP is configured to automatically assign:
- IP address
- Default gateway
- DNS server (Router1)

This allows clients to automatically use the router as their DNS server.

---

## How It Works

1. A PC sends a request to resolve "server.local"
2. Router checks its local DNS table
3. Finds matching entry
4. Returns IP address (192.168.1.10)
5. PC sends traffic to that IP

---

## Verification Commands

show hosts
show ip interface brief

---

## Testing

ping server.local

Expected Result:
- Successful ping reply using hostname

---

## Key Concepts

- DNS resolves names to IP addresses
- "ip host" creates static DNS entries
- DHCP can provide DNS server automatically
- Network must be working before DNS works

---

## Conclusion

DNS simplifies network usage by allowing devices to communicate using names instead of IP addresses. This is a fundamental concept used in all modern networks.