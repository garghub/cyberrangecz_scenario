### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The BRICKSTORM backdoor is a sophisticated 64-bit ELF executable written in Go, designed to operate on Linux systems. It employs advanced techniques such as SOCKS proxying, multi-layered web service communication, and varied command execution to obscure its activities. The backdoor uses XOR cipher encryption to hide key strings within its code and employs environment variables for connection parameters, logging, WebSocket connectors, and request handlers.

**Objective**: Investigate and mitigate the BRICKSTORM backdoor on the target system.

#### ACCESS_LEVEL
- **Entry Host**: target (IP: 192.168.50.5)
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

#### TRAINING_LEVEL 1
**Task**: Identify the suspicious service related to the BRICKSTORM backdoor.

**Description**: The BRICKSTORM backdoor is known to create a service named "vami". Investigate the running services on the target system to identify this suspicious service.

**Hint**: Use the `systemctl list-units --type=service` command to list all running services.

**Validation**: The task is marked as successful if the student identifies the "vami" service.

**Flag**: vami

#### TRAINING_LEVEL 2
**Task**: Investigate the persistence mechanism used by the BRICKSTORM backdoor.

**Description**: The BRICKSTORM backdoor modifies the PATH environment variable to maintain persistence. Check the environment variables to identify this persistence mechanism.

**Hint**: Use the `printenv` command to list all environment variables.

**Validation**: The task is marked as successful if the student identifies the PATH environment variable modification.

**Flag**: PATH

#### TRAINING_LEVEL 3
**Task**: Identify the suspicious outbound IP address used for C2 communication.

**Description**: The BRICKSTORM backdoor communicates with a C2 server at IP address 1.1.1.1. Investigate the network connections to identify this suspicious outbound IP address.

**Hint**: Use the `ss -tulnp` command to list all network connections.

**Validation**: The task is marked as successful if the student identifies the IP address 1.1.1.1.

**Flag**: 1.1.1.1

---

This scenario is designed to align with the provided MISP event, sandbox topology, and security profile, ensuring a realistic and effective training exercise for incident response.