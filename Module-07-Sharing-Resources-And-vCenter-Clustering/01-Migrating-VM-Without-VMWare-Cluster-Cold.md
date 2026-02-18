# Migrating a VM Without VMware Cluster (Cold Migration)

## Overview

Cold migration means moving a virtual machine from one ESXi host to another **while it is powered off**.

This method does not require:
- Cluster
- vMotion
- Shared storage
- HA or DRS

It is commonly used in lab environments or small setups.

---

## When to Use Cold Migration

- No shared storage available
- No vMotion license
- Moving VM between standalone hosts
- Hardware maintenance
- Storage migration between local datastores

---

## Important Requirement

The VM **must be powered off** before migration.

---

# Method 1 – Cold Migration Using vCenter

If both hosts are added to vCenter:

1. Power off the VM.
2. Right-click the VM.
3. Select:
   **Migrate**
4. Choose:
   - Change compute resource
   - Or Change both compute resource and storage
5. Select destination host.
6. Select datastore (if needed).
7. Click **Finish**.

The VM files are copied to the new host.

---

# Method 2 – Manual Migration (No vCenter)

If using standalone ESXi hosts:

### Step 1 – Power Off the VM

Make sure the VM is completely powered off.

---

### Step 2 – Download VM Files

1. Open ESXi Host Client.
2. Go to **Storage → Datastore Browser**.
3. Locate the VM folder.
4. Download all VM files:
   - .vmx
   - .vmdk
   - .nvram
   - etc.

---

### Step 3 – Upload to New Host

1. Log in to destination ESXi.
2. Open **Datastore Browser**.
3. Create a new folder.
4. Upload all VM files.

---

### Step 4 – Register the VM

1. Right-click the uploaded `.vmx` file.
2. Select:
   **Register VM**
3. Power on the VM.

---

## What Happens During Cold Migration?

- VM is completely offline.
- Disk files are moved or copied.
- No data corruption risk.
- No downtime-sensitive operations.

---

## Cold Migration vs vMotion

| Cold Migration | vMotion |
|---------------|----------|
| VM powered off | VM stays powered on |
| No shared storage required | Shared storage required |
| No cluster required | Cluster usually required |
| Causes downtime | No downtime |

---

## Best Practices

- Verify network configuration on destination host.
- Confirm datastore compatibility.
- Ensure sufficient storage space.
- Keep ESXi versions compatible.
- Always verify VM boots successfully after migration.

---

## Summary

Cold migration is the simplest method to move a virtual machine between ESXi hosts. It requires powering off the VM and copying its files to the new host. It is ideal for small environments or scenarios without shared storage or clustering.
