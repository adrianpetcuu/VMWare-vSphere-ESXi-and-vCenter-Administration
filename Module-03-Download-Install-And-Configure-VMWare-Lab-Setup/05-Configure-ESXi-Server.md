
# Configure VMware ESXi Server

## Introduction

After installing VMware ESXi, the next step is to configure the server properly for management and virtual machine deployment.

This guide covers the basic post-installation configuration steps.

---

## Step 1: Access the Direct Console (DCUI)

1. On the ESXi physical console, press **F2**.
2. Log in with the **root** account.
3. You will enter the System Customization menu.

---

## Step 2: Configure Management Network

1. Select **Configure Management Network**.
2. Configure the following:

### Network Adapters
- Select the correct physical NIC for management traffic.

### VLAN (Optional)
- Set VLAN ID if your management network uses VLAN tagging.

### IPv4 Configuration
- Choose **Set static IPv4 address and network configuration**.
- Enter:
  - IP Address
  - Subnet Mask
  - Default Gateway

### DNS Configuration
- Enter primary DNS server.
- Set hostname (e.g., esxi01.company.local).

3. Press **Esc** and confirm restart of management network.

---

## Step 3: Test Network Connectivity

From DCUI:

1. Select **Test Management Network**.
2. Verify:
   - Default gateway reachable
   - DNS resolution working

---

## Step 4: Access ESXi Web Interface

From another computer:

1. Open a browser.
2. Go to:

   https://<ESXi-IP-Address>

3. Log in with:
   - Username: root
   - Password: your configured password

You are now in the ESXi Host Client.

---

## Step 5: Configure Storage (Datastore)

1. Go to **Storage**.
2. Click **New Datastore**.
3. Choose disk or LUN.
4. Select VMFS version.
5. Assign a datastore name.
6. Complete the wizard.

---

## Step 6: Configure Networking (vSwitch)

1. Go to **Networking**.
2. Review default **vSwitch0**.
3. Create additional:
   - Port Groups
   - VLAN IDs
   - VMkernel adapters (for vMotion, etc.)

---

## Step 7: Enable Services (Optional)

Go to **Host → Manage → Services**:

- Enable SSH (for troubleshooting)
- Enable ESXi Shell (if needed)

⚠ Disable SSH after use for security reasons.

---

## Step 8: Configure NTP (Time Synchronization)

1. Go to **Host → Manage → System → Time & Date**.
2. Enable NTP service.
3. Add NTP servers (e.g., pool.ntp.org).
4. Start and set to automatic.

---

## Step 9: Security Hardening (Basic)

- Change default root password if needed
- Disable unnecessary services
- Configure lockdown mode (optional)
- Configure firewall rules

---

## Optional: Add ESXi to vCenter Server

If using vCenter:

1. Log into vCenter.
2. Add host to a Datacenter or Cluster.
3. Enter ESXi IP and credentials.
4. Assign license if required.

---

## Summary

Configuring ESXi after installation includes setting up management networking, storage, time synchronization, and basic security settings. Once configured, the host is ready to run virtual machines or be added to a vCenter-managed environment.
