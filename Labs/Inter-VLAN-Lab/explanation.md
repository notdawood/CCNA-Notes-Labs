# Inter-VLAN Routing Lab

## Objective

The goal of this lab is to enable communication between different VLANs using a router.

---

## Network Topology

* PC1 in VLAN 10
* PC2 in VLAN 20
* Both connected to a switch
* Switch connected to a router

---

## Configuration Steps

### 1. Create VLANs on Switch

* VLAN 10 (HR)
* VLAN 20 (IT)

### 2. Assign Ports

* Fa0/1 → VLAN 10
* Fa0/2 → VLAN 20

### 3. Configure Trunk Port

* Fa0/24 set to trunk mode

### 4. Configure Router (Router-on-a-Stick)

* Created subinterfaces:

  * Fa0/0.10 for VLAN 10
  * Fa0/0.20 for VLAN 20
* Assigned IP addresses to each

---

## Result

* Devices in different VLANs can now communicate
* Ping between PC1 and PC2 is successful

---

## Key Notes

* Router is required for inter-VLAN communication
* Trunk ports carry multiple VLANs
* Each VLAN has its own subnet

---

## Tools Used

This lab was implemented using Cisco Packet Tracer.
