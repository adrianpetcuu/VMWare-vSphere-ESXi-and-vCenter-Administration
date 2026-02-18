# High Availability – Linux Installation (Lab Example)

## Overview

This section explains how to install a Linux virtual machine in a cluster where **High Availability (HA)** is enabled.

The goal is to verify that the Linux VM can be automatically restarted on another ESXi host if a failure occurs.

This example assumes:

- vCenter is installed
- A cluster with at least 2 ESXi hosts exists
- HA is enabled
- Shared storage is configured

---

## Step 1 – Create Linux Virtual Machine

1. Log in to vCenter:
   https://<vcenter-IP>

2. Go to:
   Hosts and Clusters

3. Right-click the Cluster → **New Virtual Machine**

4. Choose:
   - Create a new virtual machine

5. Enter:
   - VM name (example: Linux-HA-Test)
   - Select cluster as compute resource

6. Select shared datastore.

7. Assign:
   - 2 vCPUs
   - 2–4 GB RAM
   - 20–40 GB disk

8. Attach Linux ISO file.

Click **Finish**.

---

## Step 2 – Install Linux OS

1. Power on the VM.
2. Open the Console.
3. Follow Linux installation steps:
   - Select language
   - Configure disk
   - Create user
   - Complete installation

4. Reboot after installation.

---

## Step 3 – Install VMware Tools

After OS installation:

- Install open-vm-tools (recommended for Linux)

Example (Ubuntu/Debian):

sudo apt install open-vm-tools

sudo reboot


This improves performance and HA compatibility.

---

## Step 4 – Verify HA Configuration

Ensure:

- Cluster HA is enabled.
- Admission control is configured.
- Both ESXi hosts are connected.
- VM is stored on shared datastore.

Check VM → Monitor → vSphere HA  
Confirm HA protection status is **Protected**.

---

## Step 5 – Test HA (Lab Only)

⚠ Perform only in lab environment.

To simulate host failure:

1. Power off one ESXi host.
2. Wait for HA detection.
3. Observe:

- VM is marked as unavailable.
- HA restarts the VM on the remaining host.

Downtime: typically 1–3 minutes.

---

## What Happens During HA Restart?

- Host failure detected.
- HA agent identifies affected VMs.
- VM is powered on another host.
- Same storage and network are used.
- Same IP address remains.

---

## Important Notes

- HA restarts the VM (not live migration).
- VM must be on shared storage.
- Sufficient cluster resources must be available.
- Always test HA in controlled conditions.

---

## Summary

Installing a Linux VM inside an HA-enabled cluster allows you to test infrastructure resilience. If a host fails, HA automatically restarts the VM on another host, reducing downtime and improving availability.
