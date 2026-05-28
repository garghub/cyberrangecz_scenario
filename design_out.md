### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux system infected with the BRICKSTORM backdoor. Your goal is to identify and mitigate the threat, including its command and control (C2) communications, persistence mechanisms, and lateral movement activities.

**Learning Objectives:**
- Identify indicators of compromise (IOCs) related to the BRICKSTORM backdoor.
- Analyze network traffic for suspicious C2 communications.
- Investigate persistence mechanisms and lateral movement activities.
- Develop mitigation strategies to contain and remove the threat.

**Prerequisites:**
- Basic knowledge of Linux command line.
- Familiarity with network analysis tools.
- Understanding of incident response procedures.

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
Investigate the running services on the target system and identify any suspicious services that may be related to the BRICKSTORM backdoor.

**Steps:**
1. Log in to the target system using SSH.
2. List all running services using the appropriate command.
3. Identify any suspicious services, particularly those named "vami".
4. Document the service name and its associated details.

**Flag:** vami

**Validation:**
The flag should be the name of the suspicious service identified.

**Hint:**
Use commands like `systemctl list-units --type=service` or `ps aux` to list running services.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Persistence Mechanism

**Description:**
Examine the system for persistence mechanisms used by the BRICKSTORM backdoor. Focus on environment variables and service configurations.

**Steps:**
1. Check the PATH environment variable for any suspicious modifications.
2. Inspect service configurations for any unusual entries.
3. Identify any persistence mechanisms related to the "vami" service.
4. Document the persistence mechanism and its details.

**Flag:** vami

**Validation:**
The flag should be the name of the service associated with the persistence mechanism.

**Hint:**
Use commands like `echo $PATH` and `systemctl list-unit-files` to investigate persistence mechanisms.

---

#### TRAINING_LEVEL 3
**Task:** Analyze Network Traffic for C2 Communications

**Description:**
Analyze network traffic on the target system to identify any suspicious outbound connections to known C2 IP addresses and ports.

**Steps:**
1. Use network analysis tools to monitor outbound connections.
2. Identify any connections to the IP address 1.1.1.1 on port 443.
3. Document the details of the suspicious connections, including timestamps and data transferred.
4. Develop a plan to block these connections.

**Flag:** 443

**Validation:**
The flag should be the port number used for the suspicious C2 communications.

**Hint:**
Use tools like `tcpdump`, `netstat`, or `ss` to analyze network traffic.

---