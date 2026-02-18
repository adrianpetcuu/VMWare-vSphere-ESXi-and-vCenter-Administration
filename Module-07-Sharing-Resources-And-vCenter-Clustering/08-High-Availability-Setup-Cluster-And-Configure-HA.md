
# High Availability – Setup Cluster and Configure HA

## Overview

High Availability (HA) is configured at the cluster level in vCenter.  
It allows virtual machines to automatically restart on another ESXi host if a host failure occurs.

This guide explains how to create a cluster and enable HA.

---

# Step 1 – Create a Cluster

1. Log in to vCenter:
   https://<vcenter-IP-or-FQDN>

2. Go to **Hosts and Clusters**.

3. Right-click the Datacenter → **New Cluster**.

4. Enter a cluster name (example: Production-Cluster).

5. Enable:
   - vSphere HA
   - (Optional) DRS

6. Click **OK**.

---

# Step 2 – Add ESXi Hosts to the Cluster

1. Right-click the cluster → **Add Host**.
2. Enter ESXi host IP or FQDN.
3. Provide root credentials.
4. Assign license (if required).
5. Click **Finish**.

Repeat for all ESXi hosts.

---

# Step 3 – Configure HA Settings

1. Select the cluster.
2. Go to **Configure → vSphere Availability**.
3. Click **Edit**.

Configure the following:

## Host Monitoring
- Enable host monitoring (recommended).

## Admission Control
- Ensures enough resources are reserved to restart VMs if a host fails.
- Leave default settings for most environments.

## VM Restart Priority
- Set restart order (High, Medium, Low).

## Heartbeat Datastores
- Select shared datastores for HA heartbeat.

Click **Save**.

---

# Step 4 – Verify HA Status

1. Select the cluster.
2. Check **Summary** tab.
3. Confirm:
   - HA is enabled.
   - All hosts show connected status.
   - No configuration warnings.

---

# Requirements for HA

- Minimum 2 ESXi hosts
- Shared storage (NFS, VMFS, vSAN)
- Proper networking configuration
- Sufficient cluster resources

---

# What Happens During Host Failure?

1. Host stops responding.
2. HA detects the failure.
3. Affected VMs are restarted on another host.
4. Downtime is minimized.

---

# Best Practices

- Use at least 3 hosts in production.
- Keep ESXi versions consistent.
- Monitor cluster resource usage.
- Test HA in a controlled lab environment.

---

# Summary

To enable High Availability, create a cluster in vCenter, add ESXi hosts, and enable HA in cluster settings. Once configured, HA automatically restarts virtual machines on healthy hosts if a failure occurs, improving infrastructure resilience.
