
## Task 2–4: Requirements, Classification, Rationale, and Testability

Write **at least three requirements**.  
Add more rows if needed.

| Requirement ID | Requirement (single declarative sentence) | Classification (Functional / Safety / Non-Functional) | Rationale (Why important? What could go wrong if violated?) | Test Intent / Testability (How violation would be detected) |
|---------------|-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------|-------------------------------------------------------------|
| R-1 |The system shall be able to update over wired connection with another device | Functional |The  system is required to be able to update its firmware| Violation occurs if the system is unable to update its firmware over wired connection |
| R-2 |The system shall be able to update over a wireless connection with another device  | Functional | The  system is required to be able to update its firmware | Violation occurs if the system is unable to update its firmware over wireless connection |
| R-3 |The system shall enter bootloader mode if the button is pressed twice within 3 seconds of reset or power on | Functional | Ability to enter bootloader is requried for carrying out firmware updates | Violation occurs if the system does not enter bootloader mode when the button is double pressed within 3 seconds of boot |
| R-4 |The software shall be portable to similar devices with minimal changes  |Non-Functional  | The software should be designed to be portable with similar microprocessors and not require big changes for compatibility | Violation occurs if the software is incompatible with similar devices with minimal changes or if massive software changes are needed |
| R-5 |The system shall be able to recover from an interrupted update | Safety | The system is required to be resilient against power losses and connection losses which could otherwise result in software corruption| Violation occurs if a power loss or connection loss during update corrupts the software, rendering the device unusable |
