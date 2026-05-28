 1. Kobalos Linux Trojan Investigation Exercise
2. Defence-oriented
3. Intermediate
4. Incident Response
5. Investigate a complex Linux threat targeting high performance computing infrastructure named Kobalos, based on the provided MISP event and sandbox environment.

### network_topology:
- c2-server (role: c2-server, operating system: Ubuntu, purpose: Command & Control Server)
- target (role: Target, operating system: Ubuntu, purpose: Victim Host)

### levels:

LEVEL 1: INFO_LEVEL
   - title: Introduction to the Kobalos Linux Trojan Investigation
   - story: Welcome to the Kobalos Linux Trojan Investigation exercise. Your mission is to investigate a complex Linux threat targeting high performance computing infrastructure named Kobalos. We have provided you with a sandbox environment and MISP event containing indicators of compromise (IOCs) related to this malware.
   - objective: Analyze the provided sandbox environment, MISP event, and security profile to identify and investigate the Kobalos Linux Trojan.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Sandbox Environment
   - topology_overview: In this exercise, you will be given access to a sandbox environment containing two hosts: c2-server (Command & Control Server) and target (Victim Host). The target host is running Ubuntu and has been compromised by the Kobalos Linux Trojan. You will use SSH to access the target host with the provided credentials.
   - entry_host: target
   - role: Target
   - access_method: SSH
   - username: cyrano
   - password: cyrano (credential_source: Ansible)
   - instructions: Use the provided credentials to connect to the target host via SSH.

LEVEL 3: TRAINING_LEVEL
   - title: Identify Kobalos Payload Drop Location
   - task_description: Investigate the target host for signs of the Kobalos Linux Trojan. One common technique used by this malware is to drop its payload in a specific directory. Identify the location where the Kobalos payload has been dropped on the target host.
   - validation_logic: Use the `ls` command to list the contents of the current directory and search for files with suspicious names related to the Kobalos Trojan.
   - aligned_nice_task: T1087 - Command and Scripting Interpreter: Execution
   - demonstrated_skill: Linux File System Navigation
   - applied_knowledge: Malware Behavior Analysis
   - related_event_elements: Payload drop to /tmp/.installer (MISP Event)

LEVEL 4: TRAINING_LEVEL
   - title: Investigate Kobalos Persistence Mechanism
   - task_description: The Kobalos Linux Trojan is known for using various persistence mechanisms. One common technique is to use LD_PRELOAD to inject malicious code into legitimate processes. Investigate the target host for signs of this persistence mechanism.
   - validation_logic: Use the `strings` command to search for suspicious strings related to LD_PRELOAD in the /etc/ld.so.preload file.
   - aligned_nice_task: T1086 - Initial Access: Sustained XMRig Mining
   - demonstrated_skill: Linux Process Analysis
   - applied_knowledge: Malware Behavior Analysis
   - related_event_elements: ld.so.preload persistence (MISP Event)

LEVEL 5: TRAINING_LEVEL
   - title: Identify Kobalos C2 Communication
   - task_description: The Kobalos Linux Trojan is known to communicate with its Command & Control server over a specific port. Investigate the target host for signs of this communication.
   - validation_logic: Use the `netstat` command to list open network connections and search for connections on the specified C2 port (7070).
   - aligned_nice_task: T1071 - Network Connection Brute Force
   - demonstrated_skill: Linux Network Analysis
   - applied_knowledge: Malware Behavior Analysis
   - related_event_elements: c2 beacon to 151.80.57.191:7070 every 120s (MISP Event)

### scoring_strategy:
- Points will be awarded based on the correct identification of Kobalos artifacts, persistence mechanisms, and C2 communication.

### optional_hints:
- Hint 3: Payload drop location: Look for files with suspicious names related to the Kobalos Trojan in common directories such as /tmp, /var/tmp, or /home/user/.
- Hint 4: Persistence mechanism: Check for the presence of LD_PRELOAD strings in the /etc/ld.so.preload file.
- Hint 5: C2 communication: Look for open network connections on port 7070 using the `netstat` command.

### optional_QA:
- Q3: What is the location of the Kobalos payload drop on the target host?
   - A: /tmp/.installer

- Q4: How does the Kobalos Linux Trojan maintain persistence on the target host?
   - A: By using LD_PRELOAD to inject malicious code into legitimate processes.

- Q5: What is the IP address of the Command & Control server used by the Kobalos Linux Trojan?
   - A: 151.80.57.191 (This information is not directly provided in the sandbox or MISP event, but can be inferred from the C2 port and beacon interval.)