# Day 9 - OSPF Routing Lab

## Overview

This lab demonstrates dynamic routing using OSPF (Open Shortest Path First) between two routers.
Unlike static routing, OSPF allows routers to automatically exchange routing information and build routing tables dynamically.

---

## Network Topology

The topology consists of:

* Two routers connected directly
* Two LAN networks (one on each router)
* Two end devices (PCs)

PC1 —— Router1 —— Router2 —— PC2

---

## IP Addressing

### Router1:

* GigabitEthernet0/0 → 192.168.1.1 /24
* GigabitEthernet0/1 → 10.0.0.1 /24

### Router2:

* GigabitEthernet0/0 → 10.0.0.2 /24
* GigabitEthernet0/1 → 192.168.2.1 /24

### PCs:

* PC1 → 192.168.1.2 /24, Gateway: 192.168.1.1
* PC2 → 192.168.2.2 /24, Gateway: 192.168.2.1

---

## OSPF Configuration

OSPF was configured on both routers using process ID 1 and area 0.

### Router1:

* Advertises:

  * 192.168.1.0/24
  * 10.0.0.0/24

### Router2:

* Advertises:

  * 192.168.2.0/24
  * 10.0.0.0/24

---

## How OSPF Works in This Lab

* Each router advertises its directly connected networks
* Routers exchange routing information using OSPF
* Each router learns about the remote network automatically
* Routing tables are updated dynamically without manual configuration

---

## Verification

The following commands were used to verify OSPF operation:

show ip route
show ip ospf neighbor

Expected result:

* Routes marked with "O" (OSPF)
* Neighbor relationship established between Router1 and Router2

---

## Testing

Connectivity was tested using ping:

ping 192.168.2.2

Successful replies confirm that OSPF routing is working correctly.

---

## Conclusion

This lab demonstrates how OSPF enables automatic routing between networks.
It simplifies network management compared to static routing and is widely used in real-world enterprise networks.

---

## Tools Used

* Cisco Packet Tracer
* Cisco 1941 Routers
