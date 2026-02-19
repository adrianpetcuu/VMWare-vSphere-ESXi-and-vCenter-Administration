# Fault Tolerance (FT)

## Overview

Fault Tolerance (FT) is a VMware feature that provides continuous availability for virtual machines.

Unlike HA, which restarts a VM after a host failure, Fault Tolerance keeps a secondary copy of the VM running at the same time.

If the primary host fails, the secondary VM immediately takes over with **zero downtime and no data loss**.

---

## How Fault Tolerance Works

1. A primary VM runs on one ESXi host.
2. A secondary VM runs on another host.
3. Both VMs stay synchronized in real time.
4. If the primary host fails:
   - The secondary VM instantly becomes active.
   - Users experience no interruption.

This is called **lockstep execution**.

---

## Fault Tolerance vs High Availability

| Fault Tolerance (FT) | High Availability (HA) |
|----------------------|-------------------------|
| Zero downtime | Short downtime (restart) |
| No data loss | Possible minimal data loss |
| Secondary VM always running | VM restarted after failure |
| Higher resource usage | Lower resource usage |

FT is designed for mission-critical workloads.

---

## Requirements for Fault Tolerance

- vCenter Server
- Cluster with at least two ESXi hosts
- Shared storage
- vMotion configured
- FT logging network configured
- Compatible CPUs
- VM must meet FT requirements

---

## FT Logging Network

A dedicated FT network is required to:

- Synchronize primary and secondary VMs
- Transfer execution state
- Ensure real-time consistency

High bandwidth and low latency are recommended.

---

## Limitations

- Higher CPU and network overhead
- Limited number of FT-protected VMs per host
- Not suitable for very large multi-vCPU workloads (depending on version)
- Requires careful capacity planning

---

## When to Use Fault Tolerance

Recommended for:

- Domain Controllers
- Critical application servers
- Small but essential services
- Systems requiring zero downtime

Not typically used for large database servers or heavy workloads.

---

## Enabling Fault Tolerance

1. Right-click the VM.
2. Select:
   **Fault Tolerance → Turn On Fault Tolerance**
3. vCenter creates secondary VM automatically.
4. FT synchronization begins.

---

## Best Practices

- Use dedicated FT logging network.
- Monitor resource usage.
- Protect only critical VMs.
- Ensure cluster has sufficient spare capacity.

---

## Summary

Fault Tolerance provides continuous availability by running a synchronized secondary copy of a VM. If a host fails, the secondary VM instantly takes over with zero downtime. It is ideal for critical workloads that cannot tolerate interruptions.
