# VMware Cluster

## Overview

A VMware Cluster is a group of multiple ESXi hosts combined and managed together through vCenter.

Instead of managing each host separately, a cluster allows you to pool CPU, memory, storage, and networking resources into a single logical unit.

Clusters are required to use advanced features like:

- High Availability (HA)
- Distributed Resource Scheduler (DRS)
- vMotion
- Fault Tolerance (FT)

---

## Why Use a Cluster?

Without a cluster:

- Each ESXi host works independently.
- No automatic VM restart if a host fails.
- No automatic workload balancing.

With a cluster:

- Resources are shared.
- VMs can move between hosts.
- Failures are handled automatically (if HA is enabled).

---

## Basic Cluster Architecture

Example:

    Datacenter
    └── Cluster-Production
        ├── ESXi01
        ├── ESXi02
        └── ESXi03


All hosts inside the cluster:

- Share storage
- Share networking
- Are managed centrally

---

## Key Cluster Features

### 1. High Availability (HA)

If one ESXi host fails:

- HA detects the failure.
- VMs are automatically restarted on another host.
- Downtime is minimized.

---

### 2. Distributed Resource Scheduler (DRS)

DRS automatically balances workloads across hosts.

If one host becomes overloaded:

- VMs are migrated using vMotion.
- Resource usage is balanced.

---

### 3. Resource Pooling

CPU and memory from all hosts are treated as one large pool.

Example:

3 hosts × 64GB RAM  
→ 192GB total available in cluster.

---

## Requirements for a Cluster

- vCenter Server
- At least two ESXi hosts
- Shared storage (for HA and vMotion)
- Consistent networking configuration
- Compatible CPU family

---

## What Happens If a Host Fails?

If HA is enabled:

- Failed host is detected.
- Affected VMs are restarted on other hosts.
- Infrastructure continues running.

Without HA:

- VMs on failed host remain offline.

---

## Cluster vs Single Host

| Single Host | Cluster |
|-------------|----------|
| No redundancy | Redundancy available |
| No HA | HA supported |
| No automatic balancing | DRS supported |
| Limited scalability | High scalability |

---

## Best Practices

- Use minimum 3 hosts for production.
- Enable HA for protection.
- Enable DRS for workload balancing.
- Keep ESXi versions consistent.
- Monitor resource usage regularly.

---

## Summary

A VMware Cluster groups multiple ESXi hosts into a single resource pool. It enables high availability, automatic workload balancing, and scalability. Clusters are the foundation of resilient and enterprise-grade VMware environments.
