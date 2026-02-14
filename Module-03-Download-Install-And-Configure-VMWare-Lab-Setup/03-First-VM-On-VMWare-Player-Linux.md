
# First VM on VMware Workstation Player – Linux

## Introduction

In this guide, you will learn how to create and configure your first Linux virtual machine (VM) using VMware Workstation Player.

This lab is ideal for beginners who want hands-on experience with virtualization.

---

## Prerequisites

Before starting, make sure you have:

- VMware Workstation Player installed
- A Linux ISO file (e.g., Ubuntu, Debian, CentOS)
- At least 8 GB RAM recommended on your host machine
- Hardware virtualization enabled in BIOS (Intel VT-x or AMD-V)

---

## Step 1: Download a Linux ISO

1. Go to an official Linux distribution website (example: Ubuntu).
2. Download the latest stable ISO version (64-bit).
3. Save the ISO file locally.

Example file:
ubuntu-22.04-desktop-amd64.iso

---

## Step 2: Create a New Virtual Machine

1. Open VMware Workstation Player.
2. Click Create a New Virtual Machine.
3. Select Installer disc image file (ISO).
4. Click Browse and select your Linux ISO.
5. Click Next.

VMware may automatically detect the Linux distribution.

---

## Step 3: Choose Guest Operating System

If auto-detection does not work:

1. Select Linux.
2. Choose the correct version (e.g., Ubuntu 64-bit).
3. Click Next.

---

## Step 4: Name and Location

1. Enter a name (e.g., Ubuntu-Lab).
2. Choose the location to store the VM files.
3. Click Next.

---

## Step 5: Configure Disk Size

1. Specify disk size (recommended: 20–40 GB).
2. Choose:
   - Store virtual disk as a single file (better performance)
   - Or split into multiple files (easier file movement)
3. Click Next.

---

## Step 6: Customize Hardware (Important)

Click Customize Hardware before finishing.

Recommended settings:

- Memory: 2–4 GB (minimum 2 GB)
- Processors: 2 cores
- Network Adapter: NAT (default)
- CD/DVD: Ensure ISO is connected

Click Close, then Finish.

---

## Step 7: Power On the Virtual Machine

1. Select the VM.
2. Click Play virtual machine.
3. The Linux installer will start.

---

## Step 8: Install Linux

Follow the Linux installation wizard:

- Choose language
- Select keyboard layout
- Configure disk (use entire disk inside VM)
- Create username and password
- Start installation

After installation:
- Reboot the VM
- Remove ISO if prompted

---

## Step 9: Install VMware Tools (Recommended)

VMware Tools improves performance and integration.

To install:

1. In VMware menu, click:
   Player → Manage → Install VMware Tools
2. Inside Linux, mount and install the tools package.
3. Reboot the VM.

Benefits:
- Better display resolution
- Clipboard sharing
- Improved performance

---

## Networking Modes Explained

VMware Player offers three network types:

### NAT (Default)
- VM shares host internet connection
- Easiest setup

### Bridged
- VM gets IP from same network as host
- Appears as separate device on LAN

### Host-Only
- VM communicates only with host
- No internet access

For beginners → use NAT.

---

## Summary

Creating your first Linux virtual machine in VMware Workstation Player is the foundation of learning virtualization. This hands-on practice helps you understand how virtual machines operate and prepares you for more advanced platforms like VMware ESXi and vSphere.
