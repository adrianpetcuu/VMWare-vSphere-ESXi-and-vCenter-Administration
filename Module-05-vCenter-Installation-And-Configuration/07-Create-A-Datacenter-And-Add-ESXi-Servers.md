
# Create a Datacenter and Add ESXi Servers

## Overview

After installing vCenter, the next step is to create a Datacenter object and add ESXi hosts to it.  
The Datacenter is a logical container used to organize hosts, clusters, networking, and storage.

---

## Step 1 – Log in to vCenter

Open your browser:

https://<vcenter-IP-or-FQDN>

Login with:

administrator@vsphere.local

---

## Step 2 – Create a Datacenter

1. In the left menu, right-click on the vCenter Server name.
2. Select:
   **New Datacenter**
3. Enter a name (example: Production-DC).
4. Click **OK**.

The Datacenter container is now created.

---

## Step 3 – (Optional) Create a Cluster

If you plan to use HA or DRS:

1. Right-click the Datacenter.
2. Select:
   **New Cluster**
3. Enter cluster name (example: Production-Cluster).
4. Enable:
   - HA (optional)
   - DRS (optional)
5. Click **OK**.

---

## Step 4 – Add ESXi Host

1. Right-click the Datacenter or Cluster.
2. Select:
   **Add Host**
3. Enter the ESXi host IP or FQDN.
4. Provide root credentials.
5. Accept security certificate.
6. Assign license (if required).
7. Click **Finish**.

Repeat the process for additional ESXi hosts.

---

## Step 5 – Verify Hosts

After adding hosts, verify:

- Host status is connected
- Datastores are visible
- Networking is configured
- No alarms or warnings

You can now manage all hosts centrally from vCenter.

---

## Best Practices

- Use consistent naming (esxi01, esxi02).
- Ensure all hosts use the same ESXi version.
- Configure shared storage before enabling HA.
- Verify DNS resolution for all hosts.

---

## Summary

Creating a Datacenter in vCenter provides logical organization for your infrastructure. Adding ESXi hosts allows centralized management, clustering, and advanced features like HA and DRS.
