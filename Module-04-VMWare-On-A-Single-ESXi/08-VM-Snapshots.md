
# VM Snapshots

## Introduction

A VM Snapshot captures the state of a virtual machine at a specific point in time. It records:

- Virtual disk state
- VM configuration
- Memory state (optional)

Snapshots are commonly used for testing, patching, and temporary rollback scenarios.

---

## How Snapshots Work

When a snapshot is created:

- The original virtual disk becomes read-only.
- A delta disk is created to record all changes.
- The VM continues running using the delta file.

Multiple snapshots can be chained, forming a snapshot tree.

---

## When to Use Snapshots

Snapshots are useful for:

- Testing updates or patches
- Software upgrades
- Configuration changes
- Temporary backup before risky changes

They are not intended for long-term backups.

---

## Create a Snapshot (ESXi)

1. Log in to ESXi Host Client.
2. Select the Virtual Machine.
3. Click **Actions → Snapshots → Take Snapshot**.
4. Enter:
   - Name
   - Description
5. Optionally check:
   - Snapshot the virtual machine’s memory
6. Click **Take Snapshot**.

---

## View Snapshot Tree

1. Select the VM.
2. Go to **Snapshots → Manage Snapshots**.
3. View snapshot hierarchy.
4. Identify parent and child snapshots.

---

## Revert to a Snapshot

1. Open Snapshot Manager.
2. Select desired snapshot.
3. Click **Revert**.

The VM returns to the saved state.

---

## Delete a Snapshot

Deleting a snapshot:

- Merges delta disk with base disk.
- Consolidates disk changes.

Steps:

1. Open Snapshot Manager.
2. Select snapshot.
3. Click **Delete**.

Or choose **Delete All** to consolidate entire chain.

---

## Snapshot Best Practices

- Do not keep snapshots longer than 48–72 hours.
- Avoid multiple snapshot chains in production.
- Monitor datastore space usage.
- Always delete snapshots after testing.
- Do not use snapshots as backup replacement.

---

## Performance Impact

Snapshots may:

- Increase disk I/O latency
- Consume additional storage space
- Slow down performance if chained

Long snapshot chains can significantly impact VM performance.

---

## Common Issues

### Snapshot Consolidation Needed

If delta disks are not properly merged:

- You may see "Consolidation needed" warning.
- Use Consolidate option from Snapshot Manager.

### Datastore Full

Large snapshots can fill datastore space quickly.

---

## Snapshot vs Backup

Snapshot:
- Short-term state capture
- Not independent copy
- Stored on same datastore

Backup:
- Full copy of VM data
- Stored separately
- Used for disaster recovery

---

## Summary

VM Snapshots provide a powerful mechanism to capture a virtual machine’s state before making changes. However, they must be managed carefully to avoid performance degradation and storage issues. Always treat snapshots as temporary safety mechanisms, not long-term backup solutions.
