 Based on the provided MISP event, sandbox topology, Ansible configuration, and security profile, I will generate a deployable KYPO scenario aligned with the given constraints.

---

### INFO_LEVEL
The scenario is based on a Mirai botnet targeting Realtek and Huawei routers. The attack uses various exploits to infiltrate devices, installs a new encoder, and sets up DDoS attack capabilities.

### ACCESS_LEVEL
The exercise will be conducted from the `c2-server` host with the username `cyrano`. SSH access is available to all hosts in the sandbox.

### TRAINING_LEVEL 1
**Task:** Identify/investigate/detect suspicious beacon service

**Description:** Analyze network traffic on the `c2-server` host to identify a potential beaconing service used by the Mirai botnet.

**Hint:** Look for unusual outbound connections or processes related to the malware indicators of compromise (IOCs).

**Flag:** Service name associated with the beaconing service.

---

### TRAINING_LEVEL 2
**Task:** Identify/investigate/detect suspicious flood service

**Description:** Investigate network traffic on the `bot1` and `bot2` hosts to identify a potential flood service used by the Mirai botnet for DDoS attacks.

**Hint:** Look for unusual outbound connections or processes related to the malware IOCs.

**Flag:** Service name associated with the flood service.

---

### TRAINING_LEVEL 3
**Task:** Contain/Block C2 communication

**Description:** Configure a firewall rule on the `router` host to block communication between the botnet members (`bot1`, `bot2`) and the command-and-control server (`c2-server`).

**Hint:** Use the C2 IP addresses provided in the MISP event as a starting point.

**Flag:** Port number associated with the blocked communication.