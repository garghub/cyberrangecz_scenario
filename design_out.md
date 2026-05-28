 1. Kobalos Backdoor Investigation Exercise
2. Defence-oriented Scenario
3. Intermediate
4. Incident Response
5. Investigate a Kobalos backdoor infection in a multi-host sandbox environment

### network_topology:
- c2-server (role: c2-server, operating system: Ubuntu)
- target (role: Target, operating system: Ubuntu)
- next-target (role: Victim, operating system: Ubuntu)

### levels:

LEVEL 1: INFO_LEVEL
   - title: Kobalos Backdoor Investigation Overview
   - story: You are a member of the incident response team at CyberRangeCZ. A recent MISP event has reported a Kobalos backdoor infection in one of our systems. Your task is to investigate this incident, identify the compromised hosts, and gather evidence to support your findings.
   - objective: Investigate the Kobalos backdoor infection, identify affected hosts, and collect evidence for further analysis.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Sandbox Environment
   - topology_overview: In this exercise, you will be provided access to a multi-host sandbox environment containing three hosts: c2-server, target, and next-target. The target host is compromised by the Kobalos backdoor. You will use SSH to access the target host with the credentials:
     - username: cyrano
     - password: cyrano (credential_source: Ansible)
   - entry_host: target
   - role: Target
   - access_method: SSH
   - instructions: Connect to the target host using SSH and begin your investigation.

LEVEL 3: TRAINING_LEVEL
   - title: Identify Kobalos Backdoor Artifacts
   - task_description: Search for indicators of compromise (IOCs) related to the Kobalos backdoor on the compromised target host.
   - validation_logic: Use the `locate` command or manually search for files with known Kobalos hashes in the /tmp directory.
   - aligned_nice_task: T1077 - Initial Access
   - demonstrated_skill: File System Navigation and Searching
   - applied_knowledge: Malware Analysis Techniques
   - related_event_elements: Kobalos malware, hashes (e.g., 2c693d26ba9df26edf77557c1a709528)

LEVEL 4: TRAINING_LEVEL
   - title: Investigate Network Connections
   - task_description: Examine the network connections of the compromised target host to identify any unusual or suspicious activity.
   - validation_logic: Use `netstat` or `ss` commands to inspect active connections and listen ports on the target host.
   - aligned_nice_task: T1045 - Network Scanning
   - demonstrated_skill: Network Traffic Analysis
   - applied_knowledge: Network Security Monitoring
   - related_event_elements: Kobalos c2 communication, port 7070

LEVEL 5: TRAINING_LEVEL
   - title: Gather Evidence and Report Findings
   - task_description: Collect evidence of the Kobalos backdoor infection on the target host and prepare a report summarizing your findings.
   - validation_logic: Use `ls`, `cat`, or other commands to gather relevant files, logs, and indicators of compromise (IOCs). Write a brief report summarizing your investigation results.
   - aligned_nice_task: T1027 - System Analysis Reporting
   - demonstrated_skill: Evidence Collection and Report Writing
   - applied_knowledge: Incident Response Procedures
   - related_event_elements: Kobalos backdoor, compromised hosts, evidence collection

### scoring_strategy:
- Points will be awarded based on the completeness and accuracy of your findings, as well as the quality of your report.

### optional_hints:
- Hint 1: Look for files with known Kobalos hashes in the /tmp directory.
- Hint 2: Use `netstat` or `ss` commands to inspect active connections and listen ports on the target host.

### optional_QA:
- Q1: What is the primary goal of this exercise?
   - A: Investigate a Kobalos backdoor infection, identify affected hosts, and collect evidence for further analysis.

- Q2: What are the credentials to access the target host?
   - A: Username: cyrano, Password: cyrano (credential_source: Ansible)