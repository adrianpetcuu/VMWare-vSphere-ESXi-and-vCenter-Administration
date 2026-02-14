
# Download and Install VMware Workstation Player

## Introduction

VMware Workstation Player is a free (for personal use) Type 2 hypervisor that allows you to run virtual machines on a Windows or Linux computer.

It is commonly used for:
- Learning virtualization
- Testing operating systems
- Building home labs
- Running legacy applications

---

## System Requirements

Before installation, ensure your system meets the minimum requirements:

### Hardware Requirements
- 64-bit CPU with virtualization support (Intel VT-x or AMD-V)
- Minimum 4 GB RAM (8 GB recommended)
- At least 20 GB free disk space
- Hardware virtualization enabled in BIOS/UEFI

### Operating System (Host)
- Windows 10 / 11 (64-bit)
- Supported Linux distributions

---

## Step 1: Download VMware Workstation Player

1. Open your web browser.
2. Go to the official VMware website.
3. Navigate to **Products → Workstation Player**.
4. Select the version for your operating system (Windows or Linux).
5. Download the installer file.

The file will typically be:
- `.exe` for Windows
- `.bundle` for Linux

---

## Step 2: Install on Windows

1. Double-click the downloaded `.exe` file.
2. Click **Next** on the setup wizard.
3. Accept the license agreement.
4. Choose the installation location (default is recommended).
5. Select optional features (such as desktop shortcut).
6. Click **Install**.
7. Click **Finish** when installation completes.
8. Restart your computer if prompted.

---

## Step 3: Install on Linux

1. Open a terminal.
2. Navigate to the directory where the file was downloaded.
3. Make the file executable:

```bash
chmod +x VMware-Player-*.bundle
```

4. Run the installer:

```bash
sudo ./VMware-Player-*.bundle
```

5. Follow the installation prompts.

---

## Step 4: First Launch

1. Open VMware Workstation Player.
2. Choose **Use VMware Workstation Player for free for non-commercial use** (if applicable).
3. Accept the license agreement.
4. The main interface will appear.

You are now ready to create virtual machines.

---

## Step 5: Enable Virtualization in BIOS (If Needed)

If you receive an error related to virtualization:

1. Restart your computer.
2. Enter BIOS/UEFI (usually by pressing F2, DEL, or F10).
3. Enable:
   - Intel VT-x (Intel Virtualization Technology)
   - AMD-V (SVM Mode)
4. Save changes and reboot.

---

## Creating Your First Virtual Machine

1. Click **Create a New Virtual Machine**.
2. Select an ISO file (Windows or Linux).
3. Choose the guest operating system.
4. Allocate disk size.
5. Set CPU and RAM.
6. Click **Finish**.

Your virtual machine is now ready to power on.

---

## Summary

VMware Workstation Player is easy to download and install. It provides a simple way to run virtual machines on your local computer without needing enterprise hardware. It is an excellent starting point for learning virtualization concepts and preparing for VMware certifications.