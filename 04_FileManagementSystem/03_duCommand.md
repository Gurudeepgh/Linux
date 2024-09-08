The `du` command in Linux is used to estimate and display the disk usage of files and directories. It provides information about the amount of disk space used by files and directories.

### Basic Syntax:
```bash
du [OPTION]... [FILE]...
```

### Common Options:

- `-a`, `--all`  
  Show disk usage for all files and directories, not just directories.

- `-b`, `--bytes`  
  Display sizes in bytes.

- `-h`, `--human-readable`  
  Print sizes in human-readable format (e.g., 1K, 234M, 2G).

- `-k`  
  Display sizes in kilobytes (default block size is 1024 bytes).

- `-m`  
  Display sizes in megabytes.

- `-s`, `--summarize`  
  Show only a total for each argument.

- `-c`, `--total`  
  Produce a grand total at the end of the output.

- `-d`, `--max-depth=N`  
  Show the total size of directories up to a maximum depth of N.

- `-L`, `--dereference`  
  Show the disk usage of the files pointed to by symbolic links, not the links themselves.

- `-P`, `--no-dereference`  
  Do not follow symbolic links (default behavior).

- `--time`  
  Show the time of the last modification of any file in the directory.

- `--exclude=PATTERN`  
  Exclude files and directories that match the specified pattern.

- `--help`  
  Display a help message and exit.

- `--version`  
  Display version information and exit.

### Examples:

1. **Display Disk Usage of the Current Directory:**
   ```bash
   du
   ```

2. **Display Disk Usage in Human-Readable Format:**
   ```bash
   du -h
   ```

3. **Display Disk Usage for All Files and Directories:**
   ```bash
   du -a
   ```

4. **Display Total Disk Usage for Each Directory (Summarize):**
   ```bash
   du -sh
   ```

5. **Display Disk Usage Up to a Depth of 2:**
   ```bash
   du -h --max-depth=2
   ```

6. **Display Disk Usage in Megabytes:**
   ```bash
   du -m
   ```

7. **Display Grand Total Disk Usage:**
   ```bash
   du -ch
   ```

8. **Exclude Specific Files/Directories from Output:**
   ```bash
   du --exclude=*.log
   ```

9. **Display Disk Usage of a Specific Directory:**
   ```bash
   du -sh /path/to/directory
   ```

For more detailed information, you can refer to the `du` command’s manual page:
```bash
man du
```

Or get a quick overview of the options with:
```bash
du --help
```
