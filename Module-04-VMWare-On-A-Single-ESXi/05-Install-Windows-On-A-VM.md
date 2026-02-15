
# Install Windows on a Virtual Machine

## Introduction

This guide explains how to install Microsoft Windows inside a Virtual Machine (VM) using VMware ESXi or VMware Workstation.

The process is similar for Windows 10, Windows 11, and Windows Server editions.

---

## Prerequisites

Before starting, ensure you have:

- A created Virtual Machine
- Windows ISO file (uploaded to datastore or available locally)
- Minimum 4 GB RAM (8 GB recommended for Windows Server)
- At least 40 GB virtual disk space
- CPU virtualization enabled

---

## Step 1: Attach Windows ISO

### On ESXi

1. Edit VM settings.
2. Go to CD/DVD Drive.
3. Select Datastore ISO file.
4. Choose the Windows ISO.
5. Check "Connect at power on".

### On Workstation

1. Open VM Settings.
2. Select CD/DVD.
3. Choose "Use ISO image file".
4. Select the Windows ISO.

---

## Step 2: Power On the VM

1. Click Power On.
2. Open the Console.
3. The Windows installer will boot automatically.

---

## Step 3: Start Windows Installation

1. Select language, time, and keyboard layout.
2. Click Next.
3. Click Install Now.

---

## Step 4: Enter Product Key

- Enter product key (if available)
- Or choose "I don't have a product key" for evaluation

Select Windows edition if prompted.

---

## Step 5: Select Installation Type

Choose:

Custom: Install Windows only (advanced)

---

## Step 6: Disk Selection

1. Select the virtual disk.
2. Click New (if required).
3. Click Next.

Windows will create necessary partitions automatically.

---

## Step 7: Installation Process

The installer will:

- Copy files
- Install features
- Install updates
- Restart automatically

This may take 10–20 minutes depending on resources.

---

## Step 8: Initial Configuration

After reboot:

- Set region
- Configure network
- Create user account (or Administrator for Server)
- Set password
- Configure privacy settings

---

## Step 9: Install VMware Tools (Important)

Installing VMware Tools improves:

- Display resolution
- Network driver performance
- Mouse integration
- Time synchronization

### On ESXi

1. Select VM.
2. Click Actions → Guest OS → Install VMware Tools.
3. Inside Windows, open the mounted CD.
4. Run setup.exe.
5. Complete installation and reboot.

---

## Step 10: Windows Updates

After installation:

1. Open Settings.
2. Go to Windows Update.
3. Install latest updates.

This ensures security and stability.

---

## Recommended VM Settings

For Windows 10 / 11:

- 2–4 vCPUs
- 8 GB RAM
- 60 GB disk (recommended)

For Windows Server:

- 4 vCPUs
- 8–16 GB RAM
- 80+ GB disk

---

## Post-Installation Best Practices

- Rename computer
- Configure static IP (if server)
- Join to Active Directory (if applicable)
- Enable firewall
- Install antivirus (if required)

---

## Summary

Installing Windows on a virtual machine follows the same steps as a physical installation. Once VMware Tools are installed and updates are applied, the VM is ready for production, lab, or testing environments.
