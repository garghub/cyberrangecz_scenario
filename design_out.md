 1. BRICKSTORM Backdoor Investigation Exercise
2. Defence-oriented Scenario
3. Intermediate
4. Incident Response
5. Investigate a BRICKSTORM backdoor incident in a simulated lab environment

### network_topology:
- c2-server (Ubuntu)
  - role: C2 Server
  - purpose: Command and Control server for the BRICKSTORM backdoor
- target (Ubuntu)
  - role: Target
  - purpose: Compromised system hosting the BRICKSTORM backdoor
- next-target (Ubuntu)
  - role: Next Target
  - purpose: A reachable system from the compromised target for lateral movement analysis

### levels:

LEVEL 1: INFO_LEVEL
   - title: Introduction to the BRICKSTORM Backdoor Incident
     story: Welcome to the BRICKSTORM Backdoor Investigation Exercise. Your mission is to investigate a suspected BRICKSTORM backdoor incident in a simulated lab environment. The BRICKSTORM backdoor is a Go-based malware that uses multiple techniques to maintain persistence on compromised systems, communicate with its command and control (C2) server using HTTPS and WebSocket protocols, and can download files from the C2 server or specific sections of a file from the compromised host.
   - objective: Your goal is to identify the presence of the BRICKSTORM backdoor on the target system, analyze its behavior, and gather evidence for further investigation.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Lab Environment
     topology_overview: In this exercise, you will be given access to a lab environment containing three systems: c2-server, target, and next-target. The target system is compromised by the BRICKSTORM backdoor, while the c2-server acts as its command and control server. The next-target system is reachable from the target for lateral movement analysis.
     entry_host: target
     role: Target
     access_method: SSH
     username: cyrano
     password: cyrano (lab credentials)
     credential_source: Default lab credentials
     instructions: Use the provided credentials to connect to the target system via SSH.

LEVEL 3: TRAINING_LEVEL
   - title: Identify BRICKSTORM Backdoor Indicators of Compromise
     task_description: Search for indicators of compromise (IOCs) related to the BRICKSTORM backdoor on the target system.
     validation_logic: Use the `grep` command to search for known hashes, domains, and IP addresses associated with the BRICKSTORM backdoor in relevant log files and directories.
     aligned_nice_task: T1084 - System Network Scanning
     demonstrated_skill: Linux File System Navigation
     applied_knowledge: Malware Analysis Techniques
     related_event_elements: Hashes, Domains, IP addresses

LEVEL 4: TRAINING_LEVEL
   - title: Analyze BRICKSTORM Backdoor Behavior
     task_description: Investigate the behavior of the BRICKSTORM backdoor on the target system by analyzing its network traffic and processes.
     validation_logic: Use tools such as `tcpdump` or `netstat` to analyze network traffic, and `ps` or `pgrep` to list running processes. Look for signs of communication with the C2 server or lateral movement within the lab environment.
     aligned_nice_task: T1086 - PowerShell
     demonstrated_skill: Network Traffic Analysis
     applied_knowledge: Malware Behavior Understanding
     related_event_elements: Network traffic, Processes

LEVEL 5: TRAINING_LEVEL
   - title: Gather Evidence for Further Investigation
     task_description: Collect evidence related to the BRICKSTORM backdoor incident for further analysis and reporting. This may include relevant log files, network captures, or malware samples.
     validation_logic: Use the `cp`, `tar`, or `scp` commands to copy relevant files from the target system to a secure location for further analysis.
     aligned_nice_task: T1027 - Remote Access Software
     demonstrated_skill: Evidence Collection and Preservation
     applied_knowledge: Incident Response Procedures
     related_event_elements: Log files, Network captures, Malware samples

### scoring_strategy:
Points will be awarded based on the completeness and accuracy of the investigation, as well as the quality of evidence collected.

### optional_hints:
Hint 3: To find more information about the BRICKSTORM backdoor, you can refer to the MISP event provided in the scenario description.

### optional_QA:
Question 3: What is the primary purpose of the target system in this exercise?
Answer: The primary purpose of the target system is to serve as a compromised system hosting the BRICKSTORM backdoor.