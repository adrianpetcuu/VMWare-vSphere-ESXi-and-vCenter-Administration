# VM Export and Import (OVF)

## Overview

OVF (Open Virtualization Format) is a standard format used to export and import virtual machines between environments.

It allows you to:

- Move VMs between ESXi hosts
- Transfer VMs between vCenter environments
- Backup a VM in portable format
- Share appliances across platforms

---

## What Is OVF?

OVF consists of:

- `.ovf` file (configuration file)
- `.vmdk` file(s) (virtual disks)
- `.mf` file (manifest with checksums)

Sometimes it is packaged as a single `.ova` file (Open Virtual Appliance).

- OVF = multiple files  
- OVA = single compressed file

---

# Export VM as OVF (From vCenter)

1. Power off the VM (recommended).
2. Right-click the VM.
3. Select:
   **Export OVF Template**
4. Choose destination folder.
5. Save as:
   - OVF (multiple files)
   - OVA (single file)

The system downloads the VM files to your local machine.

---

# Import VM (Deploy OVF/OVA)

## Method 1 – Using vCenter

1. Right-click Datacenter or Cluster.
2. Select:
   **Deploy OVF Template**
3. Upload OVF or OVA file.
4. Choose:
   - Host/Cluster
   - Datastore
   - Network mapping
5. Finish deployment.

---

## Method 2 – Using ESXi Host Client

1. Log in to:
   https://<ESXi-IP>
2. Click:
   **Create / Register VM**
3. Choose:
   **Deploy a virtual machine from OVF or OVA file**
4. Upload files.
5. Configure resources.
6. Click **Finish**.

---

## When to Use OVF Export/Import

- Migrating between environments
- Sending VM to another site
- Creating portable backups
- Deploying virtual appliances
- Lab replication

---

## OVF vs Clone

| OVF Export | Clone |
|------------|--------|
| Portable format | Stays within same environment |
| Used for transfer | Used for duplication |
| Can move across vCenters | Same vCenter only |
| Requires upload/download | Fast inside cluster |

---

## Best Practices

- Power off VM before export.
- Verify sufficient disk space.
- Use OVA format for easier transfer.
- Verify checksum if transferring across networks.
- Update VMware Tools after import.

---

## Summary

OVF export and import allows administrators to package virtual machines into portable files that can be moved, backed up, or deployed in other environments. It is a flexible and widely used method for VM portability in VMware infrastructures.
