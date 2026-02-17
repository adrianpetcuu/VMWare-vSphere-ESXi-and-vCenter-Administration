
# Configure, Permissions and Datacenters (Menu)

## Overview

In vCenter, the **Configure**, **Permissions**, and **Datacenters** sections allow administrators to manage infrastructure settings, access control, and logical organization of resources.

---

# 1. Configure (Tab)

The **Configure** tab is available when selecting a Datacenter, Cluster, or Host.

From here you can manage:

### Networking
- vSwitches
- VMkernel adapters
- VLAN settings

### Storage
- Datastores
- Storage policies
- Storage adapters

### Services
- NTP configuration
- Host profiles
- Licensing

### System Settings
- Advanced settings
- Authentication
- Firewall rules

This section is used for infrastructure-level configuration.

---

# 2. Permissions (Access Control)

The **Permissions** section controls who can access and manage resources.

vCenter uses:

- Users
- Groups
- Roles

### Common Roles:
- Administrator
- Read-Only
- Virtual Machine Power User

To assign permissions:

1. Select object (Datacenter, Cluster, Host, VM).
2. Go to **Permissions** tab.
3. Click **Add Permission**.
4. Select user/group and role.

Permissions can be inherited by child objects.

---

# 3. Datacenters (Logical Organization)

A **Datacenter** in vCenter is a logical container used to organize:

- Clusters
- Hosts
- VMs
- Networking
- Storage

It does not represent a physical building.  
It is simply a structure for organizing infrastructure.

Example:

vCenter
└── Datacenter-Production
    ├── Cluster-01
    └── Cluster-02

---

## Best Practices

- Use clear naming conventions for Datacenters.
- Apply permissions at higher levels when possible.
- Follow least-privilege principle for user access.
- Separate production and lab environments logically.

---

## Summary

The Configure tab manages infrastructure settings, Permissions control access and roles, and Datacenters organize your environment logically. Together, they form the foundation of structured and secure vCenter administration.
