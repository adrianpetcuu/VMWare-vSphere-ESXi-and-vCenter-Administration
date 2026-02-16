
# Accessing vCenter – HTML, SSH, and Admin Portal

## 1. HTML5 vSphere Client (Main Interface)

This is the primary web interface for managing vCenter.

Access via browser:

https://<vcenter-FQDN-or-IP>

Login with:
administrator@vsphere.local

Used for:
- Managing ESXi hosts
- Creating clusters
- Managing VMs
- Monitoring performance

Note: Flash client is deprecated. Only HTML5 is supported in modern versions.

---

## 2. VAMI (vCenter Appliance Management Interface)

Used for appliance-level configuration and backups.

Access:

https://<vcenter-FQDN-or-IP>:5480

Login with:
root

Used for:
- Backup and restore
- Network configuration
- NTP settings
- Appliance health monitoring

---

## 3. SSH Access

SSH allows command-line access to the vCenter appliance.

Enable SSH from:
VAMI → Access → Enable SSH

Then connect using:

ssh root@<vcenter-IP>

Used for:
- Troubleshooting
- Log inspection
- Advanced configuration

---

## Summary

- Port 443 → Main vSphere HTML interface  
- Port 5480 → Appliance management (VAMI)  
- SSH → Command-line troubleshooting  

Each interface serves a different administrative purpose.
