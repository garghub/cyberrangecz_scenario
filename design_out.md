 1. BRICKSTORM Backdoor Investigation Exercise
2. Defence-oriented
3. Intermediate
4. Incident Response
5. Investigate a BRICKSTORM backdoor incident in a simulated environment

### network_topology:
- c2-server (Role: C2 Server, Operating System: Ubuntu)
- target (Role: Target, Operating System: Ubuntu)

### levels:

LEVEL 1: INFO_LEVEL
   - title: Introduction to the BRICKSTORM Backdoor Incident
   - story: Welcome to the BRICKSTORM Backdoor Investigation Exercise. Your mission is to investigate a suspected BRICKSTORM backdoor incident on a target system. The malware is known for its sophisticated Go-based backdoor, secure command and control (C2), and self-monitoring function that reinstalls or restarts if disrupted.
   - objective: Your goal is to identify the presence of the BRICKSTORM backdoor, understand its behavior, and gather evidence to support your findings.

LEVEL 2: ACCESS_LEVEL
   - title: Accessing the Target System
   - topology_overview: In this exercise, you will be given access to a target system (IP address: 192.168.50.5) that is suspected of being compromised by the BRICKSTORM backdoor. The target system runs Ubuntu and has an SSH service available for login.
   - entry_host: target
   - role: Target
   - access_method: SSH
   - username: cyrano
   - password: cyrano (credential_source: Ansible)
   - instructions: Connect to the target system using SSH and begin your investigation.

LEVEL 3: TRAINING_LEVEL
   - title: Identify BRICKSTORM Backdoor Indicators of Compromise (IOCs)
   - task_description: Search for known indicators of compromise related to the BRICKSTORM backdoor, such as hashes, IP addresses, domains, or filenames.
   - validation_logic: Use command-line tools like `grep` and `find` to search for IOCs in relevant system directories (e.g., /etc, /var/log, /home).
   - aligned_nice_task: Investigate Malware Artifacts (NICE TA-0014)
   - demonstrated_skill: Linux Command Line Navigation and Execution (NICE ST-0002)
   - applied_knowledge: Understanding BRICKSTORM Backdoor IOCs (NICE KA-0036)
   - related_event_elements: Hashes, IP addresses, domains, filenames

LEVEL 4: TRAINING_LEVEL
   - title: Analyze System Logs for BRICKSTORM Backdoor Activity
   - task_description: Examine system logs (e.g., /var/log/syslog, /var/log/auth.log) to identify any suspicious activity related to the BRICKSTORM backdoor.
   - validation_logic: Use command-line tools like `grep` and `less` to search for specific keywords or patterns in system logs.
   - aligned_nice_task: Analyze System Logs (NICE TA-0013)
   - demonstrated_skill: Linux Command Line Navigation and Execution (NICE ST-0002)
   - applied_knowledge: Understanding BRICKSTORM Backdoor Behavior (NICE KA-0037)
   - related_event_elements: System logs, keywords, patterns

LEVEL 5: TRAINING_LEVEL
   - title: Gather Evidence and Document Findings
   - task_description: Collect evidence of the BRICKSTORM backdoor activity and document your findings in a report.
   - validation_logic: Use command-line tools like `cp`, `mv`, and text editors (e.g., nano, vim) to gather relevant files and create a report detailing your investigation.
   - aligned_nice_task: Collect and Document Evidence (NICE TA-0012)
   - demonstrated_skill: Linux Command Line Navigation and Execution (NICE ST-0002)
   - applied_knowledge: Report Writing (NICE KA-0038)
   - related_event_elements: Evidence, report writing

### scoring_strategy:
Participants will be scored based on the completeness and accuracy of their findings, as well as the quality of their report.

### optional_hints:
Hint 1: Look for known BRICKSTORM backdoor hashes in system files.
Hint 2: Check system logs for unusual network connections or commands.
Hint 3: Examine the target system's configuration files for any signs of malicious activity.

### optional_QA:
Question 1: What is the primary purpose of the BRICKSTORM backdoor?
Answer: The primary purpose of the BRICKSTORM backdoor is to provide secure command and control (C2) capabilities for attackers.

Question 2: What are some common indicators of compromise related to the BRICKSTORM backdoor?
Answer: Some common indicators of compromise related to the BRICKSTORM backdoor include hashes, IP addresses, domains, filenames, and unusual network connections or commands in system logs.