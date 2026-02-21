## RAID (Redundant Array of Independent Disks)

RAID combines multiple
physical disks into one
logical unit to improve
performance, redundancy,
or both.

---

### Common RAID Levels

- **RAID 0 (Striping)**
  - Performance only
  - No redundancy
  - Minimum 2 disks

- **RAID 1 (Mirroring)**
  - Data duplicated
  - High availability
  - Minimum 2 disks

- **RAID 5 (Striping + Parity)**
  - Performance + redundancy
  - Tolerates 1 disk failure
  - Minimum 3 disks

- **RAID 6 (Double Parity)**
  - Tolerates 2 disk failures
  - Minimum 4 disks

- **RAID 10 (1+0)**
  - Mirror + stripe
  - High performance and redundancy
  - Minimum 4 disks

---

### Software RAID in Linux
Linux uses **mdadm**
for software RAID.

Install:
```bash
dnf install mdadm -y
```

---

### Create RAID (Example RAID 1)
```bash
mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/sdb /dev/sdc
```

---

### Check RAID Status
```bash
cat /proc/mdstat
mdadm --detail /dev/md0
```

---

### Filesystem and Mount
```bash
mkfs.ext4 /dev/md0
mount /dev/md0 /data
```

---

### Summary
RAID improves disk
performance and/or
availability and is
commonly used in servers
for data protection.
