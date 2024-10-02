Environment variables in Linux are dynamic values that can affect the behavior of processes and programs running in the operating system. They are part of the environment in which a process runs and can provide information about the system, user settings, and configurations.

### Common Environment Variables

1. **`HOME`**: The home directory of the current user.
   ```bash
   echo $HOME
   ```

2. **`USER`**: The username of the current user.
   ```bash
   echo $USER
   ```

3. **`PATH`**: A colon-separated list of directories where executable programs are located.
   ```bash
   echo $PATH
   ```

4. **`SHELL`**: The path to the current user's shell.
   ```bash
   echo $SHELL
   ```

5. **`PWD`**: The current working directory.
   ```bash
   echo $PWD
   ```

6. **`LANG`**: The current language and locale settings.
   ```bash
   echo $LANG
   ```

7. **`TERM`**: The terminal type being used.
   ```bash
   echo $TERM
   ```

### Setting Environment Variables

You can set environment variables in the shell using the `export` command:

```bash
export VARIABLE_NAME=value
```

**Example:**
```bash
export MY_VAR="Hello, World!"
```

You can then access it with:

```bash
echo $MY_VAR
```

### Persisting Environment Variables

To make an environment variable persistent across sessions, you can add the `export` command to your shell's startup file:

- For **bash**, add it to `~/.bashrc` or `~/.bash_profile`.
- For **zsh**, add it to `~/.zshrc`.
  
**Example:**
```bash
echo 'export MY_VAR="Hello, World!"' >> ~/.bashrc
```

Then, apply the changes with:

```bash
source ~/.bashrc
```

### Unsetting Environment Variables

To remove an environment variable, you can use the `unset` command:

```bash
unset VARIABLE_NAME
```

**Example:**
```bash
unset MY_VAR
```

### Viewing Environment Variables

To view all environment variables, you can use the `env` or `printenv` command:

```bash
env
```
or
```bash
printenv
```

### Summary

Environment variables are a fundamental part of the Linux operating system, providing crucial information and settings for user sessions and applications. They can be set, modified, and used to control the behavior of programs. If you have specific scenarios or further questions about environment variables, feel free to ask!
