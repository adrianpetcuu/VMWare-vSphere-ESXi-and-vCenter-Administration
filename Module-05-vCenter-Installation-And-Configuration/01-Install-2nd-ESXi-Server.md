# Install 2nd ESXi Server

## Introduction

Installing a second ESXi server is an important step when building a production or lab cluster. A second host allows you to enable High Availability (HA), load balancing, and improved redundancy.

This guide explains how to install and prepare a second ESXi host.

---

## Why Install a Second ESXi Host?

With only one ESXi host:
- All virtual machines depend on a single physical server.
- If the server fails, all VMs go down.

With two or more ESXi hosts:
- Virtual machines can be moved between hosts.
- HA can restart VMs if one host fails.
- Maintenance can be performed with less downtime.

---

## Prerequisites

Before installing the second ESXi host, ensure:

- Compatible physical hardware
- At least 16 GB RAM recommended
- Local storage (SSD recommended)
- Bootable ESXi ISO
- Same ESXi version as the first host (recommended)
- Network connectivity to the same management network

---

## Step 1: Prepare Bootable Media

1. Download the same ESXi ISO version used on the first host.
2. Create a bootable USB using tools such as Rufus or balenaEtcher.
3. Insert the USB into the second server.

---

## Step 2: Install ESXi

1. Boot from the USB device.
2. Press **Enter** to start installation.
3. Accept the license agreement (F11).
4. Select the target disk for installation.
5. Choose keyboard layout.
6. Set a strong root password.
7. Confirm installation and wait for completion.
8. Reboot the server.

---

## Step 3: Configure Management Network

After reboot:

1. Press **F2** to access DCUI.
2. Log in as root.
3. Go to **Configure Management Network**.
4. Set:
   - Static IP address
   - Subnet mask
   - Default gateway
   - DNS server
   - Hostname (e.g., esxi02.company.local)
5. Restart the management network.

Ensure the second host can communicate with the first host and vCenter.

---

## Step 4: Verify Connectivity

From another machine:

- Access the host via browser:
  https://<ESXi-IP>

- Confirm network connectivity.
- Verify DNS resolution.

---

## Step 5: Add the Second Host to vCenter (If Used)

If using vCenter:

1. Log in to vCenter.
2. Right-click the Datacenter or Cluster.
3. Select **Add Host**.
4. Enter the new ESXi IP and root credentials.
5. Complete the wizard.
6. Assign license if required.

The second host is now part of the cluster.

---

## Best Practices

- Use the same ESXi version on all hosts.
- Configure identical networking (vSwitch, VLANs).
- Ensure shared storage is accessible (if using HA or vMotion).
- Use consistent naming conventions (esxi01, esxi02).

---

## Summary

Installing a second ESXi host improves redundancy and prepares your environment for clustering, High Availability, and workload balancing. It is a foundational step in building a reliable virtual infrastructure.
