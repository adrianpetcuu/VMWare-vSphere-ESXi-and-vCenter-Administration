
# Install Linux Operating System (Inside a Virtual Machine)

## Introduction

This guide explains how to install a Linux operating system inside a virtual machine (VM) using VMware ESXi or VMware Workstation.

The process is similar for most Linux distributions such as Ubuntu, Debian, or CentOS.

---

## Prerequisites

Before starting, ensure you have:

- A created Virtual Machine
- Linux ISO file uploaded (ESXi) or selected (Workstation)
- Minimum 2 GB RAM assigned to the VM (4 GB recommended)
- At least 20 GB virtual disk space

---

## Step 1: Attach the ISO File

If using ESXi:

1. Edit VM settings.
2. Go to CD/DVD Drive.
3. Select Datastore ISO file.
4. Choose the Linux ISO.
5. Check "Connect at power on".

If using Workstation:

1. Open VM settings.
2. Select CD/DVD.
3. Choose "Use ISO image file".
4. Select the Linux ISO.

---

## Step 2: Power On the Virtual Machine

1. Click Power On.
2. Open the Console.
3. The Linux installer will boot automatically.

---

## Step 3: Start Installation

Most Linux distributions show options like:

- Try Linux
- Install Linux

Select **Install Linux**.

---

## Step 4: Select Language and Keyboard

1. Choose your preferred language.
2. Select keyboard layout.
3. Click Continue.

---

## Step 5: Installation Type

Choose:

- Normal installation (recommended for beginners)
- Minimal installation (optional)

When prompted about disk configuration:

Select:
- Erase disk and install Linux

⚠ This affects only the virtual disk, not your physical computer.

---

## Step 6: Time Zone

1. Select your region.
2. Confirm time zone.
3. Click Continue.

---

## Step 7: Create User Account

Enter:

- Your name
- Computer name
- Username
- Password

Choose whether to log in automatically or require password.

---

## Step 8: Installation Process

The installer will:

- Format the virtual disk
- Copy system files
- Install bootloader
- Configure system settings

This process may take 5–15 minutes.

---

## Step 9: Reboot the Virtual Machine

After installation:

1. Click Restart Now.
2. Remove the ISO if prompted.
3. Press Enter to continue boot.

Linux will now boot from the virtual hard disk.

---

## Step 10: Install VMware Tools (Recommended)

Installing VMware Tools improves:

- Display resolution
- Performance
- Clipboard sharing
- Time synchronization

To install:

1. Mount VMware Tools ISO from the hypervisor menu.
2. Install required packages inside Linux.
3. Reboot the VM.

---

## Basic Post-Installation Tasks

After login:

- Update the system:

  sudo apt update && sudo apt upgrade

- Configure network (if needed)
- Install additional software

---

## What You Learned

You now understand:

- How to install Linux inside a virtual machine
- How disk partitioning works in a VM
- Basic OS configuration steps
- Post-installation best practices

---

## Summary

Installing Linux inside a virtual machine is a safe and practical way to learn operating systems and virtualization. It allows testing, experimentation, and lab environments without affecting physical hardware.
