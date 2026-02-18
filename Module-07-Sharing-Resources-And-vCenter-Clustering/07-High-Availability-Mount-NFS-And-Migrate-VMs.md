
# High Availability – Mount NFS and Migrate VMs

## Overview

To enable High Availability (HA), all ESXi hosts must access the same shared storage.  
This guide explains how to mount an NFS datastore on multiple hosts and migrate virtual machines to shared storage.

---

# Step 1 – Mount NFS Datastore on ESXi Hosts

## Using vCenter

1. Go to **Storage**.
2. Click **New Datastore**.
3. Select **NFS**.
4. Enter:
   - NFS Server IP
   - Folder path (example: /nfs-share)
   - Datastore name
5. Click **Finish**.

Ensure the datastore is visible on all ESXi hosts in the cluster.

---

## Verify Mount

- Go to **Hosts and Clusters**.
- Select each ESXi host.
- Confirm the NFS datastore appears under Storage.

All hosts must see the same datastore for HA to function properly.

---

# Step 2 – Migrate Existing VMs to NFS (Storage Migration)

If VMs are currently on local storage, move them to shared NFS.

## Using vCenter (Storage vMotion)

1. Right-click the VM.
2. Select **Migrate**.
3. Choose:
   Change storage only.
4. Select the NFS datastore.
5. Click **Finish**.

The VM can remain powered on during this process.

---

## If No Storage vMotion (Cold Migration)

1. Power off the VM.
2. Right-click → **Migrate**.
3. Choose:
   Change both compute resource and storage (if needed).
4. Select NFS datastore.
5. Finish migration.

---

# Step 3 – Verify HA Protection

After migration:

1. Select the VM.
2. Go to **Monitor → vSphere HA**.
3. Confirm status is **Protected**.

This means HA can restart the VM on another host if a failure occurs.

---

# Step 4 – Test HA (Lab Only)

To test:

1. Place one ESXi host in maintenance mode or simulate failure.
2. Observe VM restart on another host.

HA will power on the VM automatically using shared NFS storage.

---

# Important Notes

- Shared storage is mandatory for HA.
- Ensure sufficient free space on NFS datastore.
- Use stable network connectivity for storage traffic.
- Keep consistent networking across hosts.

---

# Summary

Mounting NFS storage across ESXi hosts enables shared access to VM files.  
After migrating VMs to shared storage, High Availability can automatically restart them on another host if one fails.
