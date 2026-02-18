
# Setup NFS from NAS Device for VMware HA

## Overview

Using a NAS device as NFS shared storage is a common and simple way to provide shared storage for ESXi hosts.

This allows:

- Multiple ESXi hosts to access the same datastore
- vMotion support
- High Availability (HA) functionality

---

## Architecture Example

    NAS Device (NFS Share)
    │
    ├── ESXi01
    └── ESXi02


Both ESXi hosts mount the same NFS share.

---

# Step 1 – Configure NFS Share on NAS

The exact steps depend on the vendor (Synology, QNAP, TrueNAS, etc.), but generally:

1. Log in to NAS management interface.
2. Enable **NFS Service**.
3. Create a new shared folder (example: vmware-nfs).
4. Enable NFS permissions for that folder.
5. Allow access from ESXi host IP addresses.
6. Grant:
   - Read/Write access
   - No root squash (if available option)

Note the following:

- NAS IP address
- NFS export path (example: /volume1/vmware-nfs)

---

# Step 2 – Add NFS Datastore in vCenter

1. Log in to vCenter.
2. Go to **Storage**.
3. Click **New Datastore**.
4. Select **NFS**.
5. Enter:
   - Name (example: NFS-Shared-01)
   - NAS IP address
   - Folder path (export path from NAS)
6. Click **Finish**.

The datastore will be mounted to the selected host or cluster.

---

# Step 3 – Verify Datastore on All Hosts

1. Go to **Hosts and Clusters**.
2. Select each ESXi host.
3. Confirm the NFS datastore appears under **Storage**.

All hosts must see the same datastore for HA and vMotion.

---

# Step 4 – Migrate or Create VMs on NFS

- Create new VMs directly on the NFS datastore  
or
- Migrate existing VMs to NFS using Storage vMotion.

After migration, VMs become eligible for HA restart.

---

# Best Practices

- Use a dedicated storage VLAN for NFS traffic.
- Use at least 1Gb network (10Gb recommended for production).
- Use static IP addresses.
- Ensure NAS has RAID protection.
- Monitor datastore capacity regularly.

---

# Limitations

For lab environments:
- NAS NFS is cost-effective and easy to configure.

For production:
- Enterprise storage with redundancy is recommended.
- Consider dual NICs and redundant switches.

---

# Summary

Setting up NFS from a NAS device provides shared storage required for HA and vMotion. Once mounted on all ESXi hosts, virtual machines stored on the NFS datastore can be automatically restarted on another host if a failure occurs.
