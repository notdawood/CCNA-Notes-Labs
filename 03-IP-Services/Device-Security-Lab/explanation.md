# Day 15 - Device Security Basics Lab

## Overview
This lab demonstrates basic security configurations on a Cisco router to protect access and secure management.

---

## Objective
- Secure router access using passwords
- Protect console and remote access
- Encrypt stored passwords
- Display warning banner

---

## Topology
PC → Switch → Router1

---

## IP Addressing
- PC: 192.168.1.10
- Router: 192.168.1.1

---

## Security Features Implemented

### 1. Enable Secret
Used to secure privileged EXEC mode.

---

### 2. Console Security
Password is required to access router via console.

---

### 3. VTY Security
Password required for remote access (Telnet).

---

### 4. Password Encryption
Encrypts all plain text passwords in configuration.

---

### 5. Banner MOTD
Displays warning message before login.

---

## Verification

show running-config

---

## Testing

- Access console → should ask for password
- Telnet to router → should require password

---

## Key Concepts

- enable secret is more secure than enable password
- service password-encryption hides passwords
- console and VTY lines must be secured
- banner provides legal warning

---

## Conclusion
Basic device security is essential to prevent unauthorized access and protect network devices.