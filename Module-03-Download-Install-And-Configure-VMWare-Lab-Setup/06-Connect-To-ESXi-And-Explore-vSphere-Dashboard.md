
# Connect to ESXi and Explore vSphere Dashboard

## Introduction

After installing and configuring VMware ESXi, the next step is connecting to the host and exploring the vSphere (ESXi Host Client) dashboard.

This guide explains how to connect and understand the main interface components.

---

## Step 1: Verify ESXi IP Address

From the ESXi console (DCUI):

- Confirm the configured Management IP address.
- Example:
  192.168.1.50

---

## Step 2: Connect via Web Browser

1. Open a web browser from another computer.
2. Enter:

   https://<ESXi-IP-Address>

   Example:
   https://192.168.1.50

3. Accept the security certificate warning (self-signed certificate).
4. Log in with:
   - Username: root
   - Password: (configured during installation)

You are now connected to the ESXi Host Client.

---

## Overview of the vSphere (ESXi) Dashboard

After login, you will see the main dashboard.

### 1. Host Summary

Displays:

- Host name
- ESXi version
- CPU usage
- Memory usage
- Uptime
- Hardware information

This section provides a quick health overview of the server.

---

### 2. Navigator Panel (Left Menu)

Main sections include:

- Virtual Machines
- Storage
- Networking
- Host
- Monitor
- Manage

This is where you perform administrative tasks.

---

### 3. Virtual Machines Section

Here you can:

- Create a new VM
- Power on/off VMs
- Open console
- Edit VM settings
- Take snapshots

---

### 4. Storage Section

Shows:

- Datastores (VMFS)
- Capacity and free space
- Disk devices
- Storage adapters

You can create and manage datastores here.

---

### 5. Networking Section

Displays:

- vSwitches
- Port Groups
- VMkernel adapters
- Physical NICs

You can configure VLANs and network settings.

---

### 6. Monitor Section

Provides performance and health data:

- CPU and memory graphs
- Network usage
- Hardware sensors
- System logs
- Events

Useful for troubleshooting and performance monitoring.

---

### 7. Manage Section

Used for configuration tasks:

- Licensing
- Services (SSH, ESXi Shell)
- Firewall rules
- Time & NTP settings
- Security and permissions

---

## Basic Tasks to Try

After connecting, try:

- Viewing hardware summary
- Checking datastore capacity
- Reviewing network configuration
- Creating a small test VM

This helps you become familiar with the interface.

---

## Security Note

Since ESXi uses a self-signed certificate by default:

- Browser will show a warning
- It is normal in lab environments
- In production, install a trusted certificate

---

## Summary

Connecting to ESXi through the web interface allows you to manage virtual machines, storage, networking, and host settings. The vSphere dashboard provides a centralized and intuitive way to administer your virtualization environment.
