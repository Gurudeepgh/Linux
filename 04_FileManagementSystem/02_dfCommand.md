The `df` command in Linux is used to report file system disk space usage. It displays information about the available and used disk space on file systems. Here's a summary of the `df` command along with its various options:

### Basic Syntax:
```bash
df [OPTION]... [FILE]...
```

### Common Options:

- `-a`, `--all`  
  Show all file systems, including those with 0 blocks.

- `-B`, `--block-size=SIZE`  
  Scale sizes by SIZE before printing them. E.g., `-B M` will show sizes in megabytes.

- `--total`  
  Produce a grand total for all filesystems.

- `-h`, `--human-readable`  
  Print sizes in human-readable format (e.g., 1K, 234M, 2G).

- `-H`  
  Like `-h`, but use powers of 1000 (e.g., 1K = 1000 bytes).

- `-i`, `--inodes`  
  Show inode information instead of block usage.

- `--output[=FIELD_LIST]`  
  Specify the output format. FIELD_LIST can include options like `source`, `fssize`, `used`, `avail`, `pcent`, etc. (see the `--output` section for details).

- `-l`, `--local`  
  Show only local file systems.

- `-P`, `--portability`  
  Use the POSIX output format.

- `-T`, `--print-type`  
  Print the file system type.

- `-t`, `--type=TYPE`  
  Show only file systems of the specified type(s).

- `-x`, `--exclude-type=TYPE`  
  Exclude file systems of the specified type(s).

- `--help`  
  Display a help message and exit.

- `--version`  
  Display version information and exit.

### Examples:

1. **Display Disk Usage in Human-Readable Format:**
   ```bash
   df -h
   ```

2. **Show Disk Usage in Megabytes:**
   ```bash
   df -B M
   ```

3. **Include Inode Information:**
   ```bash
   df -i
   ```

4. **Show Only Local File Systems:**
   ```bash
   df -l
   ```

5. **Display Only Certain File System Types:**
   ```bash
   df -t ext4
   ```

6. **Exclude Specific File System Types:**
   ```bash
   df -x tmpfs
   ```

7. **Output Custom Fields:**
   ```bash
   df --output=source,fstype,used,avail
   ```

For a complete list of options and detailed descriptions, you can refer to the man page by running:
```bash
man df
```

Or consult the `df` command's help with:
```bash
df --help
```
