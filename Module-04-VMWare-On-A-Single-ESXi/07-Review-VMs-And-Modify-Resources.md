
# Review VMs and Modify Resources

## Introduction

Managing virtual machine (VM) resources is a critical administrative task in VMware environments such as ESXi and vSphere.

This guide explains how to review VM settings and modify CPU, memory, storage, and network configurations safely.

---

## Step 1: Review Virtual Machines

### On ESXi Host Client

1. Log in to:
   https://<ESXi-IP-Address>
2. Click **Virtual Machines**.
3. Select a VM from the list.

You can view:

- Power state (On / Off)
- CPU allocation
- Memory allocation
- Datastore location
- Network configuration
- VMware Tools status

---

## Step 2: View VM Summary

Click the VM name to open the **Summary tab**.

Here you can monitor:

- CPU usage
- Memory usage
- Storage usage
- IP address
- Host information

Performance graphs help identify resource bottlenecks.

---

## Step 3: Modify CPU and Memory

⚠ Best practice: Power off the VM before modifying core hardware resources (unless hot-add is enabled).

1. Select the VM.
2. Click **Actions → Edit Settings**.
3. Adjust:

### CPU
- Increase or decrease number of vCPUs
- Adjust cores per socket (if needed)

### Memory
- Increase or decrease RAM (in GB)

4. Click **Save**.

---

## Step 4: Modify Storage

### Expand Virtual Disk

1. Power off the VM.
2. Go to **Edit Settings**.
3. Select Hard Disk.
4. Increase disk size.
5. Save changes.

After expansion:
- Extend partition inside the guest OS.

---

## Step 5: Modify Network Settings

1. Edit VM settings.
2. Select Network Adapter.
3. Change:

- Port group
- VLAN
- Network type
- Adapter type

Save configuration.

---

## Step 6: Enable Hot Add (Optional)

Hot Add allows adding CPU and memory without powering off the VM.

1. Power off the VM.
2. Go to **Edit Settings → VM Options**.
3. Enable:

- CPU Hot Add
- Memory Hot Add

Save and power on VM.

---

## Step 7: Monitor Resource Usage

Go to:

**Monitor → Performance**

Check:

- CPU utilization
- Memory consumption
- Disk I/O
- Network throughput

This helps determine if resource adjustments are needed.

---

## Best Practices

- Avoid over-allocating CPU and RAM
- Monitor host capacity before increasing VM resources
- Use reservations for critical workloads
- Document resource changes
- Perform changes during maintenance window in production

---

## Common Scenarios

### When to Increase CPU:
- High CPU usage (>80% consistently)
- Application performance issues

### When to Increase Memory:
- Frequent memory swapping
- Slow application response

### When to Expand Disk:
- Low free disk space alerts
- Application storage requirements

---

## Summary

Reviewing and modifying VM resources ensures optimal performance and stability. Administrators must carefully balance resource allocation to prevent host contention while meeting workload demands.
