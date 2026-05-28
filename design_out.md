 INFO_LEVEL:
------------------

The provided MISP event describes a high confidence Linux/Kobalos backdoor that targets high performance computing infrastructure. The malware is portable to multiple operating systems, including Linux, BSD, Solaris, and possibly AIX and Windows. It exhibits C2, lateral movement, exfiltration, persistence, and potentially botnet behavior.

ACCESS_LEVEL:
--------------

The sandbox environment consists of three hosts: c2-server (192.168.40.5), target (192.168.50.5), and next-target (192.168.50.6). The user account "cyrano" has been created on all hosts with password "cyrano". SSH access is available between the hosts, and the target host runs an OpenSSH server (sshd) service on port 7070.

TRAINING_LEVEL:
---------------

### TRAINING_LEVEL_1

Task: Investigate the initial compromise of the target host by analyzing its logs, configuration files, and system state to identify any signs of malicious activity related to Kobalos.

Validation: Observe indicators of compromise (IOCs) from the MISP event in relevant logs or artifacts on the target host.

Hint: Start by examining the sshd logs for unusual connections, failed login attempts, or other suspicious activities. Additionally, check system files and configuration settings for any signs of malware presence or persistence mechanisms.

### TRAINING_LEVEL_2

Task: Identify the C2 server IP address and port used by the Kobalos backdoor on the target host.

Validation: Verify that the obtained C2 IP address and port match those provided in the MISP event (151.80.57.191, 7070).

Hint: Analyze network traffic or system logs to find connections to the C2 server. You may also want to look for any malware-related artifacts on the target host that could provide clues about the C2 communication.

### TRAINING_LEVEL_3

Task: Determine if there is lateral movement within the network by checking for signs of Kobalos activity on the next-target host.

Validation: Observe indicators of compromise (IOCs) from the MISP event in relevant logs or artifacts on the next-target host.

Hint: Examine system files, configuration settings, and network traffic to find any signs of malicious activity related to Kobalos. Additionally, check for any unusual SSH connections between the target and next-target hosts.