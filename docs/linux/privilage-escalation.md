
# Privilege Escalation

Privilege escalation is a process by which an attacker gains elevated access to a system or network. It usually involves exploiting a vulnerability or misconfiguration that allows the attacker to move from a lower privilege (such as a normal user account) to a higher privilege (such as an administrator or root account).

## 1. Types of Privilege Escalation
- **Horizontal Privilege Escalation**: When an attacker accesses another user's account with the same privilege level (e.g., from one user to another user).
- **Vertical Privilege Escalation**: When an attacker gains higher privileges, such as from a regular user to an administrator or root account.

## 2. Common Attack Vectors
- **Exploiting Software Vulnerabilities**: Some vulnerabilities in software allow for privilege escalation. Examples include buffer overflow, race conditions, and poorly written setuid programs in Linux.
- **Misconfigurations**: Incorrect permissions on files, services, or processes can provide attackers a way to escalate privileges. Common examples are world-writable files, or processes running with unnecessary elevated privileges.
- **Weak Passwords or Default Credentials**: Attackers may use weak or default credentials to escalate privileges.
- **Kernel Exploits**: Vulnerabilities in the kernel can give an attacker full control over the system.
- **Sudo Misconfigurations**: Misconfigurations in sudoers files or incorrect use of the sudo command can allow attackers to escalate their privileges.
- **Service Exploits**: Exploiting services running with higher privileges, such as web servers or database servers.
- **Path Vulnerabilities**: Using environment variables such as `$PATH` to trick the system into executing malicious code.

## 3. Linux Privilege Escalation Techniques
- **Kernel Exploits**: Attackers exploit kernel vulnerabilities to gain root access. Tools like `linux-exploit-suggester` can help identify vulnerabilities.
- **SUID Files**: Files with the SUID bit set run with the privileges of the file owner, regardless of who executes them. Attackers may search for SUID files (`find / -perm -4000`) to exploit.
- **Weak File Permissions**: Files or directories with improper permissions can be exploited to gain elevated access. For example, writable `/etc/passwd` or `/etc/shadow` files allow privilege escalation.
- **Sudo Exploits**: Misconfigurations in `sudo` can allow non-root users to execute commands with root privileges. For example, a user might be allowed to execute a root-level binary without needing a password.
- **Crontab Jobs**: Cron jobs running as root but with writable scripts can be modified by attackers to execute malicious commands with root privileges.
- **Escaping Restricted Shells**: Sometimes users are restricted to specific environments or shells (like Docker containers or jails). Attackers can escape these restrictions using known vulnerabilities or misconfigurations.
- **Exploiting Services**: Services like `mysql`, `apache`, etc., running with elevated privileges can be exploited if they have vulnerabilities.

## 4. Windows Privilege Escalation Techniques
- **Exploiting Vulnerable Services**: Services running as SYSTEM can be exploited if vulnerable, e.g., exploiting buffer overflows.
- **DLL Hijacking**: Attackers replace legitimate DLLs with malicious ones, which get executed with elevated privileges.
- **Unquoted Service Paths**: Services that have unquoted paths can be exploited by placing malicious executables in a higher precedence directory.
- **Token Impersonation**: In some cases, attackers can steal tokens of higher-privilege processes to impersonate an administrator or SYSTEM user.
- **Registry Misconfigurations**: Misconfigured registry keys with improper permissions allow attackers to modify or add keys that grant elevated privileges.
- **UAC Bypass**: In Windows, User Account Control (UAC) can be bypassed if there are misconfigurations or known vulnerabilities.
- **Password Dumping**: Tools like `Mimikatz` can dump credentials from memory, allowing attackers to elevate privileges using other users' credentials.

## 5. Defense Against Privilege Escalation
- **Keep Software Up to Date**: Regularly update and patch systems to fix vulnerabilities.
- **Follow Least Privilege Principle**: Ensure users and services only have the minimum privileges necessary to perform their tasks.
- **Monitor and Audit Logs**: Continuously monitor system logs for suspicious activities, such as attempts to access restricted files or escalate privileges.
- **Use Strong Authentication**: Implement multi-factor authentication (MFA) and use strong password policies.
- **Proper Configuration of Services and Permissions**: Ensure correct configuration of sudo, file permissions, and services to prevent exploitation.
- **Limit SUID and SGID Programs**: Reduce the number of files with the SUID or SGID bit set.
- **Restrict Execution of Scripts in Crontab**: Avoid having writable scripts executed by root cron jobs.
- **Disable Unnecessary Services**: Minimize the attack surface by disabling services that are not required.

## 6. Tools for Privilege Escalation
- **Linux**:
  - `LinPEAS`: Script for detecting privilege escalation paths on Linux.
  - `GTFOBins`: Collection of Unix binaries that can be exploited for privilege escalation.
  - `linux-exploit-suggester`: Tool to suggest possible kernel exploits.
- **Windows**:
  - `Windows Exploit Suggester`: Detects vulnerabilities in the Windows OS that can be exploited.
  - `PowerUp`: PowerShell script to check for common privilege escalation paths on Windows.
  - `Mimikatz`: Tool for extracting passwords, hashes, and tokens from memory.

## 7. Example of Privilege Escalation Process
- **Scenario**: Gaining root access on a Linux system through SUID.
  1. Use `find / -perm -4000 2>/dev/null` to find files with the SUID bit set.
  2. Identify a vulnerable binary, such as an outdated version of `nmap`.
  3. Use the binary in interactive mode to spawn a root shell.
