
# Managing Hosts on vCenter

## Overview

vCenter provides centralized management for all ESXi hosts in your environment.  
From a single interface, you can monitor, configure, maintain, and troubleshoot multiple hosts.

---

## Accessing Host Management

1. Log in to vCenter:
   https://<vcenter-IP-or-FQDN>

2. Navigate to:
   Menu → Hosts and Clusters

3. Select the desired ESXi host.

---

## Host Summary View

The Summary tab displays:

- ESXi version
- CPU and memory usage
- Uptime
- Hardware model
- Datastore information
- Network configuration

This provides a quick health overview.

---

## Managing Host Configuration

From the Configure tab, you can manage:

### Networking
- Standard and Distributed vSwitches
- VMkernel adapters
- VLAN configuration
- Physical NICs

### Storage
- Datastores (VMFS, NFS)
- Storage adapters (iSCSI, FC)
- Device status

### Licensing
- Assign or change ESXi license

### Authentication
- Join host to Active Directory
- Configure permissions and roles

---

## Host Maintenance Mode

Before performing hardware maintenance:

1. Right-click the host.
2. Select **Enter Maintenance Mode**.

If HA and shared storage are configured:
- VMs are migrated automatically (vMotion).

After maintenance:
- Exit Maintenance Mode.

---

## Monitoring and Performance

Under the Monitor tab you can view:

- CPU usage graphs
- Memory consumption
- Disk I/O statistics
- Network throughput
- Events and system logs

This helps identify performance bottlenecks.

---

## Host Updates and Patching

Using Lifecycle Manager (if available):

- Check for updates
- Apply patches
- Upgrade ESXi version
- Remediate multiple hosts at once

Always use maintenance mode before patching.

---

## Best Practices

- Keep ESXi versions consistent across cluster
- Monitor hardware health regularly
- Enable NTP for time synchronization
- Use consistent naming conventions
- Perform updates during maintenance windows

---

## Summary

Managing hosts in vCenter allows centralized control over configuration, monitoring, maintenance, and updates. Proper host management ensures stability, performance, and availability in a virtualized environment.
