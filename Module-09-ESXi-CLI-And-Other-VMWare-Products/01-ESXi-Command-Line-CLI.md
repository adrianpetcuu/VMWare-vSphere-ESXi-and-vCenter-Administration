
# ESXi Command Line (CLI)

## Overview

The ESXi Command Line Interface (CLI) allows administrators to manage and troubleshoot ESXi hosts using text-based commands.

It is commonly used for:

- Troubleshooting
- Advanced configuration
- Automation
- Network and storage diagnostics

---

## Ways to Access ESXi CLI

### 1. DCUI (Direct Console User Interface)

- Access directly from physical server console.
- Press F2 to log in.
- Used for basic configuration:
  - Management network
  - Restart management agents
  - Enable SSH

---

### 2. ESXi Shell

Local command-line access on the host.

Enable from:

DCUI → Troubleshooting Options → Enable ESXi Shell

---

### 3. SSH (Remote Access)

1. Enable SSH from:
   DCUI → Troubleshooting Options → Enable SSH  
   or  
   Host → Configure → Services → Start SSH

2. Connect from another machine:

ssh root@<ESXi-IP>

Used for remote command-line management.

---

## Common ESXi CLI Commands

### View system version

vmware -v

### List running VMs

esxcli vm process list

### Restart management network

/etc/init.d/networking restart

### Check storage devices

esxcli storage core device list

### Check network interfaces

esxcli network nic list

---

## esxcli Command

`esxcli` is the main ESXi command-line utility.

Used for managing:

- Networking
- Storage
- Virtual machines
- System settings
- Firewall rules

Example:

esxcli network ip interface list

---

## Best Practices

- Use SSH only when needed.
- Disable SSH after troubleshooting.
- Avoid unnecessary changes from CLI in production.
- Document any manual changes.
- Prefer vCenter for standard management tasks.

---

## Summary

The ESXi CLI provides powerful command-line access for troubleshooting and advanced management. It can be accessed via local shell or SSH and uses the `esxcli` tool for most administrative operations.
