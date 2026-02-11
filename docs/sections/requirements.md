
## Task 2–4: Requirements, Classification, Rationale, and Testability

Write **at least three requirements**.  
Add more rows if needed.

| Requirement ID | Requirement (single declarative sentence) | Classification (Functional / Safety / Non-Functional) | Rationale (Why important? What could go wrong if violated?) | Test Intent / Testability (How violation would be detected) |
|---------------|-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------|-------------------------------------------------------------|
| R-1 |The system shall be able to update over wired connection with another device | Functional |The  system is required to be able to update its firmware| Violation occurs if the system is unable to update its firmware over wired connection |
| R-2 |The system shall be able to update over a wireless connection with another device  | Functional | The  system is required to be able to update its firmware | Violation occurs if the system is unable to update its firmware over wireless connection |
| R-3 | The system shall enter bootloader mode if a push button is toggled twice within 3000ms of powerup or reset | Functional  | Provides a manual method to enter bootloader mode | Violation detected if a double press is detected within 3000ms and system fails to enter bootloader mode |
| R-4 |The software shall be portable to similar devices with minimal changes  |Non-Functional | The software should be designed to be portable with similar microprocessors and not require big changes for compatibility | Violation occurs if the software is incompatible with similar devices with minimal changes or if massive software changes are needed |
| R-5 | The system shall check the completion status of the previous flash operation status before entering application mode | Safety | Prevents running incomplete flashed software that can cause unexpected behaviour | Violation detected if system start running application software when flash complete flag is found to be not set |
| R-6 | Upon power up system shall run integrity checks on the code flashed, if there is a mismatch found system shall remain in bootloader mode | Safety | This can lead to running of incorrect/ incomplete application code and lead to unsafe and unexpected behaviour | Violation detected if system enters  directly to application mode after corrupting a small part of application flash  |
| R-7 | System shall enter application mode if previous flash operation was not interrupted and 3000ms has elapsed without button press sequence upon reset on power ON  | Functional | It is required to enter application mode if there are no user interactions| Violation detected if system does not transfer control to application software after 3000ms has elapsed without button press|
| R-8 | The DFU logic will remain transport agnostic, utilizing a shared API for data reception from either USB CDC or BLE |Non-Functional|Critical for portability for nRF52820, where RAM is scarce,and hence modularity mandatory|Code inspection for the abstraction layer. Ensure both transports can invoke the same flash write|


