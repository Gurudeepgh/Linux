The `free` command in Linux is used to display the amount of free and used memory in the system. It provides information about system memory usage, including physical RAM, swap space, and buffers/caches.

### Basic Syntax:
```bash
free [OPTION]...
```

### Common Options:

- `-b`, `--bytes`  
  Display memory sizes in bytes.

- `-k`, `--kilo`  
  Display memory sizes in kilobytes (default).

- `-m`, `--mega`  
  Display memory sizes in megabytes.

- `-g`, `--giga`  
  Display memory sizes in gigabytes.

- `-h`, `--human-readable`  
  Display memory sizes in a human-readable format (e.g., 1K, 234M, 2G).

- `-s`, `--seconds`  
  Continuously report memory usage at the specified interval in seconds.

- `-t`, `--total`  
  Show a total row in the output.

- `-V`, `--version`  
  Show version information.

- `--help`  
  Display help information and exit.

### Example Usage:

1. **Display Memory Usage in Kilobytes (default):**
   ```bash
   free
   ```
   **Output:**
   ```
                total        used        free      shared  buff/cache   available
   Mem:        8192000     2048000     4096000       409600     2048000     6144000
   Swap:       2048000           0     2048000
   ```

2. **Display Memory Usage in Human-Readable Format:**
   ```bash
   free -h
   ```
   **Output:**
   ```
                total        used        free      shared  buff/cache   available
   Mem:          7.8G        2.0G        3.9G        400M        2.0G        6.1G
   Swap:         2.0G          0B        2.0G
   ```

3. **Display Memory Usage in Megabytes:**
   ```bash
   free -m
   ```
   **Output:**
   ```
                total        used        free      shared  buff/cache   available
   Mem:         8192        2048        4096         400        2048        6144
   Swap:        2048           0        2048
   ```

4. **Continuously Report Memory Usage Every 5 Seconds:**
   ```bash
   free -s 5
   ```
   **Output (updates every 5 seconds):**
   ```
                total        used        free      shared  buff/cache   available
   Mem:         8192        2048        4096         400        2048        6144
   Swap:        2048           0        2048
   ```

5. **Display Total Memory and Swap Space Only:**
   ```bash
   free -t
   ```
   **Output:**
   ```
                total        used        free      shared  buff/cache   available
   Mem:         8192        2048        4096         400        2048        6144
   Swap:        2048           0        2048
   Total:       10240        2048        6144         400        4096        6144
   ```

### Understanding the Output:

- **total**: The total amount of memory or swap space.
- **used**: The amount of memory or swap space currently in use.
- **free**: The amount of memory or swap space that is not used.
- **shared**: The amount of memory used by tmpfs (shared memory).
- **buff/cache**: The amount of memory used for buffers and cache.
- **available**: The amount of memory available for starting new applications, without swapping.

The `free` command provides a quick way to check the memory usage and availability on a system, helping you monitor and manage system resources effectively.
