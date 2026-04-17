# Day 16 - Port Security Lab

## Overview
This lab demonstrates how to secure switch ports using Port Security to prevent unauthorized devices from connecting.

---

## Objective
- Limit number of devices per port
- Learn MAC address security
- Prevent unauthorized access

---

## Topology
PC1, PC2 → Switch → Router

---

## Concept

Port Security allows:
- Limiting MAC addresses per port
- Automatically learning MAC (sticky)
- Taking action if violation happens

---

## Configuration

- Port configured as access
- Port security enabled
- Maximum MAC = 1
- Sticky MAC enabled
- Violation mode = shutdown

---

## Violation Modes

- protect → ignore
- restrict → log
- shutdown → disable port ❌

---

## Testing

- Connect one PC → works
- Connect another → port shutdown

---

## Verification

show port-security
show mac address-table

---

## Key Concepts

- MAC-based security
- Sticky learning
- Violation handling

---

## Conclusion

Port Security helps protect the network by restricting unauthorized devices from connecting to switch ports.