### Scenario: Kobalos Malware Investigation

#### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Kobalos malware infection on a high-performance computing (HPC) cluster. Kobalos is a complex malware that targets HPC clusters and other high-profile systems, providing remote access, file system manipulation, and proxying capabilities. Your goal is to identify and mitigate the malware's presence on the affected systems.

**Learning Objectives:**
- Identify indicators of compromise (IOCs) related to the Kobalos malware.
- Investigate suspicious services and files on the affected systems.
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
2. List all running services on the system.
3. Identify the suspicious service related to the Kobalos malware.

**Flag:** sshd

**Validation:**
The flag should be the name of the suspicious service identified on the target system.

**Hint:**
Check the running services and look for any unusual or unexpected services, particularly those related to SSH.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Persistence Mechanism

**Description:**
Kobalos malware is known to use persistence mechanisms to maintain its presence on the system. Investigate the persistence mechanism used by the malware on the target system.

**Steps:**
1. Examine the SSH service configuration files for any unusual entries.
2. Check for any cron jobs or scheduled tasks that might be related to the malware.
3. Identify the persistence mechanism used by the Kobalos malware.

**Flag:** sshd

**Validation:**
The flag should be the name of the service or mechanism used for persistence by the Kobalos malware.

**Hint:**
Look for any unusual entries in the SSH service configuration files or scheduled tasks that might indicate persistence.

---

#### TRAINING_LEVEL 3
**Task:** Analyze Network Traffic for C2 Communication

**Description:**
Kobalos malware communicates with a command and control (C2) server. Analyze the network traffic on the target system to identify the C2 communication.

**Steps:**
1. Use network monitoring tools to capture and analyze network traffic on the target system.
2. Identify any suspicious outbound connections to external IP addresses or ports.
3. Determine the C2 IP address and port used by the Kobalos malware.

**Flag:** 151.80.57.191:7070

**Validation:**
The flag should be the C2 IP address and port identified in the network traffic analysis.

**Hint:**
Use tools like `tcpdump` or `Wireshark` to capture and analyze network traffic for suspicious connections.

---