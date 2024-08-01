# Linux Package Management Commands

This document provides explanations for various Linux package management commands using `dpkg`, `apt`, and `apt-get`.

## Commands

### 1. dpkg --list
This command lists all installed packages on your system. It provides a summary of each package, including its name, version, and a short description.

**Usage:**

```
dpkg --list
```
### 2. sudo apt --purge remove gimp
This command removes the `gimp` package along with its configuration files from your system. `apt --purge remove` combines the removal of both the package and its configuration files.

**Usage:**
```
sudo apt --purge remove gimp
```
### 3. sudo apt remove gimp
This command removes the `gimp` package from your system but keeps its configuration files intact. Use this command if you might want to reinstall the package later and retain its previous settings.

**Usage:**
```
sudo apt remove gimp
```
### 4. sudo apt-get autoremove
This command removes packages that were automatically installed to satisfy dependencies for other packages and are no longer needed.

**Usage:**
```
sudo apt-get autoremove
```

### 5. sudo apt purge --auto-remove gimp
This command removes the `gimp` package along with its configuration files and then removes any dependencies that were installed with it and are no longer needed.

**Usage:**
```
sudo apt purge --auto-remove gimp
```

### 6. sudo apt clean
This command clears out the local repository of retrieved package files. It removes everything but the lock file from `/var/cache/apt/archives/` and `/var/cache/apt/archives/partial/`.

**Usage:**
```
sudo apt clean
```
