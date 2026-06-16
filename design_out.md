Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**INFO_LEVEL**
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in your organization's high-performance computing (HPC) environment. Kobalos is a complex, multiplatform malware that targets HPC clusters and other high-profile systems. It is known to grant remote access to the file system, provide terminal session capabilities, and allow proxying connections to other infected servers.

**Scenario Objectives:**
1. Investigate suspicious services and files
2. Identify and contain command and control (C2) communications
3. Analyze lateral movement techniques

**Scenario Prerequisites:**
- Familiarity with Linux command line
- Basic knowledge of network security concepts
- Understanding of malware analysis and incident response processes

---

**ACCESS_LEVEL**
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

**TRAINING_LEVEL 1**
**Task:** Investigate Suspicious Service

**Task Description:**
While monitoring the target system, you notice an unusual service running. Investigate this service to determine if it is related to the Kobalos malware.

**Hint:** Check the status of all services on the system.

**Flag:** OpenSSHserver.service

**Validation:**
The flag should be submitted as the name of the suspicious service.

---

**TRAINING_LEVEL 2**
**Task:** Identify C2 Communication

**Task Description:**
Examine network connections and logs to identify any suspicious outbound communications that may indicate command and control (C2) activity.

**Hint:** Check the network connections and logs for any unusual outbound connections.

**Flag:** 7070

**Validation:**
The flag should be submitted as the port number used for C2 communication.

---

**TRAINING_LEVEL 3**
**Task:** Analyze Lateral Movement

**Task Description:**
Investigate the lateral movement techniques used by the Kobalos malware. Identify any services or processes that facilitate the transfer of data between hosts.

**Hint:** Examine the systemd services and logs for any indications of lateral movement.

**Flag:** payload-transfer.service

**Validation:**
The flag should be submitted as the name of the service facilitating lateral movement.

---

**Scenario Conclusion:**
Congratulations! You have successfully investigated the Kobalos malware infection, identified the C2 communication, and analyzed the lateral movement techniques. Your findings will help in containing the threat and preventing further damage to the organization's HPC environment.

**Debrief:**
Review your actions and the steps taken to investigate and contain the Kobalos malware. Reflect on what you learned and how you can apply this knowledge to future incident response scenarios.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event, ensuring a realistic and engaging training experience for incident responders.