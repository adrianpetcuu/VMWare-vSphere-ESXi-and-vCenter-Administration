
# Install VMware Tools

## Introduction

VMware Tools is a suite of utilities that enhances the performance and management of virtual machines running on VMware platforms such as ESXi and VMware Workstation.

Installing VMware Tools is highly recommended for both Windows and Linux virtual machines.

---

## Benefits of VMware Tools

Installing VMware Tools provides:

- Improved video/display performance
- Optimized network drivers
- Better mouse and keyboard integration
- Time synchronization with host
- Graceful shutdown and reboot from hypervisor
- Enhanced VM performance

---

## Install VMware Tools on ESXi

### Step 1: Mount VMware Tools ISO

1. Log in to ESXi Host Client.
2. Select the Virtual Machine.
3. Click:
   Actions → Guest OS → Install VMware Tools

This mounts the VMware Tools ISO inside the VM.

---

## Install VMware Tools on Windows VM

### Step 1: Open the Mounted ISO

1. Inside the Windows VM, open File Explorer.
2. Go to This PC.
3. Open the mounted VMware Tools CD drive.

---

### Step 2: Run Installer

1. Double-click setup.exe.
2. Choose Typical installation.
3. Click Next.
4. Click Install.
5. Click Finish after installation completes.

---

### Step 3: Reboot

Restart the virtual machine to complete installation.

---

## Install VMware Tools on Linux VM

### Step 1: Mount ISO

After selecting Install VMware Tools from ESXi or Workstation:

1. Open terminal in Linux VM.
2. Create mount directory:

   sudo mkdir /mnt/cdrom

3. Mount CD:

   sudo mount /dev/cdrom /mnt/cdrom

---

### Step 2: Extract Installer

1. Copy tar file to /tmp:

   cp /mnt/cdrom/VMwareTools-*.tar.gz /tmp

2. Navigate to /tmp:

   cd /tmp

3. Extract file:

   tar -zxvf VMwareTools-*.tar.gz

---

### Step 3: Run Installer

1. Navigate to extracted folder:

   cd vmware-tools-distrib

2. Run installer:

   sudo ./vmware-install.pl

3. Press Enter to accept default settings.

---

### Step 4: Reboot

After installation completes:

   sudo reboot

---

## Alternative (Recommended for Modern Linux)

For modern Linux distributions (Ubuntu, Debian, CentOS):

Install open-vm-tools instead:

Ubuntu/Debian:

   sudo apt install open-vm-tools

CentOS/RHEL:

   sudo yum install open-vm-tools

Then reboot the VM.

This method is preferred in most modern Linux systems.

---

## Verify Installation

On Windows:

- Open Services
- Confirm VMware Tools service is running

On Linux:

   vmware-toolbox-cmd -v

---

## Best Practices

- Keep VMware Tools updated
- Install immediately after OS installation
- Reboot after installation
- Use open-vm-tools for Linux when possible

---

## Summary

VMware Tools improves performance, usability, and integration between the host and the virtual machine. It is an essential step after installing any operating system in a VMware environment.
