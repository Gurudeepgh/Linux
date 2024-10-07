To create a group and add users to it in Red Hat Enterprise Linux (RHEL), you can follow these steps:

### Step 1: Create a Group

1. Open a terminal.
2. Use the `groupadd` command to create a new group. Replace `groupname` with your desired group name.

   ```bash
   sudo groupadd groupname
   ```

### Step 2: Create Users

You can create users using the `useradd` command. Replace `username` with the desired username.

```bash
sudo useradd username
```

### Step 3: Add Users to the Group

To add users to the newly created group, use the `usermod` command. Replace `username` with the user's name and `groupname` with the group name.

```bash
sudo usermod -aG groupname username
```

### Example

Here's an example where we create a group called `developers` and add two users, `alice` and `bob`, to that group.

1. Create the group:

   ```bash
   sudo groupadd developers
   ```

2. Create the users:

   ```bash
   sudo useradd alice
   sudo useradd bob
   ```

3. Add the users to the group:

   ```bash
   sudo usermod -aG developers alice
   sudo usermod -aG developers bob
   ```

### Step 4: Verify

To check if the users have been added to the group successfully, you can use the `getent` command:

```bash
getent group groupname
```

This will display the group and its members.

### Notes

- Use the `-aG` option with `usermod` to append the user to the group without removing them from other groups.
- You might want to set a password for the users with `passwd username` if needed.
- Ensure you have the necessary permissions (use `sudo`) to execute these commands. 

If you have any more questions or need further assistance, feel free to ask!
