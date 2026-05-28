 1. Kobalos Linux Trojan Investigation Exercise
2. Defence-oriented Scenario
3. Intermediate
4. Incident Response Profile
5. Investigate a Kobalos Linux trojan infection in a high-performance computing infrastructure

### network_topology:
- c2-server (c2-server) - Ubuntu 20.04 LTS
- target (Target) - Ubuntu 20.04 LTS
- next-target (Next Target) - Ubuntu 20.04 LTS

### levels:

LEVEL 1: INFO_LEVEL
   - title: Introduction
   - story: You are an incident responder tasked with investigating a Kobalos Linux trojan infection in a high-performance computing infrastructure. The initial access was gained via SSH bruteforce, and the payload was dropped to /tmp/.installer. The malware communicates with the command and control server at 151.80.57.191:7070 every 120 seconds.
   - objective: Your goal is to identify the compromised host, gather evidence of the infection, and determine the scope of the attack.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Sandbox
   - topology_overview: The sandbox consists of three hosts: c2-server, target, and next-target. Each host runs Ubuntu 20.04 LS and is connected via a network switch. You will access the target host using SSH with the provided credentials.
   - entry_host: target (Target)
   - role: Target
   - access_method: SSH
   - username: cyrano
   - password: cyrano (from Ansible configuration)
   - credential_source: Ansible
   - instructions: Use the provided credentials to log into the target host via SSH.

LEVEL 3: TRAINING_LEVEL
   - title: Identify Compromised Host
   - task_description: Determine which host in the sandbox is compromised by checking for the presence of the Kobalos payload (/tmp/.installer).
   - validation_logic: Check if the file /tmp/.installer exists on the target host.
   - aligned_nice_task: T1077 - Initial Access
   - demonstrated_skill: Linux File System Navigation
   - applied_knowledge: Identifying malware artifacts
   - related_event_elements: /tmp/.installer (MISP Event)

LEVEL 4: TRAINING_LEVEL
   - title: Gather Evidence of Infection
   - task_description: Collect logs and configuration files that may contain indicators of compromise.
   - validation_logic: Search for relevant log files, such as /var/log/auth.log or /var/log/syslog, and check for suspicious activity related to the Kobalos trojan.
   - aligned_nice_task: T1027 - Command and Scripting Interpreter
   - demonstrated_skill: Linux Log Analysis
   - applied_knowledge: Identifying malware behavior
   - related_event_elements: /var/log/auth.log, /var/log/syslog (MISP Event)

LEVEL 5: TRAINING_LEVEL
   - title: Determine the Scope of the Attack
   - task_description: Investigate reachable hosts from the compromised host and check for signs of lateral movement or additional infections.
   - validation_logic: Use tools like nmap, netstat, or dig to discover reachable hosts and examine their configurations for indicators of compromise.
   - aligned_nice_task: T1021 - Initial Access - Lateral Movement
   - demonstrated_skill: Network Scanning and Enumeration
   - applied_knowledge: Identifying malware propagation techniques
   - related_event_elements: N/A (MISP Event does not provide specific lateral movement details)

### scoring_strategy:
- Points will be awarded based on the completeness and accuracy of the investigation, as well as the ability to identify indicators of compromise.

### optional_hints:
- Hint 1: Check for unusual network connections or processes running on the compromised host.
- Hint 2: Look for suspicious files in common malware drop locations, such as /tmp, /var/spool, and /root.
- Hint 3: Examine system logs for signs of unauthorized access or unusual activity.

### optional_QA:
- Q1: What is the purpose of the target host in this scenario?
   - A: High-performance computing infrastructure

- Q2: Which tool can be used to discover reachable hosts from the compromised host?
   - A: nmap, netstat, or dig (multiple answers are acceptable)