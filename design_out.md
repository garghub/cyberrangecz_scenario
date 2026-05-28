 INFO_LEVEL:
```
Scenario Name: BRICKSTORM Backdoor Investigation
Description: This exercise focuses on investigating a BRICKSTORM backdoor infection in a Linux environment. The goal is to identify indicators of compromise, detect malicious activities, and contain the threat.
```

ACCESS_LEVEL:
```
Access Level: Incident Response
User: cyrano
Password: cyrano
SSH Access: Target (192.168.50.5) and Next-Target (192.168.50.6) hosts
```

TRAINING_LEVEL 1:
```
Task Title: Identify suspicious service running on the target host
Flag: unknown (from MISP event)

Instructions:
As a first step, identify the process name of the suspected BRICKSTORM backdoor. Use the `ps aux` command to list all processes and find the one with the malware's hash (57bd98dbb5a00e54f07ffacda1fea91451a0c0b532cd7d570e98ce2ff741c21d) in its executable file.

Hint: The malware's hash is embedded within the executable file name.
```

TRAINING_LEVEL 2:
```
Task Title: Detect lateral movement between hosts
Flag: unknown (from MISP event)

Instructions:
Investigate potential lateral movement between the target and next-target hosts by looking for file transfers using the `rsync` or similar tools. Use the `netstat -tuln` command to check open connections between the hosts, and look for any unusual traffic patterns.

Hint: The malware may use a custom service or protocol for communication.
```

TRAINING_LEVEL 3:
```
Task Title: Contain C2 communication
Flag: [redacted] (from MISP event)

Instructions:
To prevent further command and control (C2) communications, block the identified C2 IP address and port on the target host. Use `iptables` to create a rule that denies incoming traffic from the C2 IP address on the specified port.

Hint: The C2 IP address and port are provided in the MISP event.
```