 1. BRICKSTORM Backdoor Sandbox Scenario
2. Cybersecurity Exercise
3. Defence-oriented
4. Intermediate
5. Incident Response
6. Investigate a BRICKSTORM backdoor infection in a multi-host sandbox environment

### network_topology:
- c2-server (Ubuntu)
  - Role: Command and Control Server
  - Purpose: Hosts the C2 server for the BRICKSTORM backdoor

- target (Ubuntu)
  - Role: Victim
  - Purpose: Infected with the BRICKSTORM backdoor

- next-target (Ubuntu)
  - Role: Next Target
  - Purpose: A reachable host from the victim for lateral movement analysis

### levels:

LEVEL 1: INFO_LEVEL
   - title: Introduction to the BRICKSTORM Backdoor Scenario
   - story: Welcome to the BRICKSTORM Backdoor sandbox exercise. Your mission is to investigate a suspected infection of the BRICKSTORM backdoor on the target host. The malware is known for its sophisticated capabilities, including secure communication with a command and control (C2) server, installing other components, and exfiltrating data.
   - objective: Your goal is to identify the presence of the BRICKSTORM backdoor, understand its behavior, and gather evidence for further analysis.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Sandbox Environment
   - topology_overview: In this exercise, you will be provided access to a lab environment containing three hosts: c2-server, target, and next-target. The target host is the primary focus of your investigation as it is suspected to be infected with the BRICKSTORM backdoor. You can SSH into the target host using the credentials provided below.
   - entry_host: target
   - role: Victim
   - access_method: SSH
   - username: cyrano
   - password: cyrano (credential_source: Ansible)
   - instructions: Connect to the target host using your provided credentials and begin your investigation.

LEVEL 3: TRAINING_LEVEL
   - title: Identify BRICKSTORM Backdoor Indicators of Compromise (IOCs)
   - task_description: Use YARA rules to search for known IOCs related to the BRICKSTORM backdoor on the target host.
   - validation_logic: Verify that the output includes at least one match for a BRICKSTORM backdoor YARA rule.
   - aligned_nice_task: Analyze Malware Artifacts (NICE TA3071)
   - demonstrated_skill: Use YARA rules to detect malware
   - applied_knowledge: Identify indicators of compromise for the BRICKSTORM backdoor
   - related_event_elements: Yara rule(s) from MISP event

LEVEL 4: TRAINING_LEVEL
   - title: Investigate Lateral Movement with BRICKSTORM Backdoor
   - task_description: Examine the target host for evidence of lateral movement by the BRICKSTORM backdoor. Look for indicators such as SSH keys, transferred files, or network connections to other hosts.
   - validation_logic: Verify that you find at least one piece of evidence suggesting lateral movement by the BRICKSTORM backdoor.
   - aligned_nice_task: Investigate Network Traffic (NICE TA0102)
   - demonstrated_skill: Analyze network traffic for signs of malicious activity
   - applied_knowledge: Identify indicators of lateral movement for the BRICKSTORM backdoor
   - related_event_elements: Network indicators from MISP event

LEVEL 5: TRAINING_LEVEL
   - title: Analyze Logs for BRICKSTORM Backdoor Activity
   - task_description: Review system logs on the target host to find evidence of BRICKSTORM backdoor activity. Look for unusual network connections, process executions, or user account activity.
   - validation_logic: Verify that you find at least one piece of evidence suggesting BRICKSTORM backdoor activity in the logs.
   - aligned_nice_task: Analyze System Logs (NICE TA0103)
   - demonstrated_skill: Analyze system logs for signs of malicious activity
   - applied_knowledge: Identify indicators of activity for the BRICKSTORM backdoor in system logs
   - related_event_elements: Network, process, and user account indicators from MISP event

### scoring_strategy:
- Each level will be scored based on the completeness and accuracy of the participant's findings.
- Bonus points may be awarded for creative or innovative approaches to the investigation.

### optional_hints:
- Hint 3 (Level 3): Check the /home/cyrano directory for files with known BRICKSTORM backdoor hashes.
- Hint 4 (Level 4): Look for SSH keys in the ~/.ssh directory on the target host that match those found on the next-target host.
- Hint 5 (Level 5): Review system logs such as /var/log/auth.log, /var/log/syslog, and /var/log/messages for signs of BRICKSTORM backdoor activity.

### optional_QA:
- Q3: What is the purpose of the target host in this scenario?
  A: The target host is suspected to be infected with the BRICKSTORM backdoor and is the primary focus of your investigation.

- Q4: What are some indicators of compromise for the BRICKSTORM backdoor that you should look for during your investigation?
  A: Some indicators of compromise for the BRICKSTORM backdoor include YARA rule matches, lateral movement evidence (such as SSH keys, transferred files, or network connections to other hosts), and unusual activity in system logs.