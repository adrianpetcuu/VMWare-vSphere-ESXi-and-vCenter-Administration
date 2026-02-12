# Basic Virtualization Terms

Understanding virtualization requires familiarity with common technical terms used in data centers and cloud environments.

---

## 1. Host

A **host** is a physical server that provides hardware resources (CPU, RAM, storage, network) to run virtual machines.

It runs a hypervisor that manages virtualization.

---

## 2. Hypervisor

A **hypervisor** is the software layer that enables virtualization.

It:
- Creates and runs virtual machines
- Allocates hardware resources
- Ensures isolation between VMs

Two types:
- **Type 1 (Bare-metal)** – Installed directly on hardware
- **Type 2 (Hosted)** – Installed on top of an operating system

---

## 3. Virtual Machine (VM)

A **Virtual Machine (VM)** is a software-based computer that runs:
- A guest operating system
- Applications
- Virtual hardware (vCPU, vRAM, vDisk, vNIC)

Each VM operates independently from others.

---

## 4. Guest Operating System

The **guest OS** is the operating system installed inside a virtual machine (e.g., Windows Server, Linux).

It behaves as if running on physical hardware.

---

## 5. vCPU (Virtual CPU)

A **vCPU** is a virtual processor assigned to a VM.

It maps to a physical CPU core (or thread) on the host.

More vCPUs generally allow better performance but consume more host resources.

---

## 6. vRAM (Virtual Memory)

**vRAM** is the amount of memory allocated to a virtual machine.

It is carved out from the physical RAM of the host server.

---

## 7. Virtual Disk

A **virtual disk** is a file that represents a VM's hard drive.

Common formats:
- VMDK
- VHD / VHDX
- QCOW2

It stores the OS, applications, and data of the VM.

---

## 8. Datastore

A **datastore** is a logical storage container where virtual machine files are stored.

It can reside on:
- Local disks
- SAN storage
- NAS storage
- SSD or NVMe arrays

---

## 9. Snapshot

A **snapshot** captures the state of a virtual machine at a specific point in time.

It includes:
- Disk state
- Memory state (optional)
- VM configuration

Used for testing, upgrades, and temporary rollback.

---

## 10. Clone

A **clone** is a copy of an existing virtual machine.

Types:
- Full Clone – Independent copy
- Linked Clone – Shares base disk with parent VM

---

## 11. Template

A **template** is a master VM image used to quickly deploy new virtual machines.

It ensures standardized configurations.

---

## 12. Resource Pool

A **resource pool** is a logical grouping of CPU and RAM resources.

It allows administrators to:
- Set limits
- Reserve resources
- Prioritize workloads

---

## 13. High Availability (HA)

**High Availability (HA)** automatically restarts virtual machines on another host if a physical server fails.

It minimizes downtime.

---

## 14. Live Migration

**Live Migration** allows a running VM to move from one host to another without downtime.

Used for:
- Maintenance
- Load balancing
- Hardware upgrades

---

## 15. Overcommitment

**Overcommitment** means assigning more virtual resources than physically available.

Example:
- 128GB physical RAM
- 200GB allocated to VMs

The hypervisor manages usage dynamically.

---

## Summary

These basic virtualization terms form the foundation of understanding how modern data centers and cloud environments operate. Mastering them is essential for working with platforms like VMware, Hyper-V, or KVM.
