# Datastore Cluster

## Overview

A Datastore Cluster is a collection of multiple datastores grouped together and managed as a single unit.

It is part of **Storage DRS (SDRS)** and is used to balance storage space and I/O load automatically across multiple datastores.

Datastore Clusters are managed through vCenter.

---

## Why Use a Datastore Cluster?

Without a Datastore Cluster:

- You must manually choose a datastore for each VM.
- Some datastores may become full.
- I/O load may become unbalanced.

With a Datastore Cluster:

- Storage is treated as a single pool.
- vCenter automatically selects the best datastore.
- Space and performance are balanced.

---

## How It Works

1. Multiple datastores are grouped into one Datastore Cluster.
2. When creating or migrating a VM:
   - vCenter selects the optimal datastore.
3. Storage DRS monitors:
   - Free space
   - I/O latency
4. If imbalance is detected:
   - VMs are moved automatically (Storage vMotion).

---

## Requirements

- vCenter Server
- Multiple shared datastores
- Storage DRS enabled
- Storage vMotion capability

---

## Automation Modes

### Manual Mode
- vCenter provides recommendations.
- Administrator approves storage moves.

### Fully Automated Mode
- Storage DRS automatically migrates VMs.
- No manual intervention required.

---

## Example Architecture

    Datastore Cluster: Storage-Cluster-01
    ├── Datastore01
    ├── Datastore02
    └── Datastore03


All datastores act as a single storage pool.

---

## Benefits

- Automatic space balancing
- Automatic I/O balancing
- Simplified storage management
- Reduced risk of datastore overfill
- Better performance distribution

---

## Datastore Cluster vs Regular Datastore

| Regular Datastore | Datastore Cluster |
|-------------------|-------------------|
| Managed individually | Managed as a group |
| Manual placement | Automatic placement |
| No load balancing | Load balancing available |

---

## Best Practices

- Use similar storage types in the same cluster.
- Avoid mixing SSD and HDD in same datastore cluster.
- Monitor latency thresholds carefully.
- Use automated mode in production environments.

---

## Summary

A Datastore Cluster groups multiple datastores into a single logical storage pool. With Storage DRS enabled, it automatically balances storage space and I/O load, simplifying management and improving performance in VMware environments.
