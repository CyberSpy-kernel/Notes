# `echo` Command Reference

The `echo` command is used to display a line of text or a variable value on the command line. It is commonly used in shell scripts and for displaying messages.

## Basic Usage

- `echo [string]`
  - Displays `[string]` to the standard output.
  - Example: `echo "Hello, World!"`

## Special Characters

- `\n`
  - Newline character.
  - Example: `echo -e "Line 1\nLine 2"` will output:
    ```
    Line 1
    Line 2
    ```

- `\t`
  - Tab character.
  - Example: `echo -e "Column1\tColumn2"` will output:
    ```
    Column1    Column2
    ```

## Options

- `-e`
  - Enables interpretation of backslash escapes (e.g., `\n`, `\t`).
  - Example: `echo -e "Hello\nWorld"`

- `-n`
  - Suppresses the trailing newline.
  - Example: `echo -n "Hello, World!"` will output `Hello, World!` without moving to a new line.

- `-E`
  - Disables the interpretation of backslash escapes (default behavior in some systems).
  - Example: `echo -E "Hello\nWorld"`

## Variables

- `echo $VARIABLE`
  - Displays the value of the environment variable `VARIABLE`.
  - Example: `echo $HOME` will display the path to the user's home directory.

- `echo ${VARIABLE}`
  - Displays the value of the environment variable `VARIABLE` with optional additional formatting.
  - Example: `echo ${HOME}`

## Redirecting Output

- `echo [string] > file.txt`
  - Redirects the output to `file.txt`, overwriting its contents.
  - Example: `echo "Hello, File!" > file.txt`

- `echo [string] >> file.txt`
  - Appends the output to `file.txt`.
  - Example: `echo "Another Line" >> file.txt`

## Example Commands

```bash
# Display a simple string
echo "Hello, World!"

# Display a string without a trailing newline
echo -n "Hello, World!"

# Display multiple lines with newline characters
echo -e "Line 1\nLine 2"

# Display the value of an environment variable
echo $HOME

# Redirect output to a file
echo "This is a test." > testfile.txt

# Append output to a file
echo "This will be appended." >> testfile.txt
