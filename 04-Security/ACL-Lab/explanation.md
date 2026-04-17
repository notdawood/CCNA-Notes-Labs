# Day 10 - Standard ACL Lab (Access Control List)

## Overview
This lab demonstrates how to use a Standard Access Control List (ACL) in Cisco routers to control network traffic and restrict access for a specific host while allowing others.

---

## Objective
- Block a specific PC (PC1) from accessing the server network
- Allow all other devices to communicate normally
- Understand ACL placement and direction (in/out)

---

## Network Topology

PC1 —— SW —— Router1 —— Server (PC3)
        |
       PC2

---

## IP Addressing

### LAN 1 (192.168.10.0/24)
- PC1 → 192.168.10.10
- PC2 → 192.168.10.20
- Gateway → 192.168.10.1

### LAN 2 (192.168.20.0/24)
- Server (PC3) → 192.168.20.10
- Gateway → 192.168.20.1

---

## Router Configuration

Router1:
- G0/0 → 192.168.10.1
- G0/1 → 192.168.20.1

---

## ACL Configuration

access-list 1 deny host 192.168.10.10
access-list 1 permit any

interface g0/1
ip access-group 1 out

---

## Why apply ACL on G0/1 (out)?
Standard ACL filters based on SOURCE IP only, so it is placed CLOSE to the destination network to avoid blocking unnecessary traffic from other networks.

---

## Testing Results

Before ACL:
- PC1 → Server = SUCCESS
- PC2 → Server = SUCCESS

After ACL:
- PC1 → Server = FAILED ❌
- PC2 → Server = SUCCESS ✅

---

## Verification Commands

show access-lists
show ip interface g0/1

Expected:
- ACL counters increase for denied traffic
- ACL is shown applied outbound on interface

---

## Key Concepts

- ACL works top-down
- First match wins
- Implicit deny exists at the end
- Standard ACL filters only source IP
- Placement of ACL is critical

---

## Conclusion

This lab shows how Standard ACL can be used to control network access by blocking specific hosts while allowing others. It is a core concept in network security and CCNA-level networking.