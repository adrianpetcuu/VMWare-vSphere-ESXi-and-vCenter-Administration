
# Step-by-Step Linux CentOS Installation

## Overview

This guide explains how to install CentOS Linux on a virtual machine in VMware (ESXi or Workstation).

---

## Prerequisites

- CentOS ISO file downloaded
- Virtual machine created
- Minimum:
  - 2 vCPU
  - 2–4 GB RAM
  - 20 GB disk
- ISO attached to VM CD/DVD drive

---

# Step 1 – Boot from ISO

1. Power on the VM.
2. Select:
   Install CentOS Linux
3. Press Enter.

---

# Step 2 – Select Language

- Choose your preferred language.
- Click Continue.

---

# Step 3 – Installation Summary Screen

## 3.1 – Date & Time

- Select your region.
- Enable NTP (recommended).
- Click Done.

## 3.2 – Installation Destination

1. Click Installation Destination.
2. Select the virtual disk.
3. Choose Automatic partitioning.
4. Click Done.

## 3.3 – Network & Hostname

1. Click Network & Hostname.
2. Enable network (turn ON).
3. Set hostname (example: centos01.local).
4. Click Done.

---

# Step 4 – Begin Installation

Click Begin Installation.

Configure:

## Root Password
- Set strong root password.
- Click Done.

## Create User
- Enter full name.
- Set username and password.
- Optional: Make user administrator.
- Click Done.

---

# Step 5 – Complete Installation

After installation finishes:

- Click Reboot.
- Remove ISO from VM.

---

# Step 6 – First Login

Log in using:
- root
or
- created user

Verify system:

cat /etc/centos-release

Check IP:

ip a

Update system:

sudo dnf update -y

---

# Step 7 – Install VMware Tools

sudo dnf install open-vm-tools -y
sudo reboot

---

# Optional – Install GUI

sudo dnf groupinstall "Server with GUI" -y
sudo systemctl set-default graphical.target
sudo reboot

---

# Summary

CentOS installation includes configuring language, disk, network, and user settings. After installation, update the system and install VMware Tools for optimal performance in virtual environments.
