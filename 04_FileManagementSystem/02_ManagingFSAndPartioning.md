### Disk Management 
Disk management involves various tasks related to handling disk storage on a Linux system. It includes:

- **Partitioning:** Dividing a disk into partitions.
- **Formatting:** Creating file systems on partitions.
- **Mounting:** Attaching file systems to directories.
- **Monitoring:** Checking disk space and usage.
- **Repairing:** Fixing file system errors.

- 
### File System

A file system organizes and manages files on a disk. Common file systems in Linux include:

- **Ext4:** The default file system for many Linux distributions.
- **XFS:** Known for high performance and scalability.
- **NTFS:** Used by Windows.
- **FAT32:** Commonly used for compatibility with various operating systems.


### Partition of Hard Disk

Partitions are sections of a disk. They can be:

- **Primary Partition:** A primary partition can hold an operating system and can be bootable. A disk can have up to four primary partitions.
- **Extended Partition:** An extended partition acts as a container for logical partitions and allows for more than four partitions on a disk.
- **Logical Volume:** Partitions within an extended partition. They can be resized easily compared to primary partitions.

### Viewing Disk and Partition Information**

- **List Disk Partitions with fdisk:**
  To list all partitions on your system, use:
  ```bash
  sudo fdisk -l
  ```
  The `fdisk -l` command lists all available disks and their partitions on a Linux system. It provides detailed information about the disk layout and partitioning scheme. Here’s an explanation of the typical output you might see when running `sudo fdisk -l`:

![image](https://github.com/user-attachments/assets/b1d8a0ab-b067-4176-b467-d7f6717c784a)

### **Example Output of `sudo fdisk -l`**

```plaintext
Disk /dev/sda: 100 GiB, 107374182400 bytes, 209715200 sectors
Disk model: Virtual Disk
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: gpt
Disk identifier: 12345678-1234-1234-1234-123456789abc

Device         Start       End   Sectors   Size Type
/dev/sda1       2048   1048575   1046528   511M EFI System
/dev/sda2    1048576  209715199 208666624  99.5G Linux filesystem
```

### **Explanation of the Output**

1. **Disk Information:**
   - **`Disk /dev/sda:`**: Specifies the disk device name. `/dev/sda` is the first disk on the system.
   - **`100 GiB, 107374182400 bytes, 209715200 sectors:`**: Shows the total size of the disk in GiB (Gibibytes), bytes, and sectors.
   - **`Disk model: Virtual Disk:`**: Provides information about the disk model, if available. In this case, it’s a virtual disk.
   - **`Units: sectors of 1 * 512 = 512 bytes:`**: Indicates the size of each sector. Sectors are the smallest addressable units on the disk.
   - **`Sector size (logical/physical): 512 bytes / 512 bytes:`**: Shows the logical and physical sector sizes.
   - **`I/O size (minimum/optimal): 512 bytes / 512 bytes:`**: Provides information about the minimum and optimal I/O sizes for the disk.
   - **`Disk label type: gpt:`**: Indicates the partitioning scheme used. GPT (GUID Partition Table) is modern and supports larger disks and more partitions than MBR.
   - **`Disk identifier: 12345678-1234-1234-1234-123456789abc:`**: A unique identifier for the disk.

2. **Partition Table:**
   - **`Device:`**: Lists the device name and partition numbers.
     - **`/dev/sda1`**: The first partition on the `/dev/sda` disk.
     - **`/dev/sda2`**: The second partition on the `/dev/sda` disk.
   - **`Start:`**: The starting sector of the partition.
   - **`End:`**: The ending sector of the partition.
   - **`Sectors:`**: The total number of sectors in the partition.
   - **`Size:`**: The size of the partition in human-readable format (e.g., 511M for 511 MiB, 99.5G for 99.5 GiB).
   - **`Type:`**: Indicates the type of partition or file system:
     - **`EFI System:`**: A partition used for UEFI (Unified Extensible Firmware Interface) systems, typically used for booting.
     - **`Linux filesystem:`**: A partition formatted with a Linux file system (e.g., ext4, xfs).


- **List Disk Partitions with lsblk:**
  ```bash
  lsblk
  ```
  The `lsblk` command in Red Hat Enterprise Linux (RHEL) and other Linux distributions lists information about block devices, such as disks and partitions. The output can help you understand the layout and structure of your storage devices.

Here's a breakdown of what each element in the `lsblk` output means:

### **Example Output of `lsblk` Command**

```plaintext
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda    8:0    0  100G  0 disk
├─sda1 8:1    0   50G  0 part /rhel/root
├─sda2 8:2    0   30G  0 part [SWAP]
└─sda3 8:3    0   20G  0 part /rhel/home
```

### **Explanation of Output Columns and Entries**

1. **`NAME`**: This column displays the device or partition names. For example:
   - **`sda`**: This is the name of the entire disk device.
   - **`sda1`**: This is the name of the first partition on the `sda` disk.
   - **`sda2`**: This is the name of the second partition on the `sda` disk.
   - **`sda3`**: This is the name of the third partition on the `sda` disk.

2. **`MAJ:MIN`**: These numbers represent the major and minor device numbers, which are used by the kernel to identify the device.

3. **`RM`**: Indicates whether the device is removable (1 for removable, 0 for not).

4. **`SIZE`**: Shows the size of the device or partition. For example, `100G` represents 100 gigabytes.

5. **`RO`**: Indicates whether the device is read-only (1 for read-only, 0 for read-write).

6. **`TYPE`**: Specifies the type of the device. Common types include:
   - **`disk`**: A physical disk device.
   - **`part`**: A partition on a disk.
   - **`lvm`**: Logical volume (if using LVM).

7. **`MOUNTPOINT`**: Shows where the partition is mounted in the filesystem hierarchy. For example:
   - **`/rhel/root`**: The mount point of the `sda1` partition.
   - **`[SWAP]`**: Indicates that `sda2` is used as swap space (temporary storage for RAM).

### **Detailed Example Explanation**

- **`sda`**: This represents the entire physical disk device.
  - **`sda1`**: This is the first partition on the `sda` disk. It is 50 GB in size and is mounted at `/rhel/root`, meaning it is used as the root filesystem for the `/rhel` directory.
  - **`sda2`**: This is the second partition on the `sda` disk. It is 30 GB in size and is used as swap space. Swap space is used for virtual memory when RAM is full.
  - **`sda3`**: This is the third partition on the `sda` disk. It is 20 GB in size and is mounted at `/rhel/home`, which means it is used for storing user home directories under `/rhel`.

### **Summary**

- **`sda`** is the disk device.
- **`sda1`, `sda2`, and `sda3`** are partitions on the `sda` disk.
- **`/rhel/root`** is the mount point for the first partition, which is used for the root filesystem.
- **`[SWAP]`** indicates the second partition is used for swap space.
- **`/rhel/home`** is the mount point for the third partition, which is used for user data.


### **3. Creating and Managing Partitions**

- **Using `fdisk` for MBR(4 Primary Partitions) Partitions:**

  1. **Open `fdisk` with the disk you want to partition:**
     ```bash
     sudo fdisk /dev/sdX
     ```
     Replace `/dev/sdX` with your actual disk (e.g., `/dev/sda`).

  2. **Commands:**
     - `n` – Create a new partition.
     - `d` – Delete a partition.
     - `p` – Print the partition table.
     - `w` – Write changes to the disk and exit.

- **Using `parted` for GPT Partitions:**

  1. **Open `parted` with the disk:**
     ```bash
     sudo parted /dev/sdX
     ```

  2. **Commands:**
     - `mklabel gpt` – Create a new GPT partition table.
     - `mkpart` – Create a new partition.
     - `rm` – Remove a partition.
     - `print` – Show partition table.
     - `quit` – Exit `parted`.

### **4. Formatting Partitions with File Systems**

- **Format with `mkfs`:**

  - **Ext4 File System:**
    ```bash
    sudo mkfs.ext4 /dev/sdXn
    ```
    Replace `/dev/sdXn` with your partition (e.g., `/dev/sda1`).

  - **XFS File System:**
    ```bash
    sudo mkfs.xfs /dev/sdXn
    ```

  - **Btrfs File System:**
    ```bash
    sudo mkfs.btrfs /dev/sdXn
    ```

  - **NTFS File System:**
    ```bash
    sudo mkfs.ntfs /dev/sdXn
    ```

### **5. Mounting and Unmounting File Systems**

- **Mount a File System:**

  1. **Create a Mount Point:**
     ```bash
     sudo mkdir /mnt/mydrive
     ```

  2. **Mount the File System:**
     ```bash
     sudo mount /dev/sdXn /mnt/mydrive
     ```

- **Unmount a File System:**

  ```bash
  sudo umount /mnt/mydrive
  ```

  or if the device is busy:

  ```bash
  sudo umount -l /mnt/mydrive
  ```

### **6. Configuring Automatic Mounting**

To automatically mount a file system at boot, add an entry to `/etc/fstab`.

- **Edit `/etc/fstab`:**

  ```bash
  sudo nano /etc/fstab
  ```

- **Add an Entry:**

  Example entry for an ext4 partition:

  ```bash
  /dev/sdXn /mnt/mydrive ext4 defaults 0 2
  ```

  - `/dev/sdXn` – Device name.
  - `/mnt/mydrive` – Mount point.
  - `ext4` – File system type.
  - `defaults` – Mount options.
  - `0` – Dump option (0 to disable).
  - `2` – File system check order (1 for root, 2 for others).

### **7. Resizing Partitions**

- **Using `parted`:**

  1. **Resize a Partition:**
     ```bash
     sudo parted /dev/sdX
     ```

     - Use `resizepart` to change partition size.

- **Using `resize2fs` for ext filesystems:**

  1. **Resize the File System:**
     ```bash
     sudo resize2fs /dev/sdXn
     ```

  - For ext4 file systems, ensure you’ve adjusted the partition size using `fdisk` or `parted` before resizing the file system.

### **8. Checking and Repairing File Systems**

- **Check and Repair with `fsck`:**

  ```bash
  sudo fsck /dev/sdXn
  ```

  - **Note:** It’s best to unmount the file system before running `fsck`.

### **Summary**

Managing file systems and partitions involves:

- **Viewing Disk Information:** Using `fdisk`, `lsblk`, and `df`.
- **Creating and Managing Partitions:** Using `fdisk`, `parted`, and similar tools.
- **Formatting:** Using `mkfs` to create file systems.
- **Mounting and Unmounting:** Using `mount` and `umount`.
- **Automatic Mounting:** Configuring `/etc/fstab`.
- **Resizing Partitions:** Adjusting sizes with `parted` and resizing file systems with `resize2fs`.
- **Checking and Repairing:** Using `fsck` to check and repair file systems.

Understanding these concepts will help you effectively manage disk space, maintain system stability, and ensure proper organization of data on your Linux system.
