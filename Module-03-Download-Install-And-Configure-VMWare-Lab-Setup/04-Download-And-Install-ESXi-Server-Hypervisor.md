
# Download and Install VMware ESXi Server Hypervisor

## Introduction

VMware ESXi is a Type 1 (bare-metal) hypervisor that installs directly on physical hardware. It is the core component of VMware vSphere and is widely used in enterprise data centers.

This guide explains how to download and install VMware ESXi.

---

## System Requirements

Before installation, verify the following:

### Hardware Requirements
- 64-bit x86 CPU (Intel VT-x or AMD-V supported)
- Minimum 8 GB RAM (16 GB recommended for lab)
- At least 32 GB local storage (SSD recommended)
- 1 or more supported Network Interface Cards (NIC)
- Hardware listed on VMware Compatibility Guide (recommended)

---

## Step 1: Download VMware ESXi

1. Go to the official VMware website.
2. Log in or create a VMware account.
3. Navigate to Products → vSphere → ESXi.
4. Download the latest ESXi ISO image.
5. Save the .iso file locally.

Example:
VMware-VMvisor-Installer-8.x.x-xxxxxxx.x86_64.iso

---

## Step 2: Create Bootable Media

You need to create a bootable USB drive using the ESXi ISO.

### Option A: Using Rufus (Windows)

1. Insert a USB drive (at least 8 GB).
2. Open Rufus.
3. Select the ESXi ISO file.
4. Choose the USB device.
5. Click Start.

### Option B: Using balenaEtcher (Windows/Linux/macOS)

1. Open balenaEtcher.
2. Select the ISO file.
3. Select the USB drive.
4. Click Flash.

---

## Step 3: Prepare the Server

1. Insert the bootable USB into the physical server.
2. Enter BIOS/UEFI.
3. Enable:
   - Intel VT-x or AMD-V
   - Hardware virtualization
4. Set USB as first boot device.
5. Save and reboot.

---

## Step 4: Install ESXi

After booting from USB:

1. Press Enter to start installation.
2. Accept the license agreement (F11).
3. Select the disk where ESXi will be installed.
4. Choose keyboard layout.
5. Set a strong root password.
6. Press F11 to confirm installation.

Installation usually takes 5–10 minutes.

---

## Step 5: Reboot the Server

1. Remove the USB installer.
2. Press Enter to reboot.
3. ESXi will start automatically.

You will now see the ESXi Direct Console User Interface (DCUI).

---

## Step 6: Configure Management Network

1. Press F2 to log in.
2. Enter root credentials.
3. Go to:
   Configure Management Network
4. Set:
   - Static IP address
   - Subnet mask
   - Default gateway
   - DNS server
5. Restart management network.

---

## Step 7: Access ESXi Web Interface

From another computer:

1. Open a web browser.
2. Enter:
   https://<ESXi-IP-Address>
3. Log in with:
   - Username: root
   - Password: (the one you set)

You now have access to the ESXi Host Client.

---

## Summary

VMware ESXi is a bare-metal hypervisor installed directly on physical hardware. Once installed and configured, it allows you to create and manage virtual machines efficiently in enterprise or lab environments.
