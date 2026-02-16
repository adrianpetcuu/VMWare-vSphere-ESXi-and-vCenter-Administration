
# Install vCenter Server (Short Guide)

## Overview

vCenter Server is deployed as a virtual appliance (VCSA) on an ESXi host.  
It provides centralized management for ESXi hosts, clusters, and virtual machines.

---

## Prerequisites

- ESXi host installed and reachable
- Static IP for vCenter
- DNS configured (FQDN recommended)
- VCSA ISO downloaded
- Windows PC to run installer

---

# Stage 1 – Deploy Appliance

1. Mount the VCSA ISO.
2. Go to:
   vcsa-ui-installer\win32
3. Run:
   installer.exe
4. Click **Install**.

### Provide:

- ESXi host IP and root credentials
- VM name and appliance root password
- Deployment size (Tiny for lab)
- Datastore
- Static network settings (IP, DNS, gateway)

Wait 10–20 minutes for deployment.

---

# Stage 2 – Configure vCenter

After deployment, click **Continue**.

Configure:

- NTP server
- SSO domain (default: vsphere.local)
- SSO admin password
- Site name

Click **Finish** and wait for completion.

---

## Access vCenter

Open browser:

https://<vcenter-IP-or-FQDN>

Login:

administrator@vsphere.local

---

## Next Steps

- Create Datacenter
- Create Cluster
- Add ESXi hosts
- Enable HA/DRS (optional)

---

## Summary

vCenter installation has two stages: appliance deployment and SSO configuration.  
Once completed, it becomes the central management platform for your VMware environment.
