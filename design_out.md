Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**INFO_LEVEL**
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected BRICKSTORM backdoor infection on your organization's Linux systems. The BRICKSTORM backdoor is known for its sophisticated evasion techniques and multi-layered communication capabilities. Your goal is to identify, investigate, and contain the threat.

**Scenario Objectives:**
1. Identify suspicious services and files related to the BRICKSTORM backdoor.
2. Investigate the backdoor's communication patterns and persistence mechanisms.
3. Contain the threat by blocking C2 communication and removing persistence.

**Scenario Difficulty:** Intermediate

**Scenario Type:** Exercise

**Include Q/A:** true

**Include Hint:** true

---

**ACCESS_LEVEL**
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

**TRAINING_LEVEL 1**
**Task Title:** Identify Suspicious Service

**Task Description:**
While investigating the target system, you notice an unusual service running. Identify the suspicious service related to the BRICKSTORM backdoor.

**Task Instructions:**
1. Connect to the target system using SSH.
2. List all running services and look for any suspicious or unfamiliar services.
3. Identify the service related to the BRICKSTORM backdoor.

**Flag:** updatemgr.service

**Hint:** Use systemctl to list all running services.

**Q/A:**
Q: What is the name of the suspicious service?
A: updatemgr.service

---

**TRAINING_LEVEL 2**
**Task Title:** Investigate Service Persistence

**Task Description:**
The BRICKSTORM backdoor is known to use persistence mechanisms to maintain its presence on infected systems. Investigate how the identified service maintains persistence.

**Task Instructions:**
1. Examine the service unit file for the suspicious service.
2. Identify the persistence mechanism used by the service.
3. Note the path to the service unit file.

**Flag:** /etc/systemd/system/updatemgr.service

**Hint:** Check the service unit file for ExecStart and other relevant directives.

**Q/A:**
Q: What is the path to the service unit file?
A: /etc/systemd/system/updatemgr.service

---

**TRAINING_LEVEL 3**
**Task Title:** Contain C2 Communication

**Task Description:**
The BRICKSTORM backdoor communicates with a command and control (C2) server. To contain the threat, you need to block this communication.

**Task Instructions:**
1. Identify the port used by the suspicious service for C2 communication.
2. Block the identified port using the firewall.
3. Verify that the port is blocked.

**Flag:** 8090

**Hint:** Use iptables or ufw to block the port.

**Q/A:**
Q: What is the port number used for C2 communication?
A: 8090

---

This scenario is strictly aligned with the provided sandbox environment, MISP event, and security profile. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigating and containing the BRICKSTORM backdoor, leveraging the known indicators and behaviors from the MISP event.