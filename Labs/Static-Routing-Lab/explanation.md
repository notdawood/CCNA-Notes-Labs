# Day 8 - Static Routing Project Explanation

## Overview
This project demonstrates communication between two different networks using static routing between two Cisco 1941 routers.

---

## Network Topology

- Two routers connected to each other using a direct link.
- Each router is connected to a separate LAN network.

### Networks:
- Network 1: 192.168.1.0/24
- Network 2: 192.168.2.0/24
- Inter-router network: 10.0.0.0/24

---

## IP Addressing

### Router1:
- GigabitEthernet0/0 → 192.168.1.1
- GigabitEthernet0/1 → 10.0.0.1

### Router2:
- GigabitEthernet0/0 → 10.0.0.2
- GigabitEthernet0/1 → 192.168.2.1

---

## Routing Configuration

Static routes were configured on both routers to enable communication between the two networks.

### Router1:
- Route added to reach Network 192.168.2.0 via next hop 10.0.0.2

### Router2:
- Route added to reach Network 192.168.1.0 via next hop 10.0.0.1

---

## Testing and Verification

- Ping tests were performed between devices in both networks.
- Successful replies confirm that routing is working correctly.

Example:
- Ping from PC in Network 1 to PC in Network 2
- Ping between routers over the 10.0.0.0 network

---

## Conclusion

Static routing successfully enabled communication between two different networks.  
This project demonstrates basic inter-network connectivity and routing concepts using Cisco routers.

---

## Tools Used

- Cisco Packet Tracer
- Cisco 1941 Routers