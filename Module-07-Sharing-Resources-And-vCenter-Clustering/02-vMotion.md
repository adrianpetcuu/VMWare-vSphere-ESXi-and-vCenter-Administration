# vMotion

## Overview

vMotion is a VMware feature that allows you to migrate a **running virtual machine (VM)** from one ESXi host to another **without shutting it down** and without noticeable downtime.

Users connected to the VM typically do not experience interruption during the migration.

---

## Why vMotion Is Important

vMotion is commonly used for:

- Performing hardware maintenance without stopping VMs
- Load balancing across hosts
- Avoiding downtime during upgrades
- Improving availability in cluster environments

It is a core feature in enterprise VMware deployments.

---

## Requirements for vMotion

To use vMotion, the following are required:

- vCenter Server
- Two or more ESXi hosts
- Hosts in the same cluster (recommended)
- Shared storage (VMFS, NFS, or vSAN)
- Dedicated vMotion network configured
- Compatible CPU between hosts

---

## How vMotion Works (Simplified Process)

1. The VM continues running on the source host.
2. The memory of the VM is copied to the destination host.
3. Any memory changes during the copy process are synchronized.
4. When both hosts are fully synchronized, execution switches to the destination host.
5. The source host releases the VM.

The process typically takes seconds.

---

## Types of vMotion

### 1. Compute vMotion
Moves a VM between hosts while keeping storage the same.

### 2. Storage vMotion
Moves VM disk files to another datastore while the VM is running.

### 3. Enhanced vMotion
Moves both compute and storage at the same time.

---

## What Happens to Network and IP?

- The VM keeps the same IP address.
- MAC address does not change.
- Active sessions (RDP, SSH, web) remain connected.

This works because shared storage and networking remain consistent.

---

## vMotion vs Cold Migration

| vMotion | Cold Migration |
|----------|----------------|
| VM stays powered on | VM must be powered off |
| No downtime | Downtime required |
| Requires shared storage | No shared storage required |
| Used in clusters | Can be used standalone |

---

## Best Practices

- Use a dedicated vMotion network (separate VLAN).
- Ensure sufficient bandwidth (1Gb minimum, 10Gb recommended).
- Keep ESXi hosts on the same CPU family.
- Monitor performance during migration in busy environments.

---

## Summary

vMotion is a live migration technology that allows virtual machines to move between ESXi hosts without downtime. It is essential for maintenance, load balancing, and high availability in modern VMware infrastructures.
