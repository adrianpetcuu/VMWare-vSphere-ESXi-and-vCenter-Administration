
# High Availability – Setup NFS

## Overview

For High Availability (HA) to work properly, ESXi hosts must access shared storage.  
One common shared storage option in labs and small environments is NFS (Network File System).

NFS allows multiple ESXi hosts to access the same datastore over the network.

---

## Why NFS Is Required for HA

HA requires shared storage because:

- VM files must be accessible from all hosts.
- If one host fails, another host must access the same VM files.
- Without shared storage, HA cannot restart VMs on another host.

---

## Architecture Example

NFS Server (Linux / NAS)
        │
        ├── ESXi01
        └── ESXi02

Both ESXi hosts mount the same NFS datastore.

---

# Step 1 – Configure NFS Server (Linux Example)

### Install NFS packages

Ubuntu/Debian:

sudo apt install nfs-kernel-server

---

### Create shared folder

sudo mkdir /nfs-share
sudo chmod 777 /nfs-share

---

### Edit exports file

sudo nano /etc/exports

Add:

/nfs-share *(rw,sync,no_subtree_check,no_root_squash)

---

### Restart NFS service

sudo systemctl restart nfs-kernel-server

---

# Step 2 – Add NFS Datastore to ESXi

On vCenter:

1. Go to Storage
2. Click New Datastore
3. Choose NFS
4. Enter:
   - NFS server IP
   - Folder path (example: /nfs-share)
   - Datastore name
5. Click Finish

Repeat for all ESXi hosts (or add via cluster).

---

# Step 3 – Verify Shared Access

- Confirm datastore appears on all ESXi hosts.
- Upload or create a test VM.
- Ensure VM is visible from all hosts.

---

# Step 4 – Enable HA in Cluster

1. Right-click Cluster → Settings
2. Enable vSphere HA
3. Configure:
   - Host monitoring
   - Admission control
   - VM restart priority
4. Click Save

---

# Important Considerations

- Use dedicated storage network if possible.
- Ensure NFS server has sufficient performance.
- Use static IP addresses.
- Configure proper firewall rules.
- Avoid using NFS on unstable networks.

---

# Summary

Setting up NFS provides shared storage required for High Availability.  
Once both ESXi hosts access the same NFS datastore, HA can restart virtual machines on another host if one fails.
