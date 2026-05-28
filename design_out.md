 INFO_LEVEL:
```
Sandbox Overview:
The sandbox consists of three hosts: c2-server, target, and next-target. The c2-server is running an SSH server (service name: ssh) and is communicating with the target host over port 4444. The target host has a Kobalos backdoor (malware_name: Complex Linux threat targeting high performance computing infrastructure) embedded in its OpenSSH server executable (sshd). The next-target host is reachable from the target host and is used for lateral movement.
```

ACCESS_LEVEL:
```
Access Level:
You have access to the entry host, which is the target host with username cyrano and password cyrano. You can use SSH to connect to other hosts in the sandbox.
```

TRAINING_LEVEL 1:
```
Task: Identify/investigate/detect suspicious service on the target host (Flag: sshd)

Objective:
Determine if the sshd process running on the target host is a sign of compromise.

Hint:
Investigate the process list, check for unusual activity, and look for signs of Kobalos in the process or its associated files.

Validation:
Verify that the sshd process is running and check if it has any suspicious characteristics related to Kobalos.
```

TRAINING_LEVEL 2:
```
Task: Identify/investigate/detect malicious services on the target host (Flag: Kobalos)

Objective:
Determine if there are any other malicious services running on the target host that could be related to Kobalos.

Hint:
Use tools like netstat, lsof, or ps to inspect open network connections and running processes. Look for unusual activity or known indicators of compromise (IOCs) associated with Kobalos.

Validation:
Verify the presence of any additional malicious services related to Kobalos on the target host.
```

TRAINING_LEVEL 3:
```
Task: Contain/Block C2 communication (Flag: 4444)

Objective:
Prevent further communication between the target host and the c2-server by blocking port 4444.

Hint:
Use iptables or firewalld to block incoming and outgoing traffic on port 4444 from the target host.

Validation:
Verify that no more data is being exchanged between the target host and the c2-server over port 4444.
```