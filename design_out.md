### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected BRICKSTORM backdoor infection on a Linux-based network. The BRICKSTORM backdoor is known for its sophisticated evasion techniques, including SOCKS proxying, multi-layered web service communication, and varied command execution. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Investigate suspicious services and files.
- Identify persistence mechanisms.
- Detect and block C2 communication.
- Contain and mitigate the threat.

**Prerequisites:**
- Basic knowledge of Linux commands.
- Familiarity with network security concepts.
- Understanding of incident response procedures.

**Scenario Duration:** 2 hours

**Difficulty Level:** Intermediate

**Cybersecurity Approach:** Defence-oriented

**Scenario Type:** Exercise

**Include Q/A:** true

**Include Hint:** true

---

#### ACCESS_LEVEL
**Entry Host:** target (IP: 192.168.50.5)

**Username:** cyrano

**Password:** cyrano

**Access Method:** SSH

**Privilege Boundaries:**
- Initial access with user privileges.
- Escalate to root if necessary for mitigation tasks.

**Reachable Hosts:**
- next-target (IP: 192.168.50.6)

---

#### TRAINING_LEVEL 1
**Task:** Identify and investigate the suspicious service "vami".

**Description:**
The BRICKSTORM backdoor is known to use a service named "vami" for its malicious activities. Investigate the "vami" service on the target host to gather information about its behavior and configuration.

**Steps:**
1. Log in to the target host using SSH.
2. Check the running services using the `systemctl` command.
3. Investigate the "vami" service by examining its configuration files and logs.
4. Document the findings, including the service's behavior and any suspicious indicators.

**Flag:** vami

**Validation:**
- The task is marked as completed when the service name "vami" is identified and documented.

**Q/A:**
- Q: What is the purpose of the "vami" service?
- A: The "vami" service is used by the BRICKSTORM backdoor for its malicious activities, including C2 communication and lateral movement.

**Hint:**
- Use the `systemctl list-units --type=service` command to list all running services and look for the "vami" service.

---

#### TRAINING_LEVEL 2
**Task:** Identify and investigate the persistence mechanism.

**Description:**
The BRICKSTORM backdoor is known to use a persistence mechanism involving the PATH environment variable modification. Investigate the persistence mechanism on the target host to understand how the backdoor maintains its presence.

**Steps:**
1. Log in to the target host using SSH.
2. Examine the PATH environment variable using the `echo $PATH` command.
3. Check for any suspicious entries in the PATH that might indicate the persistence mechanism.
4. Document the findings, including the suspicious PATH entries and any related configuration files.

**Flag:** vami

**Validation:**
- The task is marked as completed when the persistence mechanism involving the PATH environment variable modification is identified and documented.

**Q/A:**
- Q: What is the persistence mechanism used by the BRICKSTORM backdoor?
- A: The BRICKSTORM backdoor uses the PATH environment variable modification as its persistence mechanism.

**Hint:**
- Use the `echo $PATH` command to examine the PATH environment variable and look for any suspicious entries.

---

#### TRAINING_LEVEL 3
**Task:** Contain and block C2 communication.

**Description:**
The BRICKSTORM backdoor communicates with its C2 server using a specific IP address and port. Identify the C2 communication and block it to prevent further malicious activities.

**Steps:**
1. Log in to the target host using SSH.
2. Monitor network traffic using tools like `tcpdump` or `netstat` to identify the C2 communication.
3. Block the C2 communication by adding firewall rules or disabling the relevant service.
4. Document the steps taken to block the C2 communication and verify that it has been successfully contained.

**Flag:** 443

**Validation:**
- The task is marked as completed when the C2 communication is identified and blocked, and the port number "443" is documented.

**Q/A:**
- Q: What is the purpose of blocking C2 communication?
- A: Blocking C2 communication prevents the backdoor from receiving further commands and exfiltrating data, thereby containing the threat.

**Hint:**
- Use the `tcpdump -i any port 443` command to monitor network traffic on port 443 and identify the C2 communication.

---