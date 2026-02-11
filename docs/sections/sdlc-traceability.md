# 1. Key Sequence Diagrams

## SD-1: System Start-up and Boot Decision
```mermaid
sequenceDiagram
    participant Power
    participant Bootloader
    participant Button
    participant Flash
    participant Application

    Power-->>Bootloader: Power On / Reset
    Bootloader->>Button: Monitor button input (3000 ms)
    Bootloader->>Flash: Check flash completion flag
    Bootloader->>Flash: Run integrity check

    alt Double press detected
        Bootloader->>Bootloader: Enter Bootloader Mode
    else Integrity check failed
        Bootloader->>Bootloader: Remain in Bootloader Mode
    else No button press and integrity OK
        Bootloader->>Application: Jump to application
    end
