The `du` and `df` commands are both used for managing disk space, but they serve different purposes and provide different types of information. Here’s a detailed comparison with examples:

### `df` Command

- **Purpose:** `df` (disk free) shows the amount of disk space available and used on mounted file systems. It provides a summary of space usage for the entire file system or specified file systems.

- **Focus:** Overall space usage and availability at the file system level.

- **Output:** Shows total space, used space, available space, and the percentage of space used for each file system.

- **Typical Use Cases:** Checking how much disk space is available on a drive or partition; monitoring disk usage across different file systems.

#### Example Usage:
1. **Display Disk Space Usage for All File Systems:**
   ```bash
   df -h
   ```
   **Output:**
   ```
   Filesystem      Size  Used Avail Use% Mounted on
   /dev/sda1       50G   25G   23G  54% /
   /dev/sdb1      100G   60G   35G  65% /data
   ```

2. **Show Disk Usage for Specific File System Type:**
   ```bash
   df -t ext4
   ```
   **Output:**
   ```
   Filesystem      Size  Used Avail Use% Mounted on
   /dev/sda1       50G   25G   23G  54% /
   ```

### `du` Command

- **Purpose:** `du` (disk usage) estimates and reports the disk space used by files and directories within the file system. It provides details about space usage at the directory and file level.

- **Focus:** Space usage for specific files and directories.

- **Output:** Shows the amount of disk space used by each file or directory and can summarize usage.

- **Typical Use Cases:** Finding out which directories or files are consuming the most space; getting detailed usage information for specific directories.

#### Example Usage:
1. **Display Disk Usage of Current Directory:**
   ```bash
   du -h
   ```
   **Output:**
   ```
   4.0K    ./subdir1
   12M     ./subdir2
   1.5G    ./subdir3
   1.6G    .
   ```

2. **Display Disk Usage for a Specific Directory:**
   ```bash
   du -sh /path/to/directory
   ```
   **Output:**
   ```
   1.6G    /path/to/directory
   ```

3. **Show Disk Usage Up to a Depth of 2:**
   ```bash
   du -h --max-depth=2
   ```
   **Output:**
   ```
   4.0K    ./subdir1/inner
   12M     ./subdir2
   1.0G    ./subdir3/subsubdir
   1.6G    .
   ```

### Summary of Differences

- **Scope of Information:**
  - `df` provides a summary of space usage for entire file systems.
  - `du` provides detailed information about disk usage for specific files and directories.

- **Granularity:**
  - `df` shows overall disk space available and used on a file system level.
  - `du` shows how much space is used by individual files and directories.

- **Use Case:**
  - Use `df` to check the overall space and availability on partitions or disks.
  - Use `du` to analyze space usage within specific directories and files, to find large files or directories consuming significant space.

