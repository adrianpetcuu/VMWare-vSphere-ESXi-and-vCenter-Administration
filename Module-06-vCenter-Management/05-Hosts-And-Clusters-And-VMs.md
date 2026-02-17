
# Hosts & Clusters and Virtual Machines

## Overview

The **Hosts & Clusters** view in vCenter is the primary area used to manage ESXi hosts, clusters, and virtual machines.  
It provides a hierarchical structure for organizing and operating your virtual infrastructure.

---

# Hosts & Clusters

This section displays:

- vCenter Server
- Datacenters
- Clusters
- ESXi Hosts
- Virtual Machines

It represents the compute structure of your environment.

---

## Clusters

A Cluster groups multiple ESXi hosts together.

Benefits:

- High Availability (HA)
- Distributed Resource Scheduler (DRS)
- vMotion support
- Resource pooling

Clusters allow workloads to be balanced and protected automatically.

---

## ESXi Hosts

Each host provides:

- CPU resources
- Memory resources
- Local and shared storage access
- Network connectivity

From the host level, you can:

- Enter Maintenance Mode
- Configure networking and storage
- Monitor performance
- Apply updates

---

# Virtual Machines (VMs)

Virtual Machines run inside ESXi hosts.

Each VM has:

- vCPU
- Memory (RAM)
- Virtual Disk (VMDK)
- Network Adapter

VMs can be:

- Powered on/off
- Snapshotted
- Cloned
- Migrated between hosts (vMotion)

---

## Managing VMs from This View

From Hosts & Clusters, you can:

- Create new VMs
- Move VMs between hosts
- Monitor performance
- Modify CPU and memory
- Enter maintenance mode safely

This view focuses on compute and workload placement.

---

## Best Practices

- Use clusters for production environments.
- Keep ESXi versions consistent across cluster.
- Monitor resource utilization regularly.
- Avoid overcommitting CPU and memory excessively.
- Organize VMs logically within folders.

---

## Summary

The Hosts & Clusters section is the core compute management area in vCenter.  
It allows administrators to manage ESXi hosts, organize clusters, and control virtual machines from a single centralized interface.
