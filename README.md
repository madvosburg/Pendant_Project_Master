Led a project to develop an RS-485 communication system for a pendant remote control as part of the Jay partner pendant development project at Conductix-Wampfler. The project aimed to create a wired version of the Jay Radio system, utilizing STM32 microcontrollers in a master-slave configuration. Key responsibilities included designing and implementing the embedded system, selecting appropriate transceivers, and developing both hardware and software components.

The objective on the master side was to track a certain number of buttons (testing with four) and send the state of each to the slave side. Variables for each on and off state of each button tracked were defined. If a button was not pressed, the corresponding relay state would be off, and oppositely, if a button was pressed, the relay would need to be on. The master logic for each button was structured as follows: if it was not pressed, the program sent a RELAY_OFF message. When pressed, the program recognized the signal and sent a RELAY_ON message. This message was sent every 10 milliseconds. To verify correct data transmission from master to slave, a checksum, also known as a CRC, was implemented. To ensure there were no faults occurring within the program, a watchdog timer was added. In this application, the watchdog ensured that data was being sent on time. If no data was being sent or received within the millisecond time frame, the watchdog reset the program every 3 seconds. Putty communication was also added to count button presses, which were sent through UART, to facilitate easy tracking during testing.
