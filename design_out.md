 INFO_LEVEL
------------

The scenario is based on a high confidence MISP event about a complex Linux backdoor named Kobalos, targeting high performance computing infrastructure. The malware is known to be portable to Linux, BSD, Solaris, and possibly AIX and Windows. It communicates with its Command and Control (C2) server over SSH on port 7070 using the IP address 151.80.57.191.

ACCESS_LEVEL
-------------

The exercise will be conducted from a user account named `cyrano` on the target host with SSH access to the next-target and c2-server hosts. The user has sudo privileges on the target host.

TRAINING_LEVEL 1
-----------------

### Task: Identify/investigate/detect suspicious service

**Objective:** Determine if the `sshd` service is running on the target host.

**Hint:** Use the `ss` command to list open network connections and services.

```bash
ss -tuln | grep sshd
```

**Validation:** If the output contains a line with the `sshd` service, the task is considered complete.

TRAINING_LEVEL 2
-----------------

### Task: Identify/investigate/detect persistence mechanism

**Objective:** Investigate how Kobalos establishes persistence on the target host.

**Hint:** Look for signs of the malware embedded in OpenSSH server executable (sshd) or stand-alone variants that connect to a C&C server or wait for an inbound connection on a given TCP port.

```bash
# Check if sshd binary has been modified
md5sum /usr/bin/sshd | grep -q "73576d5a21ec2f164fe37bea86964e18dca1b800a8c7a104223cc35d74e7bd58"
```

**Validation:** If the output contains a line with the expected MD5 hash, the task is considered complete.

TRAINING_LEVEL 3
-----------------

### Task: Identify/investigate/detect malicious services

**Objective:** Determine if there are any other suspicious services running on the target host that could be related to Kobalos.

**Hint:** Use `netstat` or `ss` commands to list open network connections and services.

```bash
# Check for unusual services listening on non-standard ports
netstat -tuln | grep -vE '(ssh|http|https)'
```

**Validation:** If the output contains any lines with unusual services or unexpected ports, the task is considered complete.