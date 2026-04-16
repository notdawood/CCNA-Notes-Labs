# Day 12 - DHCP Lab

## Overview
This lab demonstrates how DHCP is used to automatically assign IP addresses to devices in a LAN using a Cisco router.

---

## Topology
PC1, PC2, PC3 → Switch → Router1 (DHCP Server)

---

## IP Addressing
- Network: 192.168.1.0/24
- Router Gateway: 192.168.1.1

---

## DHCP Concept
DHCP (Dynamic Host Configuration Protocol) automatically assigns:
- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

This removes the need for manual IP configuration on each device.

---

## Configuration Breakdown

### 1. Interface Setup
Router interface g0/0 is configured with:
- IP: 192.168.1.1
- Subnet: 255.255.255.0

---

### 2. Excluded Addresses
These IPs are reserved and NOT given to clients:
- 192.168.1.1 → 192.168.1.10

---

### 3. DHCP Pool
Defines the range of IPs given to clients:
- Network: 192.168.1.0/24
- Default Gateway: 192.168.1.1
- DNS Server: 8.8.8.8

---

## How It Works

1. PC connects to network
2. Sends DHCP request
3. Router responds with available IP
4. PC automatically gets:
   - IP Address
   - Gateway
   - DNS

---

## Verification Commands

show ip dhcp binding
show ip dhcp pool
show ip interface brief

---

## Expected Result
All PCs automatically receive valid IP addresses and can communicate with the router successfully.