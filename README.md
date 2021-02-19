## Windows Sandbox Configurations
## Daniel Douglas Soyka [ddsoyka@pm.me](mailto:ddsoyka@pm.me)

# Abstract

This repository contains a set of preconfigured [Windows Sandbox](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-sandbox/windows-sandbox-overview) configuration files.

These configurations are made available in order to give interested users a number of setups which provide a virtualized sandbox environment with a known amount of security.

# Requirements

1. Windows 10 Pro/Enterprise/Education Build 18305+
2. AMD64 Architecture
3. 4GB+ Memory
4. 1GB+ Free Disk Space
5. 2+ CPU Cores

# Configurations

The following configurations are provided as part of this repository:

1. ## [default.wsb](default.wsb)
    - Provides an acceptable tradeoff between security & usefulness.
    - All graphics, networking & I/O capabilities are disabled.
    - The following folders are mounted in read-only mode:
        1. `C:\Program Files`
        2. `C:\Program Files (x86)`
        3. `C:\Users\Public\Documents`
        4. `C:\Users\Public\Downloads`
        5. `C:\Users\Public\Music`
        6. `C:\Users\Public\Pictures`
        7. `C:\Users\Public\Videos`
2. ## [permissive.wsb](permissive.wsb)
    - Provides the maximum amount of usefulness at the expense of security.
    - All graphics, networking & I/O capabilities are enabled.
    - The following folders are mounted in read-only mode:
        1. `C:\Program Files`
        2. `C:\Program Files (x86)`
    - The following folders are mounted in read-write mode:
        1. `C:\Users\Public\Documents`
        2. `C:\Users\Public\Downloads`
        3. `C:\Users\Public\Music`
        4. `C:\Users\Public\Pictures`
        5. `C:\Users\Public\Videos`
3. ## [restricted.wsb](restricted.wsb)
    - Provides the maximum amount of security at the expense of usefulness.
    - All capabilities are disabled.
    - The host filesystem is completely inaccessible.
    - The sandbox runs in an enhanced protection mode.

# Memory Limit

All configurations are provided with a maximum of 2048MB of RAM. It is recommended that users change this value to suit their own needs and purposes.

# Usage

It is recommended that users choose the configuration which meets their security needs.

To use a configuration file, invoke the `WindowsSandbox` command, with the path of the configuration file to use, from a Powershell terminal on the host system.

## Example

```powershell
WindowsSandbox default.wsb
```