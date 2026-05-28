### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host infected with the BRICKSTORM backdoor. Your goal is to identify and mitigate the threat posed by this sophisticated malware.

**Learning Objectives:**
- Identify indicators of compromise related to the BRICKSTORM backdoor.
- Investigate persistence mechanisms and lateral movement techniques.
- Analyze network traffic for signs of command and control (C2) communication.
- Mitigate the threat by containing and removing the malware.

**Prerequisites:**
- Basic knowledge of Linux command line.
- Familiarity with network security concepts.
- Understanding of malware analysis and incident response procedures.

**Scenario Duration:** 2 hours

---

#### ACCESS_LEVEL
**Entry Host:** target (192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Reachable Hosts:**
- next-target (192.168.50.6)
- c2-server (192.168.40.5)

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service

**Description:**
Investigate the running services on the target host and identify any suspicious services that may be related to the BRICKSTORM backdoor.

**Steps:**
1. Connect to the target host using SSH.
2. List all running services using the appropriate command.
3. Identify any suspicious services, particularly those named "vmware-sphere" or "WebService".

**Flag:** vmware-sphere

**Validation:**
The flag should be the name of the suspicious service identified.

**Hint:**
Check the list of running services and look for any that seem out of place or match the known indicators of the BRICKSTORM backdoor.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Persistence Mechanism

**Description:**
Examine the persistence mechanisms used by the BRICKSTORM backdoor to maintain its presence on the compromised host.

**Steps:**
1. Investigate the environment variables and PATH modifications on the target host.
2. Look for any suspicious entries that may indicate the presence of the BRICKSTORM backdoor.
3. Document your findings, including the specific environment variables or PATH modifications.

**Flag:** vmware-sphere

**Validation:**
The flag should be the name of the service associated with the persistence mechanism.

**Hint:**
Check the environment variables and PATH settings for any unusual entries that could be used to maintain persistence.

---

#### TRAINING_LEVEL 3
**Task:** Analyze Network Traffic for C2 Communication

**Description:**
Analyze the network traffic on the target host to identify any signs of command and control (C2) communication related to the BRICKSTORM backdoor.

**Steps:**
1. Monitor the network traffic on the target host, focusing on outbound connections.
2. Look for any suspicious connections to known C2 IP addresses or ports, such as 8.8.8.8 on port 443.
3. Document your findings, including the source and destination IP addresses, ports, and any relevant protocol information.

**Flag:** 443

**Validation:**
The flag should be the port number used for C2 communication.

**Hint:**
Use network monitoring tools to identify any unusual outbound connections that match the known indicators of the BRICKSTORM backdoor.

---