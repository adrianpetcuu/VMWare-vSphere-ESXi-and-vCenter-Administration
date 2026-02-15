
# First VM on ESXi

## Introduction

This guide explains how to create your first Virtual Machine (VM) directly on a VMware ESXi host using the ESXi Host Client.

This is the foundation for working with enterprise virtualization environments.

---

## Prerequisites

Before creating a VM, make sure:

- ESXi is installed and configured
- You can access the ESXi web interface
- A datastore is available
- You have an ISO file (Windows or Linux) uploaded to the datastore

---

## Step 1: Log in to ESXi Host Client

1. Open a web browser.
2. Navigate to:

   https://<ESXi-IP-Address>

3. Log in with:
   - Username: root
   - Password: your configured password

---

## Step 2: Upload ISO File

1. Go to **Storage**.
2. Select your datastore.
3. Click **Datastore Browser**.
4. Click **Upload**.
5. Select your ISO file (e.g., Ubuntu or Windows ISO).

Wait until upload completes.

---

## Step 3: Create New Virtual Machine

1. Click **Virtual Machines**.
2. Click **Create / Register VM**.
3. Select **Create a new virtual machine**.
4. Click **Next**.

---

## Step 4: Name and Compatibility

1. Enter VM name (e.g., Linux-VM01).
2. Select compatibility version (default recommended).
3. Choose Guest OS Family:
   - Linux
   - Windows
4. Select Guest OS Version.
5. Click **Next**.

---

## Step 5: Select Storage

1. Choose the datastore.
2. Click **Next**.

---

## Step 6: Customize Hardware

Configure:

- CPU (2 vCPUs recommended for lab)
- Memory (2–4 GB minimum)
- Hard Disk (20–40 GB recommended)
- Network Adapter (VM Network)
- CD/DVD Drive:
  - Select Datastore ISO file
  - Choose the uploaded ISO
  - Check "Connect at power on"

Click **Next**, then **Finish**.

---

## Step 7: Power On the VM

1. Select the newly created VM.
2. Click **Power On**.
3. Click **Console** to open the VM screen.

The OS installer will start.

---

## Step 8: Install Operating System

Follow the installation wizard inside the VM:

- Choose language
- Configure disk (use entire disk inside VM)
- Create user account
- Complete installation

After installation:

- Reboot the VM
- Disconnect ISO file if needed

---

## Step 9: Install VMware Tools

For better performance:

1. Power off the VM.
2. Edit settings.
3. Attach VMware Tools ISO (if required).
4. Install tools inside the OS.
5. Reboot.

Benefits:

- Improved display
- Better drivers
- Time synchronization
- Better performance

---

## Basic VM Operations

You can now:

- Start / Stop / Restart VM
- Edit CPU and RAM
- Take snapshots
- Monitor performance
- Clone (if managed via vCenter)

---

## What You Learned

After completing this lab, you now understand:

- How to create a VM in ESXi
- How to allocate compute resources
- How to attach ISO files
- How virtualization abstracts physical hardware
- Basic VM lifecycle management

---

## Summary

Creating your first VM on ESXi is the first real step into enterprise virtualization. This process demonstrates how physical resources are transformed into virtual infrastructure capable of running multiple operating systems efficiently and securely.
