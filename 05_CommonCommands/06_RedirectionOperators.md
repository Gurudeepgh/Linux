In Linux, redirection operators are used to control the input and output of commands. They allow you to redirect data to and from files instead of using the standard input (keyboard) and standard output (screen). Here are the most commonly used redirection operators:

### Output Redirection

1. **`>`** (Redirect Standard Output)
   Redirects the output of a command to a file, replacing the file's contents if it already exists.

   ```bash
   command > output.txt
   ```

   **Example:**
   ```bash
   echo "Hello, World!" > hello.txt
   ```

2. **`>>`** (Append Standard Output)
   Redirects the output of a command to a file, appending the output to the file if it exists.

   ```bash
   command >> output.txt
   ```

   **Example:**
   ```bash
   echo "Another line" >> hello.txt
   ```

### Input Redirection

3. **`<`** (Redirect Standard Input)
   Redirects input for a command from a file instead of the keyboard.

   ```bash
   command < input.txt
   ```

   **Example:**
   ```bash
   sort < unsorted.txt
   ```

### Error Redirection

4. **`2>`** (Redirect Standard Error)
   Redirects error messages (stderr) to a file, replacing the file's contents.

   ```bash
   command 2> error.txt
   ```

   **Example:**
   ```bash
   ls non_existing_file 2> error.log
   ```

5. **`2>>`** (Append Standard Error)
   Appends error messages to a file instead of replacing it.

   ```bash
   command 2>> error.txt
   ```

### Combining Output and Error Redirection

6. **`&>`** (Redirect Both Standard Output and Standard Error)
   Redirects both stdout and stderr to the same file, replacing its contents.

   ```bash
   command &> output.txt
   ```

   **Example:**
   ```bash
   ls existing_file non_existing_file &> output.log
   ```

7. **`&>>`** (Append Both Standard Output and Standard Error)
   Appends both stdout and stderr to a file.

   ```bash
   command &>> output.txt
   ```

### Here Documents

8. **`<<`** (Here Document)
   Allows you to provide a block of text as input to a command.

   ```bash
   command << EOF
   line 1
   line 2
   EOF
   ```

   **Example:**
   ```bash
   cat << EOF
   This is line 1.
   This is line 2.
   EOF
   ```

### Summary

Redirection operators are powerful tools for controlling input and output in the Linux command line, allowing for more flexible and efficient scripting and command execution. If you have specific scenarios or questions about using these operators, feel free to ask!
