# `whereis` Command Reference

The `whereis` command is used to locate the binary, source, and manual page files for a command or program in Unix-like operating systems. It provides a quick way to find the location of executable files and related documentation.

## Basic Usage

- `whereis [options] [command]`
  - Locates the binary, source, and manual page files for `[command]`.
  - Example: `whereis bash`

## Options

- `-b`
  - Search only for binaries.
  - Example: `whereis -b gcc`

- `-m`
  - Search only for manual pages.
  - Example: `whereis -m bash`

- `-s`
  - Search only for source files.
  - Example: `whereis -s bash`

- `-u`
  - Display results that are not found in the specified directories.
  - Example: `whereis -u bash`

## Example Commands

```bash
# Locate the binary, source, and manual page files for 'bash'
whereis bash

# Locate only the binary file for 'gcc'
whereis -b gcc

# Locate only the manual page file for 'bash'
whereis -m bash

# Locate only the source file for 'bash'
whereis -s bash
