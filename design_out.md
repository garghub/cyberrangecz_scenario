 1. Kobalos Backdoor Investigation Exercise
2. Defence-oriented Scenario
3. Intermediate
4. Incident Response
5. Investigate a Kobalos backdoor infection in a sandbox environment

### network_topology:
- c2-server (c2-server) - Ubuntu 20.04 LTS
- target (Target) - Ubuntu 20.04 LTS
- next-target (Next Target) - Ubuntu 20.04 LTS

### levels:

LEVEL 1: INFO_LEVEL
   - title: Introduction to the Kobalos Backdoor Investigation Exercise
   - story: Welcome to the Kobalos Backdoor Investigation Exercise! Your mission is to investigate a suspected Kobalos backdoor infection in our sandbox environment. The malware has been observed targeting high-performance computing infrastructure and has been linked to various cyber attacks. You will be provided with access to the affected system, logs, and indicators of compromise (IOCs). Your goal is to identify the initial access vector, lateral movement, persistence mechanisms, and command and control (C2) communication.
   - objective: Investigate a Kobalos backdoor infection in our sandbox environment and gather evidence about the malware's behavior.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Sandbox Environment
   - topology_overview: In this exercise, you will be given access to a target system (Target) that has been infected with the Kobalos backdoor. The Target is a Ubuntu 20.04 LTS machine with an IP address of 192.168.50.5. You can reach it via SSH using the default lab credentials: username: student, password: Passw0rd!.
   - entry_host: Target
   - role: Target
   - access_method: SSH
   - username: student
   - password: Passw0rd!
   - credential_source: Default Lab Credentials
   - instructions: Connect to the target system using SSH and start your investigation.

LEVEL 3: TRAINING_LEVEL
   - title: Initial Access Vector Investigation
   - task_description: Analyze the logs on the Target system to identify the initial access vector used by the Kobalos backdoor.
   - validation_logic: Search for SSH-related log entries indicating a brute force attack or unusual login activity.
   - aligned_nice_task: T1078 - Initial Access
   - demonstrated_skill: Analyzing system logs
   - applied_knowledge: Understanding initial access techniques used by malware
   - related_event_elements: SSH bruteforce, initial access via ssh

LEVEL 4: TRAINING_LEVEL
   - title: Lateral Movement Investigation
   - task_description: Investigate the Target system for signs of lateral movement by the Kobalos backdoor. Look for any unusual file transfers or network connections.
   - validation_logic: Check for files with suspicious names or modified timestamps, and examine netstat output for active connections.
   - aligned_nice_task: T1021 - Lateral Movement
   - demonstrated_skill: Identifying lateral movement techniques
   - applied_knowledge: Understanding how malware moves within a network
   - related_event_elements: payload drop to /tmp/.installer, data encrypted for impact

LEVEL 5: TRAINING_LEVEL
   - title: Command and Control (C2) Communication Investigation
   - task_description: Analyze the Target system's network traffic to identify any communication with the Kobalos backdoor's command and control server.
   - validation_logic: Look for outgoing connections on port 7070, which is known to be used by the Kobalos C2 server.
   - aligned_nice_task: T1071 - Exfiltration Over Command and Control
   - demonstrated_skill: Analyzing network traffic
   - applied_knowledge: Understanding how malware communicates with its command and control infrastructure
   - related_event_elements: c2 beacon to 151.80.57.191:7070 every 120s

### scoring_strategy:
Points will be awarded based on the completeness and accuracy of your findings, as well as the quality of your analysis and reporting.

### optional_hints:
Hint 3: Look for any unusual network connections or outgoing traffic from the Target system.

Question 3: What is the IP address of the Kobalos C2 server?
Answer: 151.80.57.191

### optional_QA:
Question 1: What is the purpose of the target system in this exercise?
Answer: The target system is a Ubuntu 20.04 LTS machine that has been infected with the Kobalos backdoor. Its purpose is to serve as the focus of your investigation.

Question 2: What are the default lab credentials for accessing the sandbox environment?
Answer: Username: student, Password: Passw0rd!