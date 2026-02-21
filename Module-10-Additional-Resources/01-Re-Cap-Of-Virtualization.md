# Recap of Virtualization

## What Is Virtualization?

Virtualization is the process of creating virtual versions of physical resources such as:

- Servers
- Storage
- Networking
- Operating systems

It allows multiple virtual machines (VMs) to run on a single physical server using a hypervisor.

---

## What Is a Hypervisor?

A hypervisor is the software layer that:

- Creates and manages virtual machines
- Allocates CPU, memory, storage, and network resources
- Isolates VMs from each other

Example:
- VMware ESXi (Type 1 hypervisor)

---

## Physical vs Virtual Environment

### Traditional (Physical)

- One OS per server
- Low hardware utilization
- High cost
- Limited scalability

### Virtualized

- Multiple VMs per server
- Higher resource utilization
- Lower hardware cost
- Easier scalability

---

## Key Components in VMware Environment

- ESXi → Hypervisor
- vCenter → Central management
- Datastores → VM storage
- Clusters → Group of hosts
- HA → Automatic VM restart
- DRS → Load balancing
- vMotion → Live migration

---

## Benefits of Virtualization

- Reduced hardware costs
- Better resource utilization
- Faster deployment
- Improved disaster recovery
- High availability
- Scalability
- Simplified management

---

## Core VMware Features Reviewed

- VM creation and management
- Snapshots
- Cloning and templates
- OVF export/import
- HA (High Availability)
- DRS (Distributed Resource Scheduler)
- Fault Tolerance
- NFS shared storage

---

## Why Virtualization Is Important

Virtualization is the foundation of:

- Private cloud
- Hybrid cloud
- Enterprise data centers
- DevOps environments
- Disaster recovery strategies

It enables flexible, efficient, and resilient IT infrastructure.

---

## Final Summary

Virtualization allows multiple virtual machines to run on a single physical server using a hypervisor.  
In VMware environments, ESXi and vCenter provide centralized management, high availability, and advanced resource optimization.

Understanding virtualization fundamentals is essential for building scalable and reliable modern infrastructure.