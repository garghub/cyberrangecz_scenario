### Scenario: Kobalos Malware Investigation

#### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Kobalos malware infection on a high-performance computing (HPC) cluster. Kobalos is a complex malware that targets HPC clusters and other high-profile systems, providing remote access, file system manipulation, and proxying capabilities. Your goal is to identify and mitigate the malware's presence on the affected systems.

**Learning Objectives:**
- Identify indicators of compromise (IOCs) related to Kobalos malware.
- Investigate suspicious services and files on compromised hosts.
- Analyze network traffic for signs of command and control (C2) communication.
- Mitigate the malware's persistence mechanisms and C2 communication.

**Prerequisites:**
- Basic knowledge of Linux command line.
- Familiarity with network security concepts.
- Understanding of malware analysis and incident response procedures.

**Scenario Duration:** 2 hours

---

#### ACCESS_LEVEL
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano

**Access Method:** SSH

**Privilege Boundaries:**
- Initial access with user-level privileges.
- Escalation to root privileges may be required for certain tasks.

**Reachable Hosts:**
- next-target (IP: 192.168.50.6)
- c2-server (IP: 192.168.40.5)

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service

**Description:**
Investigate the services running on the target host and identify any suspicious services that may be related to the Kobalos malware.

**Steps:**
1. Log in to the target host using SSH.
2. List all running services using the appropriate command.
3. Identify any suspicious services, particularly those related to SSH or remote access.
4. Document the name of the suspicious service.

**Flag:** Kobalos C&C

**Validation:**
- The flag should be the name of the suspicious service identified.

**Hint:**
- Look for services that are not part of the standard system configuration or those that have unusual properties.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Persistence Mechanism

**Description:**
Examine the persistence mechanisms used by the Kobalos malware on the target host.

**Steps:**
1. Investigate the SSH server configuration and related files.
2. Look for any modifications or unusual entries that indicate persistence.
3. Identify the persistence mechanism used by the malware.
4. Document the name of the service or file associated with the persistence mechanism.

**Flag:** OpenSSH server

**Validation:**
- The flag should be the name of the service or file associated with the persistence mechanism.

**Hint:**
- Check the SSH server configuration files and look for any unusual entries or modifications.

---

#### TRAINING_LEVEL 3
**Task:** Analyze Network Traffic for C2 Communication

**Description:**
Analyze network traffic on the target host to identify any signs of command and control (C2) communication with the Kobalos malware.

**Steps:**
1. Use network monitoring tools to capture and analyze traffic on the target host.
2. Look for any unusual outbound connections, particularly to known Kobalos C2 servers.
3. Identify the IP address and port used for C2 communication.
4. Document the IP address and port used for C2 communication.

**Flag:** 151.80.57.191:7070

**Validation:**
- The flag should be the IP address and port used for C2 communication.

**Hint:**
- Use tools like `tcpdump` or `Wireshark` to capture and analyze network traffic.

---

### Conclusion
By completing these tasks, you will have identified and mitigated the Kobalos malware on the affected systems, ensuring the security and integrity of the HPC cluster.