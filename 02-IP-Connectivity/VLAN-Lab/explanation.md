# VLAN Lab

## Objective

The goal of this lab is to create multiple VLANs on a switch and assign devices to different VLANs.

---

## Network Topology

* PC1 is connected to FastEthernet0/1
* PC2 is connected to FastEthernet0/2
* Both devices are connected to the same switch

---

## Configuration Steps

### 1. Create VLANs

* VLAN 10 for HR department
* VLAN 20 for IT department

### 2. Assign Ports to VLANs

* FastEthernet0/1 → VLAN 10
* FastEthernet0/2 → VLAN 20

---

## Commands Used

```
enable
configure terminal

vlan 10
name HR

vlan 20
name IT

interface fa0/1
switchport mode access
switchport access vlan 10

interface fa0/2
switchport mode access
switchport access vlan 20
```

---

## Result

* PC1 and PC2 are in different VLANs
* Devices in different VLANs cannot communicate directly

---

## Key Notes

* VLANs improve network segmentation and security
* Each VLAN acts as a separate broadcast domain
* Inter-VLAN communication requires a router or Layer 3 switch

---

## Tools Used

This lab was implemented using Cisco Packet Tracer.
