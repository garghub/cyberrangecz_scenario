### Scenario: Kobalos Malware Investigation

#### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Kobalos malware infection on a high-performance computing (HPC) cluster. Kobalos is a complex malware that targets HPC clusters and other high-profile systems, providing remote access, terminal sessions, and proxying capabilities. Your goal is to identify and mitigate the malware's presence on the affected systems.

**Learning Objectives:**
- Identify indicators of compromise (IOCs) related to Kobalos malware.
- Investigate suspicious services and files.
- Analyze network traffic for signs of command and control (C2) communication.
- Mitigate the malware's persistence mechanisms and C2 communication.

**Prerequisites:**
- Basic knowledge of Linux command line.
- Familiarity with network security concepts.
- Understanding of malware analysis and incident response procedures.

**Scenario Duration:** 2 hours

---

#### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service

**Description:**
Investigate the target system for suspicious services. Kobalos malware is known to embed itself in the OpenSSH server executable. Identify the suspicious service running on the target system.

**Steps:**
1. Log in to the target system using SSH.
2. List all running services using the `systemctl list-units --type=service` command.
3. Identify any suspicious services, particularly those related to SSH.

**Flag:** sshd

**Validation:**
The flag should be the name of the suspicious service identified.

**Hint:**
Look for services that are not typically expected on a standard system or those that have unusual configurations.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Suspicious File

**Description:**
Kobalos malware is known to modify the OpenSSH server executable. Investigate the target system for suspicious files related to the SSH service.

**Steps:**
1. Navigate to the directory containing the SSH service executable, typically `/usr/sbin/`.
2. Check the file attributes and hash of the `sshd` executable using the `ls -l /usr/sbin/sshd` and `sha256sum /usr/sbin/sshd` commands.
3. Compare the hash with the known good hash of the SSH service executable.

**Flag:** 75edf6662811d001da179b96bd06d675aa2439fd88a981cc84f24b4a5b4f8f45

**Validation:**
The flag should be the hash of the suspicious file identified.

**Hint:**
Use the `sha256sum` command to generate the hash of the file and compare it with the known good hash.

---

#### TRAINING_LEVEL 3
**Task:** Analyze Network Traffic for C2 Communication

**Description:**
Kobalos malware communicates with a command and control (C2) server. Analyze the network traffic on the target system to identify any suspicious outbound connections.

**Steps:**
1. Use the `netstat -tuln` command to list all network connections.
2. Look for any suspicious outbound connections, particularly those to the IP address `151.80.57.191` on port `7070`.
3. Investigate the process responsible for the suspicious connection using the `ps aux | grep <PID>` command.

**Flag:** 7070

**Validation:**
The flag should be the port number used for the suspicious outbound connection.

**Hint:**
Use the `netstat` command to identify suspicious network connections and investigate the responsible process.

---