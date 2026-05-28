 INFO_LEVEL
------------

The scenario is based on a MISP event involving the Kobalos backdoor malware, specifically the Linux/Kobalos variant. The malware is known to target high-performance computing infrastructure and has a complex behavior that includes C2 communication, lateral movement, exfiltration, persistence, and stealing SSH credentials.

ACCESS_LEVEL
-------------

The exercise will be conducted from the `target` host with the username `cyrano`. The password for this account is also `cyrano`. Access to the `c2-server` and `next-target` hosts can be established using SSH.

TRAINING_LEVEL 1: Investigate suspicious service
--------------------------------------------------

Task: Identify the running service associated with the Kobalos malware on the target host.

*Hint*: Use command-line tools available on the target host to inspect active services and their related processes.

Validation: Check if the output of your command includes the service name mentioned in the MISP event (`ssh`).

TRAINING_LEVEL 2: Detect persistence mechanism
-----------------------------------------------

Task: Locate the persistence mechanism used by Kobalos on the target host.

*Hint*: Investigate system files, configurations, and running processes to find signs of the malware's persistence.

Validation: Check if your findings match the persistence_mechanism mentioned in the MISP event (`Embedded in sshd or stand-alone variants`).

TRAINING_LEVEL 3: Detect data exfiltration
-------------------------------------------

Task: Identify any signs of data exfiltration by Kobalos on the target host.

*Hint*: Analyze logs, network traffic, and system files to find indicators of stolen SSH credentials being sent over the network.

Validation: Check if your findings match the Exfilerated/stolen data mentioned in the MISP event (`SSH credentials`).