# Day 11 - NAT (Network Address Translation) Lab

## Overview
This lab demonstrates how NAT is used to allow devices inside a private network to access an external network using a single public IP address.

---

## Topology

PCs (Inside Network) → Switch → Router1 (NAT Router) → Router2 (ISP)

---

## IP Addressing

### Inside Network (LAN)
- Network: 192.168.1.0/24
- PC1 → 192.168.1.10
- PC2 → 192.168.1.20
- Router1 G0/0 → 192.168.1.1 (Inside)

---

### Outside Network (WAN / Internet)
- Network: 10.0.0.0/24
- Router1 G0/1 → 10.0.0.1 (Outside)
- Router2 G0/0 → 10.0.0.2

---

## NAT Concept

NAT (Network Address Translation) is used to translate private IP addresses into a public IP address so that internal devices can access external networks.

---

## NAT Configuration Steps

### 1. Define Inside and Outside Interfaces
- G0/0 → Inside (LAN side)
- G0/1 → Outside (Internet side)

### 2. Create Access Control List (ACL)
Used to identify which internal network is allowed to use NAT.

### 3. Enable PAT (Overload)
All internal devices share one public IP (Router1 G0/1).

---

## How NAT Works

1. A PC sends a packet using its private IP (192.168.1.x)
2. Router1 translates it into its public IP (10.0.0.1)
3. Router2 receives the request
4. Reply comes back to Router1
5. Router1 translates it back to the correct internal PC

---

## Verification Commands

show ip nat translations  
show ip nat statistics  
show ip interface brief  

---

## Testing

ping 10.0.0.2  

Expected Result:
- Successful replies from Router2 (ISP side)

---

## Key Concepts Learned

- Inside vs Outside interfaces
- NAT translation process
- PAT (Port Address Translation)
- ACL usage in NAT
- Real-world internet simulation

---

## Conclusion

NAT allows multiple private devices to access external networks using a single public IP address. It is a fundamental concept used in all real-world networking environments.