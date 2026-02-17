
# Monitors in vCenter

## Overview

Monitoring in vCenter allows administrators to track the health, performance, and status of ESXi hosts and virtual machines.

It helps identify performance bottlenecks, resource contention, and potential failures.

---

## What Can Be Monitored?

### 1. CPU
- Usage percentage
- Ready time
- Core utilization

### 2. Memory
- Consumed memory
- Active memory
- Ballooning or swapping

### 3. Storage
- Datastore capacity
- Disk I/O latency
- Read/Write throughput

### 4. Network
- Traffic usage
- Packet loss
- Throughput rates

---

## Where to Access Monitoring

1. Log in to vCenter.
2. Go to:
   Hosts and Clusters
3. Select a Host or VM.
4. Click the **Monitor** tab.

You can view real-time and historical performance graphs.

---

## Alarms and Alerts

vCenter provides built-in alarms for:

- High CPU usage
- Low datastore space
- Host connection loss
- VM power state changes

Custom alarms can also be created.

---

## Best Practices

- Monitor regularly, not only during incidents.
- Investigate consistent high resource usage.
- Set alarms for critical thresholds.
- Review historical performance data before scaling resources.

---

## Summary

Monitoring in vCenter provides visibility into infrastructure performance and health. Proper monitoring ensures stability, proactive issue resolution, and optimal resource utilization.
