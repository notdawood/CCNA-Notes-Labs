# Day 14 - SSH & Telnet Lab

## Overview
This lab demonstrates how to configure remote access to a Cisco router using SSH and Telnet.

---

## Objective
- Enable secure remote access (SSH)
- Understand Telnet vs SSH
- Configure authentication using local user database

---

## Topology
PC → Switch → Router1

---

## IP Addressing
- Network: 192.168.1.0/24
- Router: 192.168.1.1

---

## SSH vs Telnet

Telnet:
- Not secure
- Sends data in plain text

SSH:
- Secure
- Encrypts data

---

## Configuration Steps

1. Configure router interface
2. Set domain name
3. Create user account
4. Generate RSA keys
5. Enable SSH
6. Configure VTY lines

---

## Verification
- show ip ssh
- show running-config

---

## Testing

ssh -l admin 192.168.1.1
telnet 192.168.1.1

---

## Result
User can remotely access the router using SSH securely.

---

## Key Concepts
- SSH requires domain name and RSA keys
- Telnet is insecure
- login local uses local username/password

---

## Conclusion
SSH provides secure remote management of network devices and is widely used in real-world networking.