# High Availability (HA) – Introduction

## Overview

High Availability (HA) is a VMware cluster feature that automatically restarts virtual machines (VMs) if an ESXi host fails.

It is designed to minimize downtime and increase infrastructure resilience.

HA works at the cluster level and requires vCenter.

---

## Why High Availability Is Important

In a single-host environment:

- If the host fails → all VMs go down.
- Manual intervention is required.

In a cluster with HA enabled:

- If one host fails → affected VMs are automatically restarted on another host.
- Downtime is reduced to a few minutes.

HA improves business continuity.

---

## How HA Works (Basic Concept)

1. ESXi hosts in a cluster continuously monitor each other.
2. If a host stops responding, HA detects the failure.
3. vCenter (or HA agents) determine which VMs were affected.
4. VMs are automatically powered on other available hosts in the cluster.

The VM is restarted, not migrated live.

---

## HA vs vMotion

- HA restarts VMs after failure.
- vMotion moves VMs before failure (planned action).

HA handles unplanned outages.

---

## Requirements for HA

- vCenter Server
- At least two ESXi hosts
- Shared storage
- Proper network configuration
- Cluster configuration

---

## What HA Does NOT Do

- It does not prevent a host from failing.
- It does not eliminate downtime completely.
- It does not protect against application-level crashes (unless combined with other tools).

It focuses on infrastructure-level failure recovery.

---

## Summary

High Availability (HA) is a cluster feature that automatically restarts virtual machines on healthy hosts if an ESXi server fails. It is essential for building reliable and resilient VMware production environments.
