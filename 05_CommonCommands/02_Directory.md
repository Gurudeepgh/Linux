In Linux, there are several commands used to manage directories. Here are some of the most common directory commands along with examples:

### 1. **`pwd`** (Print Working Directory)
Displays the current directory you are in.

```bash
pwd
```

**Example Output:**
```
/home/user
```

### 2. **`ls`** (List Directory Contents)
Lists files and directories in the current directory.

```bash
ls
```

**Example Output:**
```
Documents  Downloads  Music  Pictures  Videos
```

You can use options with `ls` to display more information:

- `-l` for a detailed list
- `-a` to include hidden files

```bash
ls -la
```

### 3. **`cd`** (Change Directory)
Changes the current directory to the specified path.

```bash
cd Documents
```

To go back to the previous directory:

```bash
cd ..
```

### 4. **`mkdir`** (Make Directory)
Creates a new directory.

```bash
mkdir new_folder
```

### 5. **`rmdir`** (Remove Directory)
Removes an empty directory.

```bash
rmdir old_folder
```

### 6. **`rm -r`** (Remove Directory and Contents)
Deletes a directory and its contents recursively.

```bash
rm -r folder_to_delete
```

### 7. **`cp`** (Copy)
Copies files or directories. To copy a directory and its contents, use the `-r` option.

```bash
cp -r source_directory target_directory
```

### 8. **`mv`** (Move or Rename)
Moves files or directories. If the target is a different name, it renames the source.

```bash
mv old_directory new_directory
```

### 9. **`find`** (Search for Files and Directories)
Searches for files and directories based on criteria.

```bash
find . -name "*.txt"
```

This command finds all `.txt` files in the current directory and its subdirectories.

### 10. **`tree`** (Display Directory Structure)
Displays the directory structure in a tree-like format. (You may need to install it first using your package manager.)

```bash
tree
```
