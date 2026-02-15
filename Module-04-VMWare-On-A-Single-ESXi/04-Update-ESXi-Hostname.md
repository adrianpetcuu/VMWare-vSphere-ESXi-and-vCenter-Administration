
# Update ESXi Hostname

## Introduction

Changing the ESXi hostname is a common administrative task. It is recommended to configure a proper Fully Qualified Domain Name (FQDN) for production environments.

This guide explains how to update the ESXi hostname using both the Direct Console (DCUI) and the ESXi Host Client.

---

## Method 1: Update Hostname via DCUI (Console)

### Step 1: Access DCUI

1. Go to the physical ESXi server console.
2. Press **F2** to log in.
3. Enter the root username and password.

---

### Step 2: Configure Management Network

1. Select **Configure Management Network**.
2. Choose **DNS Configuration**.
3. Select:
   - Use the following DNS server addresses and hostname
4. Enter:
   - Primary DNS server
   - Hostname (example: esxi01.company.local)

5. Press **Esc**.
6. Confirm restart of the management network.

---

## Method 2: Update Hostname via ESXi Web Interface

### Step 1: Log in to ESXi Host Client

1. Open a browser.
2. Navigate to:
   https://<ESXi-IP-Address>
3. Log in as root.

---

### Step 2: Modify Hostname

1. Go to **Host** → **Manage** → **System**.
2. Click **Edit** next to Hostname.
3. Enter the new hostname (FQDN recommended).
4. Click **Save**.

---

## Step 3: Verify DNS Resolution

Ensure:

- Forward DNS record exists (hostname → IP)
- Reverse DNS record exists (IP → hostname)

You can test from ESXi console:

Ping the DNS server and gateway to confirm connectivity.

---

## Optional: Restart Management Services

If needed, restart management network:

- From DCUI → Restart Management Network
- Or reboot the host during maintenance window

---

## Important Notes

- Always use FQDN in production environments.
- Ensure DNS is configured before changing hostname.
- If the host is part of vCenter, remove it from inventory before changing hostname.
- After hostname change, reconnect the host in vCenter.

---

## Best Practices

- Use consistent naming conventions (e.g., esxi01, esxi02).
- Match hostname with DNS records.
- Document all infrastructure changes.
- Perform hostname change during maintenance window.

---

## Summary

Updating the ESXi hostname is done through DNS configuration in DCUI or via the Host Client interface. Proper DNS configuration and consistent naming conventions are essential for stable enterprise environments.
