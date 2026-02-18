# Distributed Resource Scheduler (DRS)

## Overview

Distributed Resource Scheduler (DRS) is a VMware cluster feature that automatically balances virtual machine workloads across multiple ESXi hosts.

DRS ensures optimal use of CPU and memory resources within a cluster.

It works together with:

- vMotion
- vCenter
- Shared storage

---

## Why DRS Is Important

Without DRS:

- Some hosts may become overloaded.
- Other hosts may remain underutilized.
- Resource imbalance can affect performance.

With DRS enabled:

- Workloads are automatically distributed.
- VMs are migrated when needed.
- Performance is optimized across the cluster.

---

## How DRS Works

1. DRS continuously monitors CPU and memory usage.
2. It analyzes load imbalance in the cluster.
3. If imbalance is detected:
   - DRS recommends or performs vMotion migrations.
4. VMs are moved to less busy hosts.

This happens automatically when fully automated mode is enabled.

---

## DRS Automation Levels

### Manual
- DRS provides recommendations.
- Administrator must approve migrations.

### Partially Automated
- DRS places VMs automatically at power-on.
- Migration recommendations require manual approval.

### Fully Automated
- DRS automatically balances workloads.
- No manual intervention required.

Fully automated mode is recommended in production.

---

## DRS Requirements

- vCenter Server
- Cluster configuration
- Shared storage
- vMotion network configured
- Compatible ESXi hosts

---

## DRS vs HA

| DRS | HA |
|------|------|
| Balances workloads | Restarts VMs after host failure |
| Prevents overload | Recovers from failure |
| Uses vMotion | Uses VM restart |
| Improves performance | Improves availability |

They serve different but complementary purposes.

---

## Benefits of DRS

- Automatic workload balancing
- Better resource utilization
- Reduced performance bottlenecks
- Less manual intervention
- Improved infrastructure efficiency

---

## Best Practices

- Use fully automated mode.
- Monitor cluster resource usage.
- Avoid extreme overcommitment.
- Ensure proper vMotion network performance.

---

## Summary

DRS is a cluster feature that automatically balances virtual machine workloads across ESXi hosts using vMotion. It improves performance, optimizes resource utilization, and reduces administrative effort in VMware environments.
